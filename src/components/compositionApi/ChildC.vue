<template>
    <div>
        <h2>Child Component C</h2>
        <h3>Child Component C - {{ userName }}</h3>
        <h3>Child Component C composition userName - {{ childUserName }}</h3>

        <h3>Child Component C count {{ childCount }}</h3>
        <h3>Child Component C hero {{ firstName }} {{ lastName }}</h3>

        <button @click="incrementCount">Increment count from child</button>
    </div>
</template>

<script>
import { inject, toRefs } from 'vue'
export default {
    name: "child-c",
    inject: ['userName'],
    setup() {
        const childUserName = inject('c_userName','Defult userName')

        const childCount = inject('c_count', 0)
        const incrementCount = inject('incrementCount')
        const childHero = inject('c_hero', {})

        return{
            childUserName,
            childCount,
            ...toRefs(childHero),
            incrementCount,
        }
    }
}
</script>

<style scoped></style>