<template>
    <footer
        class=" flex flex-col md:flex-row justify-around items-center  dark:text-slate-50 border-t border-slate-600 dark:border-slate-100 py-2">
        <div class="flex justify-center items-center">
            <img class="mx-5" width="75" height="75"
                :src="useColorMode().preference === 'dark' ? '/images/zat-logo-white.svg' : '/images/zat-logo-black.svg'"
                alt="zat logo" />
            <p class="mx-5 text-sm"> لبطولات البلوت الاحترافية<br />المنصة الاحترافية الاولى لرياضة البلوت</p>
        </div>
        <div class=" flex justify-around my-5 ">

            <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href="https://www.snapchat.com/add/zat_baloot" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 1536 1536">
                    <path style="fill: #fffb00;"
                        d="M1280 1020q0-22-22-27q-67-14-118-58t-80-109q-7-14-7-25q0-15 19.5-26t42.5-17t42.5-20.5T1177 701q0-19-18.5-31.5T1120 657q-11 0-31 8t-32 8q-4 0-12-2q5-63 5-115q0-78-17-114q-36-78-102.5-121.5T778 277q-198 0-275 165q-18 38-18 115q0 38 6 114q-10 2-15 2q-11 0-31.5-8t-30.5-8q-20 0-37.5 12.5T359 702q0 21 19.5 35.5T421 758t42.5 17t19.5 26q0 11-7 25q-64 138-198 167q-22 5-22 27q0 47 138 69q2 5 6 26t11 30.5t23 9.5q13 0 38.5-5t38.5-5q35 0 67.5 15t54.5 32.5t57.5 32.5t76.5 15q43 0 79-15t57.5-32.5t54-32.5t67.5-15q13 0 39 4.5t39 4.5q15 0 22.5-9.5t11.5-31t5-24.5q138-22 138-69zm256-732v960q0 119-84.5 203.5T1248 1536H288q-119 0-203.5-84.5T0 1248V288Q0 169 84.5 84.5T288 0h960q119 0 203.5 84.5T1536 288z" />
                </svg>
            </a>
            <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href="https://youtube.com/@zat_baloot?si=vPFZgZSdWQXns47V" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16">
                    <path fill="#FF0000"
                        d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104l.022.26l.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105l-.009.104c-.05.572-.124 1.14-.235 1.558a2.007 2.007 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006l-.087-.004l-.171-.007l-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.007 2.007 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31.4 31.4 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103l.003-.052l.008-.104l.022-.26l.01-.104c.048-.519.119-1.023.22-1.402a2.007 2.007 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007l.172-.006l.086-.003l.171-.007A99.788 99.788 0 0 1 7.858 2h.193zM6.4 5.209v4.818l4.157-2.408L6.4 5.209z" />
                </svg>
            </a>
            <!-- <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href="https://www.tiktok.com/@zatbaloot" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 256 290">
                    <path fill="#FF004F"
                        d="M189.72 104.421c18.678 13.345 41.56 21.197 66.273 21.197v-47.53a67.115 67.115 0 0 1-13.918-1.456v37.413c-24.711 0-47.59-7.851-66.272-21.195v96.996c0 48.523-39.356 87.855-87.9 87.855c-18.113 0-34.949-5.473-48.934-14.86c15.962 16.313 38.222 26.432 62.848 26.432c48.548 0 87.905-39.332 87.905-87.857v-96.995h-.002Zm17.17-47.952c-9.546-10.423-15.814-23.893-17.17-38.785v-6.113h-13.189c3.32 18.927 14.644 35.097 30.358 44.898ZM69.673 225.607a40.008 40.008 0 0 1-8.203-24.33c0-22.192 18.001-40.186 40.21-40.186a40.313 40.313 0 0 1 12.197 1.883v-48.593c-4.61-.631-9.262-.9-13.912-.801v37.822a40.268 40.268 0 0 0-12.203-1.882c-22.208 0-40.208 17.992-40.208 40.187c0 15.694 8.997 29.281 22.119 35.9Z" />
                    <path
                        d="M175.803 92.849c18.683 13.344 41.56 21.195 66.272 21.195V76.631c-13.794-2.937-26.005-10.141-35.186-20.162c-15.715-9.802-27.038-25.972-30.358-44.898h-34.643v189.843c-.079 22.132-18.049 40.052-40.21 40.052c-13.058 0-24.66-6.221-32.007-15.86c-13.12-6.618-22.118-20.206-22.118-35.898c0-22.193 18-40.187 40.208-40.187c4.255 0 8.356.662 12.203 1.882v-37.822c-47.692.985-86.047 39.933-86.047 87.834c0 23.912 9.551 45.589 25.053 61.428c13.985 9.385 30.82 14.86 48.934 14.86c48.545 0 87.9-39.335 87.9-87.857V92.85h-.001Z" />
                    <path fill="#00F2EA"
                        d="M242.075 76.63V66.516a66.285 66.285 0 0 1-35.186-10.047a66.47 66.47 0 0 0 35.186 20.163ZM176.53 11.57a67.788 67.788 0 0 1-.728-5.457V0h-47.834v189.845c-.076 22.13-18.046 40.05-40.208 40.05a40.06 40.06 0 0 1-18.09-4.287c7.347 9.637 18.949 15.857 32.007 15.857c22.16 0 40.132-17.918 40.21-40.05V11.571h34.643ZM99.966 113.58v-10.769a88.787 88.787 0 0 0-12.061-.818C39.355 101.993 0 141.327 0 189.845c0 30.419 15.467 57.227 38.971 72.996c-15.502-15.838-25.053-37.516-25.053-61.427c0-47.9 38.354-86.848 86.048-87.833Z" />
                </svg>
            </a> -->
            <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href="https://x.com/zat_baloot" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                    <path fill="#14171A"
                        d="M8 2H1l8.26 11.014L1.45 22H4.1l6.388-7.349L16 22h7l-8.608-11.478L21.8 2h-2.65l-5.986 6.886L8 2Zm9 18L5 4h2l12 16h-2Z" />
                </svg>
            </a>
            <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href="https://twitch.tv/zat_baloot" target="_blank">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 256 268">
                    <path fill="#5A3E85"
                        d="M17.458 0L0 46.556v186.201h63.983v34.934h34.931l34.898-34.934h52.36L256 162.954V0H17.458Zm23.259 23.263H232.73v128.029l-40.739 40.741H128L93.113 226.92v-34.886H40.717V23.263Zm64.008 116.405H128V69.844h-23.275v69.824Zm63.997 0h23.27V69.844h-23.27v69.824Z" />
                </svg>
            </a>

            <a class="mx-2 w-10 h-10 bg-gray-300 rounded-full flex justify-center items-center hover:-translate-y-1 duration-300 transition-all"
                href=" https://www.instagram.com/zat_baloot?igsh=OGQ5ZDc2ODk2ZA==" target="_blank">
                <Icon name="skill-icons:instagram" size="27px" />
            </a>

        </div>
    </footer>
</template>

<script setup lang="ts">
</script>

<style scoped></style>