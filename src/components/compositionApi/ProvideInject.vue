<template>
    <div>
        <h3>Parent Component {{ name }}</h3>
        <h3>Parent Component count {{ count }}</h3>
        <h3>Parent Component hero {{ firstName }} {{ lastName }}</h3>

        <button @click="incrementCount">Increment Count</button>

        <ChildA />
    </div>
</template>

<script>
import ChildA from "./ChildA.vue";
import { provide, ref, reactive, toRefs } from 'vue'
export default {
    name: "provide-inject",
    components: { ChildA },
    setup() {
        provide('c_userName', 'Bruce')

        const count = ref(0)

        function incrementCount() {
            count.value++
        }

        const state = reactive({
            firstName: 'Bruce',
            lastName: 'Wayne'
        })

        provide('c_count', count)
        provide('incrementCount', incrementCount)
        provide('c_hero', state)

        return {
            count,
            ...toRefs(state),
            incrementCount
        }
    },
    data() {
        return {
            name: "David"
        };
    },
    provide() {
        return {
            userName: this.name
        };
    },
}
</script>

<style scoped></style>