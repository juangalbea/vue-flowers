<template>
  <div class="flower" v-bind:class="{'is-complete':flower.completed}">
      <input type="checkbox" v-on:change="markComplete">
    <h3>{{flower.name}}</h3>
    <p>{{flower.description}}</p>
    <img :src="require(`../assets/${flower.img}`)" />
    <button @click="$emit('del-flower', flower.id)" class="del">x</button>
    <router-link to="/flowerPage" >Info</router-link>
    <FlowerInfo v-bind:flower="flower" />
  </div>
</template>

<script>
import FlowerInfo from './FlowerInfo.vue';
export default {
  name: "Flower",
  components: {
        FlowerInfo
  },
  props: ["flower"],
  methods: {
      markComplete() {
          this.flower.completed = !this.flower.completed;
      }
  }
};
</script>

<style scoped>
.flower {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}

img {
    width: 300px;
}
</style>