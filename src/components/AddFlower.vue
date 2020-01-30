<template>
  <div>
    <form @submit="addFlower">
      <input type="text" v-model="name" name="name" placeholder="Add Flower..." />
      <input type="submit" value="submit" class="btn" />
    </form>
  </div>
</template>

<script>
import uuid from 'uuid';
export default {
  name: "AddFlower",
  data() {
    return {
      name: ''
    }
  },
  methods: {
    addFlower(e) {
      e.preventDefault();
      const newFlower = {
        id: uuid.v4(),
        name: this.name,
        description: "Hello",
        img: "rose.jpg",
        completed: false
      }
      // Send to parent
      this.$emit('add-flower', newFlower);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>