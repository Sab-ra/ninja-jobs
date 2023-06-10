<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" v-bind:key="job.id" class="job">
    <router-link v-bind:to="{ name: 'job_details', params: { id: job.id } }" >
      <h2>{{ job.title }}</h2>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: []
    }
  },
  mounted() {
    fetch( 'http://localhost:3000/jobs' )
      .then( response => response.json() )
      .then( data => this.jobs = data )
      .catch( err => console.log( err.message ))
  }
}
</script>

<style>
  .job h2 {
    background: #f4f4f4;
    padding: 16px;
    border-radius: 8px;
    margin: 10px auto;
    max-width: 600px;
    cursor: pointer;
    color: #444;
  }
  .job h2:hover {
    background: #ddd;
  }
  .job a {
    text-decoration: none;
  }
</style>