<template>
    <!-- <p class="mb-10">Take a look at my GitHub projects!</p> -->
    <div class="not-prose">
        <!-- class="not-prose" 不想被汙染 獨立組件 -->
        <section v-if="pending">Loading...</section>
        <section v-else-if="error">Something went wrong... Try again!</section>
        <!-- 不會看到 loading 因為 在server 執行了 -->
        <section v-else>
            <ul class="grid grid-cols-1 gap-4">
                <li v-for="repository in repos" :key="repository.id"
                    class="border border-gray-200 dark:border-gray-800 rounded-sm p-4 hover:bg-gray-200 dark:hover:bg-gray-800 font-mono">
                    <a :href="repository.html_url" target="_blank">
                        <div class="flex items-center justify-between text-sm">
                            <div class="font-semibold">{{ repository.name }}</div>
                            <div>{{ repository.stargazers_count }} ★</div>
                        </div>
                        <p class="text-sm">
                            {{ repository.description }}
                        </p>
                    </a>
                </li>
            </ul>
        </section>
    </div>
</template>
<script setup>
// console.log("request:", await $fetch( 'https://api.github.com/users/leo41271/repos'));// vscode 終端 和網頁console 都會顯示
// console.log("request:", await useFetch( 'https://api.github.com/users/leo41271/repos')); // 其一 只顯示在網頁
const { error, pending, data } = await useFetch('https://api.github.com/users/leo41271/repos');
const repos = computed(
    () => data.value.filter(repo => repo.description)
        .sort((a, b) => b.stargazers_count - a.stargazers_count)
)
// console.log("pending", pending);
// console.log("data", data);
// console.log("error", error);
</script>