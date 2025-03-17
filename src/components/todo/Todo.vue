<script setup lang="ts">

defineProps<{ id: number,content: string }>()

</script>

<template>
    <span class="text-2xl cursor-pointer" @click="$emit('click-detail',id)">{{ content }}</span>
    <button @click="$emit('click-update',id)" type="button" class="focus:outline-none text-white bg-yellow-400 hover:bg-yellow-500 focus:ring-4 focus:ring-yellow-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:focus:ring-yellow-900">Edit</button>
    <button @click="$emit('click-delete',id)" type="button" class="focus:outline-none text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900">Delete</button>
</template>

<style scoped>
span{
    margin-right: 10px;
}
</style>
