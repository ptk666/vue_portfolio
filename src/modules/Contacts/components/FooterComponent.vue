<template>
    <div class="border border-gray-200 border-x-transparent border-b-transparent px-5 py-5 md:px-16 md:py-10">
        <div class="grid md:flex md:justify-between grid-cols-2">
            <ul class="icons flex justify-center md:justify-start gap-2">
                <li><a href="https://github.com/ptk666" target="_blank"><img src="../../../assets/images/github.png" height="20" width="20"></a></li>
                <li><a href="https://www.linkedin.com/in/brucejamesdelacruz/" target="_blank"><img src="../../../assets/images/linkedin.png" height="20" width="20"></a></li>
            </ul>
            <button @click="scrollTop">&uarr; back to top</button>
        </div>
    </div>
</template>

<script setup>

const scrollTop = () => {
    document.body.scrollTop = 0;
    document.documentElement.scrollTop = 0;
}
</script>

<style>

</style>