<template>
  <div>
    <the-header> </the-header>
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>

    <manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
    <component :is="selectedComponent"></component>
    <!-- <badge-list></badge-list>
   
    <user-info></user-info>
    <course-goals></course-goals> -->
  </div>
</template>

<script>
// Local components
import TheHeader from "./components/TheHeader.vue";
// import BadgeList from "./components/BadgeList.vue";
// import UserInfo from "./components/UserInfo.vue";
// import CourseGoal from "./components/CourseGoals.vue";
import ManageGoals from "./components/ManageGoals.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
export default {
  components: {
    "the-header": TheHeader,

    "manage-goals": ManageGoals,
    "active-goals": ActiveGoals,
  },
  data() {
    return {
      selectedComponent: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
