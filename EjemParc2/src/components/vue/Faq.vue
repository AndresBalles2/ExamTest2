<script setup>
    import { ref } from 'vue'
    const data = [ 'Tema 1', 'Tema 2', 'Tema 3', 'Tema 4' ]
    const selectedIndex = ref(0)
    function showInfo (i) {
        if (i == selectedIndex.value){
            selectedIndex.value = -1
        } else {
            selectedIndex.value = i
        }
    }
</script>
<template>
    <div 
    class="bg-emerald-400 p-2 max-w-[600px] mx-auto mt-36 rounded-md">
        <div v-for="(theme, i) in data" :key = "i" class="mb-2">
            <h1 @click=" showInfo(i) " class="bg-slate-600 text-white font-medium px-3 flex justify-between text-center rounded-xl py-2 hover:cursor-pointer select-none"
            :class="{' bg-slate-900 ' : selectedIndex == i}">
                {{ theme }}
                <span class="text-xl">
                    {{ selectedIndex == i ? '-' : '+' }}
                </span>
            </h1>
            <div v-show="selectedIndex == i" class="bg-slate-300 flex justify-center py-1 mt-1 rounded-lg h-40">
                Texto del tema 1
            </div>
        </div>
    </div>
</template>