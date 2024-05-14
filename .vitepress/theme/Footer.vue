<script setup lang="ts">
import { useData } from 'vitepress'

const { site, frontmatter } = useData()
</script>

<template>
    <div class="divider"></div>
    <footer>
        <div>&copy; 2024 - {{ site.title }}</div>
    </footer>
</template>

<style scoped>
footer {
    text-align: center;
    padding: 8px 0;
}

.divider {
    border-bottom: 1px solid #ccc;
}

</style>