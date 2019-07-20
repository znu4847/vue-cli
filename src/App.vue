<template>
  <div class="container-fluid">
    <!-- Sidebar -->
    <div class="w3-sidebar w3-light-grey w3-bar-block" style="width:200px">
      <h3 class="w3-bar-item">Menu</h3>
      <a href="#" class="w3-bar-item w3-button" @click="currentContent = 'Section6'">Section 6</a>
      <a href="#" class="w3-bar-item w3-button" @click="currentContent = 'Section8'">Section 8</a>
    </div>

    <!-- Page Content -->
    <div style="margin-left:200px">
      <div class="w3-container w3-teal">
        <h2>{{title}}</h2>
      </div>
      <component :is="currentContent" />
    </div>
  </div>
</template>

<script>
import Section6 from "./section6/Section6.vue";
import Section8 from "./section8/Section8.vue";
export default {
  data: () => ({
    currentContent: "Section8",
    pageInfo: {
      Section6:
        "Moving to at 'Real' Development Workflow with Webpack and Vue CLI",
      Section8: "Communicating between Components"
    }
  }),
  computed: {
    title() {
      return this.pageInfo[this.currentContent];
    }
  },
  components: {
    Section6,
    Section8
  }
};
</script>

<style scope>
</style>
