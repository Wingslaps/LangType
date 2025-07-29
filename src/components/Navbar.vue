<script setup lang="ts">
    import SearchBar from '@/components/SearchBar.vue'
</script>

<template>
    <div class="flex flex-rows-3 justify-center bg-[rgb(15,15,15)] w-full h-14">
        <div class="w-1/4 h-full flex items-center pl-8">
            <p class="text-xl"><span class="text-blue-300">Lang</span><span class="text-white">Type</span></p>
        </div>
        <div class="w-1/2 h-full flex justify-center items-center">
            <SearchBar />
        </div>
        <div class="w-1/4 h-full flex justify-end items-center gap-4 pr-8">
            <div class="rounded-lg text-white h-8 w-22 text-md flex justify-center items-center">Log in</div>
            <div class="bg-blue-300 rounded-lg h-8 w-22 text-md flex justify-center items-center"><strong>Sign up</strong></div>
        </div>
    </div>
</template>
