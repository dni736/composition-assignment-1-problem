<template>
  <h2>My Internship Goals</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
  <div id="goals" v-show="visible">
    <h3>{{ goalOne }}</h3>
    <h3>{{ goalTwo }}</h3>
    <h3>{{ goalThree }}</h3>
  </div>
  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="toggle">{{ caption }}</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
import { ref, reactive } from 'vue';
export default {
  setup() {
    var visible = ref(true);
    var caption = ref('Hide');
    const goal1 = ref('Vue');
    const internshipGoalRefObj = ref({
      goal2: 'Nuxt',
    });
    const internshipGoalReactObj = reactive({
      goal3: 'Magento',
    });
    function hideOrShow() {
      visible.value = !visible.value;
      caption.value == 'Hide'
        ? (caption.value = 'Show')
        : (caption.value = 'Hide');
    }
    return {
      visible,
      caption,
      goalOne: goal1,
      goalTwo: internshipGoalRefObj.value.goal2,
      goalThree: internshipGoalReactObj.goal3,
      toggle: hideOrShow,
    };
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
