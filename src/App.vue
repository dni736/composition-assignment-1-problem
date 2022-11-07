<template>
  <h2>My Internship Goals</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
  <div id="goals" v-show="toggle">
    <h3 :key="id" v-for="(goal, id) in goals">{{ goal }}</h3>
  </div>
  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="hideOrShow">{{ caption }}</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
export default {
  data() {
    return {
      goals: ['Vue', 'Nuxt', 'Magento'],
      toggle: true,
      caption: 'Hide',
    };
  },
  methods: {
    hideOrShow() {
      this.toggle = !this.toggle;
      this.caption == 'Hide'
        ? (this.caption = 'Show')
        : (this.caption = 'Hide');
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 3rem;
  text-align: center;
}
</style>
