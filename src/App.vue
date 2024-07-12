<template>
  <GreetingHeader msg="Hello there!"/>
<RandomGif />

</template>

<script>
import GreetingHeader from './components/GreetingHeader.vue'
import RandomGif from "./components/RandomGif.vue";

export default {
  name: 'App',
  components: {
    GreetingHeader,
    RandomGif
  }
}
</script>

<style>

</style>

<!---->