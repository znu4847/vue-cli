<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <button @click="resetName()">reset Name1</button>
    <button @click="resetNameFn()">reset Name2</button>
    <p>Many Details</p>
    <p>name : {{name}}</p>
    <p>age : {{age}}</p>
  </div>
</template>

<script>
import { eventBus } from "../../main";
export default {
  props: {
    name: String,
    age: Number,
    resetNameFn: Function
  },
  methods: {
    resetName() {
      this.name = "JJanu";
      this.$emit("nameWasReset", this.name);
    }
  },
  created() {
    eventBus.$on("ageWasEdited", newAge => {
      this.age = newAge;
    });
  }
};
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
