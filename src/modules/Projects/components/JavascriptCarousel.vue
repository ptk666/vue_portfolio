<template>
    <div v-if="scroll_show">
        <div class="px-5 md:px-16 w-full overflow-hidden">
            <XyzTransition
                :appear="scroll_show"
                xyz="down-100% ease-in-out duration-8 delay-10"
            >
                <div v-if="scroll_show" class="flex justify-between">
                    <p>(repo showcase)</p>
                    <p>discover &darr;</p>
                </div>
            </XyzTransition>
        </div>
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
                        :slides-per-view="3"
                        :space-between="10"
                        :centered-slides="true"
                        :breakpoints="breakpoints"
                    >
                        <swiper-slide v-for="project in js_projects" class="text-slate-50" :key="project.id">
                            <div class="card p-10 flex justify-center flex-col items-center text-center">
                                <a :href="project.link" target="_blank">
                                    <img class="rounded-lg shadow-xs shadow-slate-50" :src="project.img" alt="Project Image" width="300">
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
                <p v-show="scroll_show">(js projects)</p>
            </XyzTransition>
        </div>
    </div>
    <div
        v-else
        class="h-96"
    >
        
    </div>
</template>

<script setup>
import { register } from 'swiper/element/bundle'
import { ref, onMounted } from 'vue'

register();

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

const js_projects = ref([
    {
        id: 1,
        name: 'Color Flipper',
        // img: '/images/1_color_flipper.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/1_color_flipper.png',
        link: 'https://ptk666.github.io/color_flipper/',
        description: 'A small project for showcasing the execution of a gacha/random selection through colors.'
    },
    {
        id: 2,
        name: 'Counter',
        // img: '/images/2_counter.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/2_counter.png',
        link: 'https://ptk666.github.io/counter/',
        description: 'A small project for showcasing how to manipulate the Document Object Model (DOM) through numbers.'
    },
    {
        id: 3,
        name: 'Testimonial Carousel',
        // img: '/images/3_testimonial_carousel.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/3_testimonial_carousel.png',
        link: 'https://ptk666.github.io/testimonial_carousel/',
        description: 'A small project for displaying testimonials in a carousel format.'
    },
    {
        id: 4,
        name: 'Responsive Navbar',
        // img: '/images/4_responsive_navbar.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/4_responsive_navbar.png',
        link: 'https://ptk666.github.io/responsive_navbar/',
        description: 'A project featuring a responsive navigation bar, adapting to different screen sizes.'
    },
    {
        id: 5,
        name: 'Responsive Sidebar',
        // img: '/images/5_responsive_sidebar.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/5_responsive_sidebar.png',
        link: 'https://ptk666.github.io/responsive_sidebar/',
        description: 'A project with a responsive sidebar layout suitable for various screen sizes.'
    },
    {
        id: 6,
        name: 'Modals',
        // img: '/images/6_modal.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/6_modal.png',
        link: 'https://ptk666.github.io/modal/',
        description: 'A project for creating and managing modal pop-ups on a web page.'
    },
    {
        id: 7,
        name: 'FAQs',
        // img: '/images/7_faqs.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/7_faqs.png',
        link: 'https://ptk666.github.io/faqs/',
        description: 'A project for displaying frequently asked questions with answers.'
    },
    {
        id: 8,
        name: 'Restaurant Menu',
        // img: '/images/8_restaurant_menu.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/8_restaurant_menu.png',
        link: 'https://ptk666.github.io/restaurant_menu/',
        description: 'A project that showcases a restaurant menu with various food items.'
    },
    {
        id: 9,
        name: 'Video Player',
        // img: '/images/9_video_player.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/9_video_player.png',        
        link: 'https://ptk666.github.io/video_player/',
        description: 'A project for playing and controlling videos on a web page.'
    },
    {
        id: 10,
        name: 'Scroll',
        // img: '/images/10_scroll.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/10_scroll.png',        
        link: 'https://ptk666.github.io/scroll/',
        description: 'A project related to scrolling functionality on a web page.'
    },
    {
        id: 11,
        name: 'Countdown Clock',
        // img: '/images/11_countdown_timer.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/11_countdown_timer.png',     
        link: 'https://ptk666.github.io/countdown_clock/',
        description: 'A project featuring a countdown clock or timer for New Year'
    },
    {
        id: 12,
        name: 'Steamed Dipsum',
        // img: '/images/12_steamed_dipsum.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/12_steamed_dipsum.png',     
        link: 'https://ptk666.github.io/steamed_dipsum/',
        description: 'A project showcasing a Lorem Ipsum version, possibly used for placeholder text or design mockups.'
    },
    {
        id: 13,
        name: 'Grocery List',
        // img: '/images/13_grocery_list.png',
        img: 'https://raw.githubusercontent.com/ptk666/vue_portfolio/master/public/images/13_grocery_list.png',     
        link: 'https://ptk666.github.io/grocery_list/',
        description: 'A CRUD (Create, Read, Update, Delete) project for efficiently managing and organizing your grocery shopping list.'
    }
]);

onMounted(() => {
    window.addEventListener('scroll', () => {
        const scrollHeight = window.scrollY;

        if(scrollHeight >= 450) {
            scroll_show.value = true;
        }
    });
})


</script>

<style scoped>
</style>