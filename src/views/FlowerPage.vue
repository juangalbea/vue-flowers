<template>
  <div class="flowerPage">
      <h2>Hola</h2>
      <FlowerInfo />
  </div>
</template>

<script>
import FlowerInfo from '../components/FlowerInfo';
export default {
    name: "flowerPage",
    components: {
        FlowerInfo
    }
}
</script>

<style>
.flowerPage {
    background-color: red;
}
</style>