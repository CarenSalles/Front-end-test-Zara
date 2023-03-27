<script setup>
const props = defineProps({
  title:{
    type: Number,
    default: null,
  },
  name: {
    type: String,
    default: null,
  },
  image:{
    type: String,
    default: null,
  },
  artist:{
    type: String,
    default: null,
  },

});
</script>

<template>
  <div class="card-container">
    <img :src="props.image" :alt="props.image" />
  <div class="card-container__text">
    <h2>{{ props.name }}</h2>
    <p>{{ props.artist }}</p>
  </div>
  </div>
    
</template>

<style lang="scss" scoped >

.card-container{
  width: 30%;
  height: 30vh;
  background-color: red;
}

</style>

