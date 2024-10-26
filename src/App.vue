<script setup lang="ts">
    import { Authenticator } from '@aws-amplify/ui-vue';
    import '@aws-amplify/ui-vue/styles.css'
    import Todos from './components/Todos.vue'
</script>

<template>
    <main>
        <Authenticator>
            <template v-slot="{ user, signOut }">
                <h1>Hello {{ user?.signInDetails?.loginId }}! Your TODOs:</h1>
                <Todos />
                <button @click="signOut">Sign Out</button>
            </template>
        </Authenticator>
    </main>
</template>
