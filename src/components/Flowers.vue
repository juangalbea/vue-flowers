<template>
  <div>
      <div v-bind:key="flower.id" v-for="flower in flowers">
          <Flower v-bind:flower="flower" v-on:del-flower="$emit('del-flower', flower.id)" />
      </div>
  </div>
</template>

<script>
import Flower from './Flower.vue';
export default {
    name: "Flowers",
    components: {
        Flower
    },
    props: ["flowers"]
}
</script>


<style scoped>

</style>