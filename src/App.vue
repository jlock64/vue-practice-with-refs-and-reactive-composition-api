<template>
  <h2>My Course Goal</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->

  <!-- with separate refs  -->
  <!-- <h3 v-if="goalIsVisible">{{ courseGoal }}</h3> -->

  <!-- with ref object -->
  <h3 v-if="goals.goalIsVisible">{{ courseGoal }}</h3>

  <!-- with reactive object -->
  <!-- <h3 v-if="goals.goalIsVisible">{{ goals.courseGoal }}</h3> -->

  <!-- with options api -->
  <!-- <h3 v-if="goalIsVisible">{{ courseGoal }}</h3> -->

  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="toggleGoal">Toggle Goal</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
import { ref } from 'vue'
// import { reactive } from 'vue';
export default {
  setup() {
    // with separate refs
    // const courseGoal = 'Finish the course!';
    // const goalIsVisible = ref(false);

    // function toggleGoal() {
    //   goalIsVisible.value = !goalIsVisible.value;
    // }

    // return {
    //   courseGoal,
    //   goalIsVisible,
    //   toggleGoal
    // }

    // with ref object
    const goals = ref({
      courseGoal: 'Finish the course',
      goalIsVisible: false
    })

    function toggleGoal() {
      goals.value.goalIsVisible = !goals.value.goalIsVisible;
    }

    return {
      courseGoal: goals.value.courseGoal,
      goals,
      toggleGoal
    }

    // with reactive object
    // const goals = reactive({
    //   courseGoal: 'Finish the course',
    //   goalIsVisible: false
    // }) 

    // with reactive object
    // function toggleGoal() {
    //   goals.goalIsVisible = !goals.goalIsVisible;
    // }

    // with reactive object
    // return { goals: goals, toggleGoal: toggleGoal }
  }
}

// with options api
// export default {
//   data() {
//     return {
//       courseGoal: 'Finish the course!',
//       goalIsVisible: false
//     }
//   },
//   methods: {
//     toggleGoal() {
//       this.goalIsVisible = !this.goalIsVisible;
//     }
//   }
// }
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