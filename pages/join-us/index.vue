<template>
    <div class="text-gray-900 dark:text-slate-50 body-font container mx-auto my-5 ">
        <FetchDataWraper :error="error" :pending="pending">
            <template #main>
                <section class="mb-20" v-if="champs && champs.length > 0">
                    <div class="flex flex-wrap w-full mb-3 md:mb-6">
                        <div class="lg:w-1/2 w-full ">
                            <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 ">البطولات المتاحة للانضمام </h1>
                            <div class="h-1 w-20 bg-yellow-500 rounded"></div>
                        </div>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
                        <template v-for="(champ, index) in champs" :key="champ.id">
                            <div class="card card-compact w-84 bg-slate-100 dark:bg-slate-600 shadow-xl">
                                <figure class="bg-amber-50">
                                    <nuxt-img :src="`${url}${champ.champ_logo}`" :alt="champ.name" class="h-52" />
                                </figure>
                                <div class="card-body">
                                    <h2 class="card-title">{{ champ.name }}</h2>
                                    <p>سارع بالانضمام مع فريقك</p>
                                    <div class="card-actions justify-end">
                                        <Nuxt-link :to="`/join-us/${champ.id}`"
                                            class="btn btn-warning shadow-lg hover:shadow-yellow-500">انضم
                                            الان</Nuxt-link>
                                    </div>
                                </div>
                            </div>
                        </template>
                    </div>
                </section>
                <div v-else
                    class="text-zinc-700 dark:text-slate-50 text-lg h-50 flex flex-col justify-center items-center py-10">
                    <Icon name="line-md:alert-circle" class="block text-9xl" />
                    <h3>لا يوجد بطولات حاليا</h3>
                </div>
            </template>
        </FetchDataWraper>
    </div>
</template>

<script setup lang="ts">
useHead({
    title: `انضم لبطولات زات للبلوت`,
})
import type { IJoinChamp } from '@/Models/IChamp';
const client = useStrapiClient()
const url = useStrapiUrl().slice(0, -4) // remove /api from strapi url 

const champs = ref<IJoinChamp[] | null>(null)
const error = ref<string | null>(null)
const pending = ref(false)

const fetchData = () => {
    pending.value = true
    return client(`/leagues/opened_to_join`, { method: 'GET' })
        .then((data: any) => {
            champs.value = data.data
            pending.value = false
        }).catch((err) => {
            console.error(err)
            error.value = "تعذر تحميل البيانات."
            pending.value = false
        })
}
onServerPrefetch(fetchData)
onBeforeMount(fetchData)

</script>

<style scoped></style>