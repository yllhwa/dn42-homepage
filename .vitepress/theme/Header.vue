<script setup lang="ts">
import { useData } from 'vitepress'

const { site, frontmatter } = useData()
</script>

<template>
    <header>
        <div class="logo-text">
            <img src="/logo.png" class="header-logo" alt="logo" />
            <div class="logo-title">
                <span class="logo-title-main">{{ site.title }}</span>
                <span class="logo-title-desc">{{ site.description }}</span>
            </div>
        </div>
    </header>
    <div>
        <nav>
            <ul>
                <li><a href="/">Home</a></li>
                <li><a href="/peering.html">Peering</a></li>
                <li><a href="/services.html">Services</a></li>
                <li><a href="/lg.html">Looking Glass</a></li>
                <li><a href="/about.html">About</a></li>
            </ul>
        </nav>
    </div>
    <div class="divider"></div>
</template>

<style scoped>
header {
    display: flex;
    overflow: hidden;
    padding: 20px 50px 0 50px;
}

.logo-text {
    display: flex;
    align-items: center;
}

.logo-title {
    display: flex;
    flex-direction: column;
}

.logo-title-main {
    font-size: 24px;
    font-weight: bold;
}

.logo-title-desc {
    font-size: 18px;
    color: #666;
}

.header-logo {
    height: 60px;
    width: 60px;
    margin-right: 5px;
}

nav {
    display: flex;
    padding: 5px 10px;
}

ul {
    display: flex;
    gap: 16px;
    margin: 8px 0;
    list-style-type: none;
    flex-wrap: wrap;
}

nav a {
    text-decoration: none;
    color: #333;
    font-size: 18px;
    white-space: nowrap;
}

nav a:hover {
    color: #666;
}

.divider {
    border-bottom: 1px solid #ccc;
}

</style>