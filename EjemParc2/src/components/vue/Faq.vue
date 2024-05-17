<script setup>

    import { ref } from 'vue'

    const showThemeOne = ref(true)
    const showThemeTwo = ref(false)
    const showThemeThree = ref(false)
    const showThemeFour = ref(false)

    function showInfo (index) {

        if (index == 1) {

            showThemeOne.value = !showThemeOne.value
            showThemeTwo.value = false
            showThemeThree.value = false
            showThemeFour.value = false
        }
        if (index == 2) {

            showThemeOne.value = false
            showThemeTwo.value = !showThemeTwo.value
            showThemeThree.value = false
            showThemeFour.value = false
        }
        if (index == 3) {

            showThemeOne.value = false
            showThemeTwo.value = false
            showThemeThree.value = !showThemeThree.value
            showThemeFour.value = false
        }
        if (index == 4) {

            showThemeOne.value = false
            showThemeTwo.value = false
            showThemeThree.value = false
            showThemeFour.value = !showThemeFour.value
        }

    }

</script>

<template>

    <div class="bg-emerald-400 p-2 max-w-[600px] mx-auto mt-36 rounded-md font-medium  ">
        <div class="mb-2">

            <h1

            @click=" showInfo(1) " 
            class="bg-slate-600 text-white px-3 flex justify-between text-center rounded-xl py-2 hover:bg-slate-700 hover:cursor-pointer select-none"
            >

                Tema 1
                
                <span class="text-xl">
                    {{ showThemeOne ? '-' : '+' }}
                </span>

            </h1>

            <div 
            
            v-show="showThemeOne"
            class="bg-slate-300 flex justify-center py-1 mt-1 rounded-lg"
            >

                Texto del tema 1

            </div>
        </div>
        <div class="mb-2">
            
            <h1

            @click=" showInfo(2) " 
            class="bg-slate-600 text-white px-3 flex justify-between text-center rounded-xl py-2 hover:bg-slate-700 hover:cursor-pointer select-none"
            >

                Tema 2
                
                <span class="text-xl">

                    {{ showThemeTwo ? '-' : '+' }}

                </span>

            </h1>

            <div 
            v-show="showThemeTwo" 
            class="bg-slate-300 flex justify-center py-1 mt-1 rounded-lg">

                Texto del tema 2

            </div>

        </div>

        <div class="mb-2">

            <h1 
            @click=" showInfo(3) " 
            class="bg-slate-600 text-white px-3 flex justify-between text-center rounded-xl py-2 hover:bg-slate-700 hover:cursor-pointer select-none"
            >

                Tema 3

                <span class="text-xl">

                    {{ showThemeThree ? '-' : '+' }}

                </span>

            </h1>
            <div 
            v-show="showThemeThree" 
            class="bg-slate-300 flex justify-center py-1 mt-1 rounded-lg"
            >

                Texto del tema 3

            </div>

        </div>

        <div class="mb-2">

            <h1 
            @click=" showInfo(4) "  
            class="bg-slate-600 text-white px-3 flex justify-between text-center rounded-xl py-2 hover:bg-slate-700 hover:cursor-pointer select-none"
            >

                Tema 4

                <span class="text-xl">

                    {{ showThemeFour ? '-' : '+' }}

                </span>

            </h1>

            <div 
            v-show="showThemeFour" 
            class="bg-slate-300 flex justify-center py-1 mt-1 rounded-lg"
            >

                Texto del tema 4
                
            </div>

        </div>
    </div>

</template>