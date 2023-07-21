<script setup>
import {ref} from "vue"

const blue = ref('bg-blue-500 hover:bg-blue-700')
const gray = ref('bg-gray-500 hover:bg-gray-700')
const onPhoto = ref("//img.icons8.com/?size=512&id=12244&format=png")
const offPhoto = ref("//img.icons8.com/?size=512&id=75&format=png")

const b1Status = ref(1)
const b2Status = ref(1)
const b3Status = ref(0)

const t1Status = ref('On')
const t2Status = ref('On')
const t3Status = ref('Off')

function text1(param) {
    return param==1?t1Status.value='On':t1Status.value='Off'
}
function text2(param) {
    return param==1?t2Status.value='On':t2Status.value='Off'
}
function text3(param) {
    return param==1?t3Status.value='On':t3Status.value='Off'
}
</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button @click="b1Status = !b1Status" :class="b1Status==1?blue:gray" class=" text-white font-bold py-2 px-4 rounded">
                    Light 1 {{ text1(b1Status) }}
                </button>
                <button @click="b2Status = !b2Status" :class="b2Status==1?blue:gray" class=" text-white font-bold py-2 px-4 rounded">
                    Light 2 {{ text2(b2Status) }}
                </button>
                <button @click="b3Status = !b3Status" :class="b3Status==1?blue:gray" class=" text-white font-bold py-2 px-4 rounded">
                    Light 3 {{ text3(b3Status) }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" :src="b1Status==1?onPhoto:offPhoto" alt="" :v-show="b1Status==1">
                <img class="w-20" :src="b2Status==1?onPhoto:offPhoto" alt="" :v-show="b2Status==1">
                <img class="w-20" :src="b3Status==1?onPhoto:offPhoto" alt="" :v-show="b3Status==1">
            </div>
        </div>
    </section>
</template>

<style scoped></style>