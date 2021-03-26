<template>
  <div>
    <nav class="navbar navbar-light bg-background">
      <span class="navbar-brand mb-0 text-white h1">Logo</span>
      <div class="text-right">
        <span class="text-white h6 mr-5"><span><img style="width: 40px; height: auto" class="mr-3" src="../assets/Ellipse 9.png"></span>Samsul Arifin</span>
        <b-icon icon="gear" class="text-white" style="cursor: pointer" @click="clickAction"/>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  methods: {
    clickAction () {
      alert('This feature will be added')
    }
  }
}
</script>

<style scoped>
  .bg-background {
    background-color: #0442D0;
  }
</style>
