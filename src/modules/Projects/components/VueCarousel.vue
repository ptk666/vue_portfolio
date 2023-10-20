<template>
    <div v-if="scroll_show">
        <div class="my-5 w-full h-auto overflow-hidden">
            <XyzTransition
                appear
                xyz="down-100% ease-in-out duration-8 delay-5"
            >
                <div
                    class="bg-slate-800"
                    v-if="scroll_show"
                >
                    <swiper-container
                        :slides-per-view="2"
                        :space-between="10"
                        :centered-slides="true"
                        :breakpoints="breakpoints"
                    >
                        <swiper-slide v-for="project in vue_projects" :key="project.id">
                            <div class="card p-10 flex justify-center flex-col items-center text-center">
                                <a :href="project.link" target="_blank">
                                    <img class="rounded-lg shadow-xs shadow-slate-50" :src="project.img" alt="Vue Project Image">
                                </a>
                                <p class="text-slate-50 text-2xl text-center mt-5">{{ project.name }}</p>
                                <p class="text-center text-gray-400 mt-2">{{ project.description }}</p>
                            </div>
                        </swiper-slide>
                    </swiper-container>
                </div>
            </XyzTransition>
        </div>
        <div class="px-5 md:px-16 overflow-hidden">
            <XyzTransition
                appear
                xyz="fade-100% ease-in-out duration-8 delay-10"
            >
                <p v-show="scroll_show">(vue projects)</p>
            </XyzTransition>
        </div>
    </div>
    <div v-else class="h-96">

    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const scroll_show = ref(false);

const breakpoints = ref({
    768: {
        slidesPerView: 2
    },
    
    425: {
        slidesPerView: 1
    },

    375: {
        slidesPerView: 1
    },
    
    320: {
        slidesPerView: 1
    },
});

const vue_projects = ref([
    {
        id: 1,
        name: 'Vue Calculator',
        img: '@/images/14_vue_calculator.png',
        link: 'https://ptk666.github.io/vue_calculator/',
        description: 'An elegantly designed calculator inspired by the iOS calculator app. Built using Vue.js, it offers a user-friendly interface for performing various arithmetic operations with precision.'
    },
    {
        id: 2,
        name: 'Vue Checkout Form',
        img: '@/images/15_vue_checkout_form.png',
        link: 'https://ptk666.github.io/vue_checkout_form/',
        description: 'A Vue.js project focused on creating a seamless and user-friendly checkout form for online transactions. This project aims to enhance the user experience during the checkout process, making it easy and efficient.'
    }
]);

onMounted(() => {
    window.addEventListener('scroll', () => {
        const scrollHeight = window.scrollY;

        if(scrollHeight >= 1400) {
            scroll_show.value = true;
        }        
    })
})

</script>

<style>

</style>