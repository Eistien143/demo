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
  props: { title: String, description: String, ammount: String },
};
</script>

<style>
.card {
  width: 100%;
  height: 200px;
  background-color: rgb(151, 209, 248);
  margin-top: 10px;
}
</style>
