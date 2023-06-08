<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" v-bind:key="job.id">
    <router-link v-bind:to="{ name: 'job_details', params: { id: job.id } }" >
      <h2>{{ job.title }}</h2>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        { title: 'Ninja UX Designer', id: 1, details: 'Lorem' },
        { title: 'Ninja Web Developer', id: 2, details: 'Lorem' },
        { title: 'Ninja Vue Developer', id: 3, details: 'Lorem' }
      ]
    }
  }
}
</script>

<style>

</style>