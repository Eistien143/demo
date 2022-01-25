<template>
  <v-container>
    <h3>See All Mobile</h3>
    <v-btn v-if="!isShow" @click="seeAllMobiles" class="ma-2" color="primary">See All Mobiles</v-btn>
    <v-btn v-else @click="seeAllMobiles" class="ma-2" color="primary">Hide All Mobiles</v-btn>
    <v-btn @click="increaseCount" class="ma-2" color="primary">increase count</v-btn>
    <h3>{{count}}</h3>
    <div v-if="isShow">
      <!-- <Card
        v-for="(mobile, i) in carts"
        :key="i"
        v-bind:title="mobile.name"
        v-bind:description="mobile.details"
        :ammount="mobile.price"
      ></Card> -->
      <v-row>
        <v-col cols="12" sm="4" v-for="(mobile, i) in carts"
        :key="i" class="mt-2">
       <v-card     
       class="mx-auto"
       max-width="344">
       <v-img
         :src="mobile.img"
         height="200px" contain></v-img>
     <v-card-title>
     {{mobile.name}}
    </v-card-title>

    <v-card-subtitle>
      {{mobile.details}}
    </v-card-subtitle>
    <span>

    <h3 class="pa-3"> Price - {{mobile.price}}</h3>
    
    <v-btn class="ma-3" color="warning" >Add to cart</v-btn>
    </span>
  </v-card>
  </v-col>
  </v-row>
    </div>

  <v-btn icon><v-icon>mdi-twitter</v-icon></v-btn>

  </v-container>
</template>

<script>
// import Card from "@/components/Card.vue";

export default {
  name:'Home',
  // components: { Card },

  data() {
    return {
      isShow: true,
      count : 0,
      carts: [
        {
          img:"https://images.samsung.com/is/image/samsung/p6pim/in/sm-g990elgginu/gallery/in-galaxy-s21-fe-g990-sm-g990elgginu-thumb-530606487?$160_160_PNG$",
          name: "Samsung Mobile",
          details: "this is a samsung phone",
          price: "2000 Rs",
        },
        {
          img:"https://www.jio.com/1-compact-design.jpg",
          name: "Jio Mobile",
          details: "this is a Jio phone",
          price: "90000 Rs",
        },
        {
          img:"https://m.media-amazon.com/images/I/61gRGQe8jjL._SL1200_.jpg",
          name: "Vivo Mobile",
          details: "this is a samsung phone",
          price: "7000 Rs",
        },
        {
          img:"data:image/jpeg;base64,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",
          name: "Intex Mobile",
          details: "this is a intex phone",
          price: "70000 Rs",
        },
      ],
    };
  },
  methods: {
    seeAllMobiles() {
      this.isShow = !this.isShow;
      console.log(this.isShow);
    },
    increaseCount(){
      this.count = this.count + 1
      console.log(this.count)
    }
  },
};
</script>

<style></style>
