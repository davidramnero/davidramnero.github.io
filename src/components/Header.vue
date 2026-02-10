<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
  </div>
</template>

<style scoped>
h1 {
  position: relative;
  top: -10px;
}


.greetings h1 {
  text-align: center;
}


@media (min-width: 300px) {
  .greetings {
    max-width: 220px;
  }
    .h1 {
    font-weight: 400;
    font-size: 0.8rem;
  }
}

@media (min-width: 1024px) {
  .greetings h1 {
    text-align: left;
  }
  .h1 {
    font-weight: 500;
    font-size: 2.6rem;
  }
}
</style>
