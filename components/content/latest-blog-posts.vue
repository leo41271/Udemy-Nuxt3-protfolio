<template>
    <BlogPosts v-slot="{ posts }" :limit="limit">
        <div v-for="(post,id) in posts" :key="id">
            <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
        </div>
    </BlogPosts>
</template>

<script setup>
defineProps({
    limit: {
        type: Number,
        default: null
    }
})
</script>