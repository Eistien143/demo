<template>
  <div>
    <h3>See All Mobile</h3>
    <button v-if="!isShow" @click="seeAllMobiles">See All Mobiles</button>
    <button v-else @click="seeAllMobiles">Hide All Mobiles</button>
    <div v-if="isShow">
      <Card
        v-for="(mobile, i) in carts"
        :key="i"
        v-bind:title="mobile.name"
        v-bind:description="mobile.details"
        :ammount="mobile.price"
      ></Card>
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  components: { Card },

  data() {
    return {
      isShow: false,
      carts: [
        {
          name: "Samsung Mobile",
          details: "this is a samsung phone",
          price: "2000 Rs",
        },
        {
          name: "Jio Mobile",
          details: "this is a Jio phone",
          price: "90000",
        },
        {
          name: "Vivo Mobile",
          details: "this is a samsung phone",
          price: "7000",
        },
        {
          name: "Intex Mobile",
          details: "this is a intex phone",
          price: "70000",
        },
      ],
    };
  },
  methods: {
    seeAllMobiles() {
      this.isShow = !this.isShow;
      console.log(this.isShow);
    },
  },
};
</script>

<style></style>
