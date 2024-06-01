<template>
    <article class="prose dark:prose-invert max-w-none">
        <!-- prose-h1:text-2xl 拿掉 -->
        <ContentDoc path="/about" />
        <!-- <div>
            <button @click="enableCustomLayout">Update layout</button>
        </div> -->
    </article>
</template>
<script setup>
// definePageMeta <script setup> <script> 都會作用
// definePageMeta({
//     layout: 'another'
// })
// function enableCustomLayout() {
//     setPageLayout('another')
// }

// useHead({
//     title: 'About',
// })
</script>
