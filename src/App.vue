<template>
<div>
    <Navbar />
    <Heroes/>
</div>

</template>

<script>
import Heroes from './components/Heroes.vue'
import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Heroes,
    Navbar
  }
}
</script>

<style>

</style>
