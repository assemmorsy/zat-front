<template>
    <FetchDataWraper class="md:w-5/6 lg:w2/3 mx-auto text-gray-900 dark:text-slate-50" :error="error" :pending="pending">
        <template #main>
            <section class="py-10 h-full" v-if="blogs && blogs.length > 0">
                <div class="flex flex-wrap w-full mb-3 md:mb-6">
                    <div class="lg:w-1/2 w-full ">
                        <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 ">اخبار زات</h1>
                        <div class="h-1 w-20 bg-yellow-500 rounded"></div>
                    </div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 mb-20">
                    <template v-for="(blog, index) in blogs" :key="index">
                        <Blog :blog="blog" />
                    </template>
                </div>
                <div class="flex justify-center mt-8 absolute bottom-3 left-1/2 -translate-x-1/2">
                    <div class="join ">
                        <button class="join-item btn bg-blue-500 text-white hover:bg-blue-300 dark:text-slate-50"
                            :disabled="(pgNum - 1) * pgSize <= 0" @click="handleNewPage(-1)">«
                        </button>
                        <button class="join-item btn dark:bg-slate-600 dark:text-slate-50 border-0">صفحة « {{ pgNum }}
                            »</button>
                        <button class="join-item btn bg-blue-500 text-white hover:bg-blue-300 dark:text-slate-50"
                            :disabled="totalBlogsCount - (pgNum * pgSize) <= 0" @click="handleNewPage(1)"> »</button>
                    </div>
                </div>
            </section>
            <div v-else
                class="text-zinc-700 dark:text-slate-50 text-lg h-50 flex flex-col justify-center items-center py-10">
                <Icon name="line-md:alert-circle" class="block text-9xl" />
                <h3>لا يوجد اخبار حاليا</h3>
            </div>
        </template>
    </FetchDataWraper>
</template>

<script setup lang="ts">
import type {IBlog} from '@/Models/IBlog'
const pgSize = 10;
const route = useRoute()
const router = useRouter()

const client = useStrapiClient()
const blogs = ref<IBlog[] | null>(null)
const error = ref<string | null>(null)
const pending = ref(false)
const pgNumStr = route.query.pageNum as string;
let pgNum = 1;
if (pgNumStr && !isNaN(parseInt(pgNumStr))) pgNum = parseInt(pgNumStr)
const totalBlogsCount = ref(0)
const fetchData = () => {
    pending.value = true
    return client(`/blogs?pgSize=${pgSize}&pgNum=${pgNum}`, { method: 'GET' })
        .then((data: any) => {
            blogs.value = data.blogs
            pending.value = false
            totalBlogsCount.value = data.totalCount
            useHead({
                title: `اخبار زات`,
            })
        }).catch((err) => {
            console.error(err)
            error.value = "تعذر تحميل البيانات."
            pending.value = false
        })
}
onServerPrefetch(fetchData)
onBeforeMount(fetchData)
const handleNewPage = (direction: -1 | 1) => {
    pgNum += direction
    router.push(`/blogs?pageNum=${pgNum}`)
}

watch(
    () => route.query,
    (newQuery, oldQuery) => {
        if (newQuery.pageNum !== oldQuery.pageNum) {
            fetchData();
        }
    }
);
</script>

<style scoped>
.team-avatar img {
    object-fit: contain;
}
</style>