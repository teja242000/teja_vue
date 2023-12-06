<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark">
      <div class="container-fluid justify-content-center">
        <a class="navbar-brand mx-auto" style="color: #7293ab; size: 20px;">Top Universities</a>
      </div>
    </nav>
    <div class="container mt-4">
      <UniversityList @onSelect="selectUniversity" :selectedUniversity="selectedUniversity" />
      <UniversityDetails v-if="selectedUniversity" :university="selectedUniversity" />
    </div>
  </div>
</template>

<script>
import UniversityList from './components/UniversityList.vue';
import UniversityDetails from './components/UniversityDetails.vue';

export default {
  name: 'App',
  components: {
    UniversityList,
    UniversityDetails
  },
  data() {
    return {
      selectedUniversity: null,
    };
  },
  methods: {
    selectUniversity(university) {
      this.selectedUniversity = university;
    }
  }
};
</script>
<style>
body{
  background-color: #7293ab !important;
}
.navbar{
  background-color: rgb(255, 255, 255);
}
</style>
