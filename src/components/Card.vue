<template>
  <div>
    <div class="card">
      <h1>{{ title }}</h1>
      <p>
        {{ description }}
      </p>
      <h3>{{ ammount }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: { title: String, description: String, ammount: Number },
};
</script>

<style>
.card {
  width: 300px;
  height: 200px;
  background-color: rgb(150, 150, 150);
}
</style>
