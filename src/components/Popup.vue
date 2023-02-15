<template>
  <div>
    <h2>This is a popup</h2>
    <input type="text" v-model="name">
    <button @click="$emit('close', name)">Close popup</button>
  </div>
</template>

<script>
export default {
  name: "popup-vue",
  emits: {
    close: (name) => {
        if(name !== ''){
            console.log('debugging true');
            return true;
        }
        else{
            console.log('debugging false');
            return false;
        }
    }
  },
  data() {
    return {
        name: ''
    }
  },
};
</script>

<style scoped></style>
