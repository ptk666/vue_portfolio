<template>
    <div class="grid grid-cols-4 px-16 py-10 w-full items-center">
        <div class="title">
            <span class="font-bold text-2xl">天</span>
        </div>
        <ul class="btn invisible md:visible col-span-2 flex gap-4 tracking-tight">
            <li @click="scrollToProjects">Projects</li>
            <li @click="scrollToContacts">Contact</li>
        </ul>
        <ul class="icons flex justify-end gap-2">
            <li><a href="https://github.com/ptk666" target="_blank"><img src="../../../assets/images/github.png" height="20" width="20"></a></li>
            <li><a href="https://www.linkedin.com/in/brucejamesdelacruz/" target="_blank"><img src="../../../assets/images/linkedin.png" height="20" width="20"></a></li>
        </ul>
    </div>
</template>

<script setup>

    const scrollToProjects = () => {
        document.body.scrollTop = 600;
        document.documentElement.scrollTop = 600;
    }

    const scrollToContacts = () => {
        document.body.scrollTop = 2500;
        document.documentElement.scrollTop = 2500;
    }
</script>

<style>

</style>