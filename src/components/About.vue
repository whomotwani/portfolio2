<template>
    <section>
        <h1 class="text-5xl">{{ data.name }}</h1>
        <h3 class="text-2xl">{{ data.designation }}</h3>

        <p class="text-xl mt-5">{{ data.comment }}</p>
        <a class="btn btn-xs mr-2" v-for="i in data.social" :key="i.name" :href="i.url" target="_blank">
            {{ i.name }}
        </a>
    </section>
</template>
<script setup>
import data from '../data.json'
</script>