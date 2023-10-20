<template>
  <div class="px-5 py-10 md:px-16 md:py-10 w-full">
    <div v-if="startup" class="flex flex-col md:justify-start md:align-start leading-3 overflow-hidden">
        <div class="overflow-hidden">
            <XyzTransition
                appear
                xyz="down-100% ease-in-out duration-8 delay-1"
            >
                <div class="overflow-hidden">
                    <p class="text-2xl text-center md:text-left md:text-5xl lg:text-6xl uppercase font-bold tracking-tighter">Bruce James Dela Cruz</p>
                </div>
            </XyzTransition>

        </div>
        <XyzTransition
            appear
            xyz="down-100% ease-in-out duration-8 delay-3"
        >
            <p class="text-2xl text-center md:text-left md:text-5xl lg:text-6xl uppercase font-bold tracking-tighter">Web Developer</p>
        </XyzTransition>
    </div>
    <div v-if="startup" class="flex flex-col text-center md:text-left md:font-normal md:text-2xl leading-snug mt-5 tracking-tight overflow-hidden">
        <XyzTransitionGroup
            appear
            xyz="fade-100% ease-in-out duration-8 delay-8"
        >
            <p key="1">I'm a Freelance Web Developer</p>
            <p key="2">with a versatile skill set that enables me</p>
            <p key="3">to serve as a Full Stack Developer.</p>
        </XyzTransitionGroup>
    </div>
    <div class="mt-5 flex justify-center md:justify-start overflow-hidden">
        <XyzTransition
            appear
            xyz="down-100% ease-in-out duration-5 delay-10"
        >
            <a href="mailto:jamesdelacruz5899@gmail.com">
                <button class="border px-5 py-3 rounded-full border-slate-800 tracking-tight font-normal md:text-xl hover:bg-slate-800 hover:text-slate-50 transition-all ease-linear duration-200">Let's connect</button>
            </a>
        </XyzTransition>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'; 

const startup = ref(false);

onMounted(() => {
    startup.value = true;
});

</script>

<style>

</style>