<template>
  <div id="app">
    <Navbar class="sticky-top"/>
    <Home/>
  </div>
</template>

<script>
import Home from './components/Home'
import Navbar from './components/Navbar'

export default {
  components: {
    Home,
    Navbar
  }
}
</script>
