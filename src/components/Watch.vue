<template>
    <div>
        <!-- Option API -->
        <input type="text" placeholder="Name" v-model="name">
        <br>
        <!-- Composition API -->
        <input type="text" placeholder="First Name" v-model="firstName">
        <input type="text" placeholder="Last Name" v-model="lastName">

        <input type="text" placeholder="Reactive First Name" v-model="fName">
        <input type="text" placeholder="Reactive Last Name" v-model="lName">
        <input type="text" placeholder="Reactive Hero Name" v-model="options.heroName">
    </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue'
import _ from 'lodash'
export default {
    name: 'watch-vue',
    setup() {

        const state = reactive({
            fName: '',
            lName: '',
            options: {
                heroName: ''
            }
        })

        // all reactive state properties
        watch(() => {
            return { ...state }
        }, (newValue, oldValue) => {
            console.log('fName Old value', oldValue.fName);
            console.log('fName New value', newValue.fName);
            console.log('lName Old value', oldValue.lName);
            console.log('lName New value', newValue.lName);
        })

        // specific reactive state property
        watch(() => state.fName, (newValue, oldValue) => {
            console.log('specific fName Old value', oldValue);
            console.log('specific fName New value', newValue);
        })

        // options reactive state property
        watch(() => _.cloneDeep(state.options), (newValue, oldValue) => {
            console.log('specific fName Old value', oldValue);
            console.log('specific fName New value', newValue);
        }, {
            deep: true
        })

        const firstName = ref('')
        const lastName = ref('Wayne')

        watch([firstName, lastName], (newValues, oldValues) => {
            console.log('first name old value', oldValues[0]);
            console.log('first name new value', newValues[0]);

            console.log('last name old value', oldValues[1]);
            console.log('last name new value', newValues[1]);
        }, {
            immediate: true
        })

        return {
            firstName,
            lastName,
            ...toRefs(state)
        }
    },
    data() {
        return {
            name: ''
        }
    },
    watch: {
        name(newValue, oldValue) {
            console.log('Old value', oldValue);
            console.log('New value', newValue);
        }
    },
}
</script>

<style scoped></style>