<template>
  <div>
    <div v-for="university in universities" :key="university._id"
         :class="{'list-group-item': true, 'list-group-item-action': true, 'active': selectedUniversity === university}"
         @click="selectUniversity(university)">
      {{ university['Name of the University '] }}
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'UniversityList',
  props: {
    selectedUniversity: Object
  },
  data() {
    return {
      universities: []
    };
  },
  created() {
    this.fetchUniversities();
  },
  methods: {
    async fetchUniversities() {
      try {
        const response = await axios.get('https://teja-moparthi.netlify.app/api');
        this.universities = response.data['Top Universities in the world'];
      } catch (error) {
        console.error(error);
      }
    },
    selectUniversity(university) {
      this.$emit('onSelect', university);
    }
  }
};
</script>

<style scoped>
.list-group-item {
  background-color: #f8f9fa; 
  color: #495057; 
  border: 1px solid #e9ecef; 
  cursor: pointer;
  transition: background-color 0.2s, color 0.2s;
}

.list-group-item:hover, .list-group-item.active {
  background-color: #7293ab; 
  color: rgb(255, 255, 255);
  border-color: rgb(255, 255, 255);
}
</style>
