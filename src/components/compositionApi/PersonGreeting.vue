<template>
    <div>Hello {{ firstName }} {{ lastName }}</div>
    <div>Hello {{ fullName }}</div>
    <button @click="sendEvent">Call Herros</button>
</template>

<script>
import { computed } from 'vue'
export default {
    name: 'person-greeting',
    props: ['firstName', 'lastName'],

    setup(props, context) {
        const fullName = computed(() => {
            return `${props.firstName} ${props.lastName}`
        })

        function sendEvent() {
            context.emit('callHeroes', fullName.value)
        }

        return {
            fullName,
            sendEvent,
        }
    },
    emits: ['callHeroes']
}
</script>

<style scoped></style>