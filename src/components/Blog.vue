<script setup>

defineProps({
  title: String,
  abstract: String,
  color: String,
  imageUrl: String,
})
</script>

<template>
  <div class="custom-component">
    <div class="title text-center" :style="{ 'background-color': color }">
      <img :src="imageUrl" alt="" class="container image ">
      <h2>{{ title }}</h2>
      <p class="abstract">
        {{ abstract }}
      </p>
    </div>
  </div>
</template>

<style scoped>
.title {
  font-size: 1.2em;
  font-family: Helvetica;
  font-style: normal;
}

.custom-component {
  background-color: v-bind(color);
}

.image {
  width: 100%;
  margin-top: 20px;
  margin-bottom: 20px;
  display: inline-block;
  display: flex;
}
</style>
