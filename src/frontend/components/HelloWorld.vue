<template>
    <div class="icons">
        <img alt="Vite logo" width="120" src="../assets/vite.svg" />
        <img alt="Vue logo" width="120" src="../assets/logo.png" />
        <img alt="Electron logo" width="120" src="../assets/electron.png" />
        <img alt="TS logo" width="120" src="../assets/ts.png" />
    </div>

    <h1>{{ msg }}</h1>

    <p>See <code>README.md</code> for more information.</p>
    <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>

    <div id="examples">
        <button type="button" @click="count++">count is: {{ count }}</button>
        <button type="button" @click="openFile()">Open a File</button>
        <p v-if="filePath">File Path: {{ filePath }}</p>
    </div>

    <hr>

    <p>
        <router-link to="/home" class="routerlink">Go to Home</router-link>
        <router-link to="/about" class="routerlink">Go to About</router-link>
    </p>

    <router-view />
</template>

<script setup lang="ts">
import { ref } from "vue";
import { storeToRefs } from "pinia";
import { useCounterStore } from "../store/counter";
defineProps<{ msg: string }>();

const { count } = storeToRefs(useCounterStore());
const filePath = ref(null);
const openFile = async () => {
    // @ts-ignore
    filePath.value = await window.electronAPI.openFile();
};
</script>

<style lang="scss" scoped>
a {
    color: #42b983;
}

hr {
    margin-block: 2em;
}

.icons {
    display: flex;
    justify-content: center;
    gap: 2em;

    img {
        width: 5em;
    }
}

label {
    margin: 0 0.5em;
    font-weight: bold;
}

code {
    background-color: #eee;
    padding: 2px 4px;
    border-radius: 4px;
    color: #304455;
}
.routerlink {
    margin: 0 10px;
}
#examples {
    margin: 10px;
    display: flex;
    justify-content: center;
    gap: 1em;
}
</style>
