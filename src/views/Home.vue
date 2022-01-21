<template>
  <div>
    <h3>this is home page</h3>
    <Card
      v-for="(mobile, i) in carts"
      :key="i"
      :title="mobile.name"
      :description="mobile.details"
      :ammount="mobile.price"
    ></Card>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  components: { Card },

  data() {
    return {
      carts: [
        {
          name: "Samsung Mobile",
          details: "this is a samsung phone",
          price: "2000 Rs",
        },
        {
          name: "Jio Mobile",
          details: "this is a Jio phone",
          price: 90000,
        },
        {
          name: "Samsung Mobile",
          details: "this is a samsung phone",
          price: 7000,
        },
      ],
    };
  },
};
</script>

<style></style>
