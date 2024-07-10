<template>
  <div class="max-w-5xl mx-auto text-center py-20">
    <h1 class="font-extrabold text-4xl">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'GreetingHeader',
  props: {
    msg: String
  }
}
</script>


<style scoped>

</style>
