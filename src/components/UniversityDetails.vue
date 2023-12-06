<template>
    <div class="card mt-3 border-primary">
      <div class="card-body">
        <h5 class="card-title" style="color: #7293ab;">{{ university['Name of the University '] }}</h5>
        <p class="card-text">Location: {{ university.Location }}</p>
        <p class="card-text">Established: {{ university.Date }}</p>
        <p class="card-text">Rank: {{ university.Rank }}</p>
        <p class="card-text">Type: {{ university['Type of University'] }}</p>
        <p class="card-text">Graduation Rate: {{ university['Graduation rate '] }}%</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'UniversityDetails',
    props: {
      university: Object
    }
  };
  </script>
  
  <style scoped>
    .card {
    margin-top: 30px;
    transition: box-shadow .3s ease;
    }
    .card {
        background-color: rgb(255, 252, 252); 
        border: 1px solid #e9e9e9; 
    }

    .card-body {
        color: #212529; 
    }

    .card-title {
        color: #007bff;
    }

    .card:hover {
        box-shadow: 0 0 10px rgba(0, 123, 255, .5); 
    }
  </style>
  