<template>
    <h1>Trackname</h1>
    <form @submit.prevent="go">
        <input type="text" v-model="token" placeholder="Trackname" />
        <input type="submit" value="go">
    </form>
</template>

<script lang="ts" setup>
const token = ref("")

function go() {
    navigateTo("/t/" + token.value)
}
</script>
