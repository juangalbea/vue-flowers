<template>
  <div id="app">

    <AddFlower v-on:add-flower="addFlower" />
    <Flowers v-bind:flowers="flowers" v-on:del-flower="deleteFlower"/>
  </div>
</template>

<script>
import Flowers from '../components/Flowers';
import AddFlower from '../components/AddFlower';

export default {
  name: "home",
  components: {
    Flowers,
    AddFlower
  },
  data() {
    return {
      flowers: [
        {
          id: 1,
          name: "Rose",
          description:
            "A rose is a woody perennial flowering plant of the genus Rosa, in the family Rosaceae, or the flower it bears.",
          img: "rose.jpg",
          completed: false
        },
        {
          id: 2,
          name: "Peony",
          description:
            "The peony or paeony[2][3] is a flowering plant in the genus Paeonia, the only genus in the family Paeoniaceae.",
          img: "peony.jpg",
          completed: false
        },
        {
          id: 3,
          name: "Dahlia",
          description:
            "Dahlia (UK: /ˈdeɪliə/ or US: /ˈdeɪljə, ˈdɑːl-, ˈdæljə/)[3] is a genus of bushy, tuberous, herbaceous perennial plants",
          img: "dahlia.jpg",
          completed: true
        }
      ]
    };
  },
  methods: {
    deleteFlower(id) {
      this.flowers = this.flowers.filter(flower => flower.id != id);
    },
    addFlower(newFlower) {
      this.flowers = [...this.flowers, newFlower];
    }
  }
};
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
