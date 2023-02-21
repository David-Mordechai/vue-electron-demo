<template>
    <div>
        <!-- Options API -->
        <input type="text" placeholder="First Name" v-model="fName">
        <input type="text" placeholder="Last Name" v-model="lName">
        <h2>Options Fullname is {{ fullName }}</h2>

        <br>
        <!-- Composition API -->
        <input type="text" placeholder="First Name" v-model="refFirstName">
        <input type="text" placeholder="Last Name" v-model="refLastName">
        <h2>Composition Fullname is {{ refFullName }}</h2>

        <br>
        <!-- Composition API - Reactive -->
        <input type="text" placeholder="First Name" v-model="reactiveFirstName">
        <input type="text" placeholder="Last Name" v-model="reactiveLastname">
        <h2>Composition Reactive Fullname is {{ ReactiveFullName }}</h2>
    </div>
</template>

<script>
import { ref, computed, reactive, toRefs } from 'vue'
export default {
    name: 'computed-vue',
    setup() {
      const refFirstName = ref('')  
      const refLastName = ref('')
    
      const refFullName = computed(function(){
        return `${refFirstName.value} ${refLastName.value}`
      })

      const state = reactive({
        reactiveFirstName: '',
        reactiveLastname: ''
      })

      const ReactiveFullName = computed(function(){
        return `${state.reactiveFirstName} ${state.reactiveLastname}`
      })

      return{
        refFirstName,
        refLastName,
        refFullName,
        ...toRefs(state),
        ReactiveFullName
      }
    },
    data() {
        return {
            fName: '',
            lName: ''
        }
    },
    computed: {
        fullName() {
            return `${this.fName} ${this.lName}`
        }
    }
}
</script>

<style scoped></style>