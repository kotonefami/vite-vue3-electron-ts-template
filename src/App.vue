<script setup lang="ts">
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
    <HelloWorld msg="Vite + Vue 3 + Electron + TypeScript + vue-router + pinia" />
</template>

<style lang="scss">
:root {
    font-family: 'Noto Sans JP', Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
    font-weight: 400;

    color-scheme: light dark;
    text-rendering: optimizeLegibility;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    -webkit-text-size-adjust: 100%;

    color: rgba(255, 255, 255, 0.87);
    background-color: #242424;
}
body {
    margin: 3em;
    text-align: center;
}
a {
    color: #646cff;
    &:hover {
        color: #535bf2;
        @media (prefers-color-scheme: light) {
            color: #747bff;
        }
    }

    text-decoration: inherit;
    font-weight: 500;
}
button {
    border-radius: 8px;
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 500;
    font-family: inherit;
    cursor: pointer;
    transition: border-color 0.25s;

    background-color: #1a1a1a;
    @media (prefers-color-scheme: light) {
        background-color: #f9f9f9;
    }

    &:hover {
        border-color: #646cff;
    }
    &:focus, &:focus-visible {
        outline: 4px auto -webkit-focus-ring-color;
    }
}
</style>
