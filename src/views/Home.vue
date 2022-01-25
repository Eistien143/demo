<template>
  <v-container>
    <h3>See All Mobile</h3>
    <v-btn v-if="!isShow" @click="seeAllMobiles" class="ma-2">
      See All Mobiles
    </v-btn>
    <v-btn v-else @click="seeAllMobiles" class="ma-2" color="primary"
      >Hide All Mobiles</v-btn
    >
    <v-btn @click="shownumber" class="ma-2" color="primary">click here</v-btn>
    <h1>{{ count }}</h1>
    <h1>{{ message }}</h1>
    <div v-if="isShow">
      <!-- <Card
        v-for="(mobile, i) in carts"
        :key="i"
        v-bind:title="mobile.name"
        v-bind:description="mobile.details"
        :ammount="mobile.price"
      ></Card> -->
      <v-row>
        <v-col cols="12" sm="4" v-for="(mobile, i) in carts" :key="i">
          <v-card class="mx-auto" max-width="344">
            <v-img :src="mobile.img" height="200px" contain></v-img>

            <v-card-title> {{ mobile.name }} </v-card-title>

            <v-card-subtitle> {{ mobile.details }}</v-card-subtitle>
            <h3 class="ma-5">Price - {{ mobile.price }}</h3>
            <v-btn class="ma-5" color="warning" elevation="0"
              >Add to cart</v-btn
            >
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      isShow: true,
      carts: [
        {
          img: "https://www.91-img.com/gallery_images_uploads/a/5/a5c68c9160f2588c91d57d40e798d50315a1aa83.jpg?tr=h-550,w-0,c-at_max",
          name: "Samsung Mobile",
          details: "this is a samsung phone",
          price: "2000 Rs",
        },
        {
          img: "https://5.imimg.com/data5/SELLER/Default/2020/8/CF/GZ/SZ/84013069/jio-phone-500x500.jpeg",
          name: "Jio Mobile",
          details: "this is a Jio phone",
          price: "90000 Rs",
        },
        {
          img: "https://akm-img-a-in.tosshub.com/aajtak/images/photo_gallery/202110/vivo_y20t_2.jpg",
          name: "Vivo Mobile",
          details: "this is a samsung phone",
          price: "7000 Rs",
        },
        {
          img: "https://img.etimg.com/thumb/msid-50753229,width-1200,height-900/magazines/panache/intex-aqua-genx-review-scores-in-build-and-features-price-a-let-down.jpg",
          name: "Intex Mobile",
          details: "this is a intex phone",
          price: "70000 Rs",
        },
      ],
      count: null,
      message: "",
    };
  },
  created: function () {
    this.count = 0;
  },
  computed: {
    // count() {
    //   if (this.count !== 10) {
    //     this.count = this.count + 1;
    //   } else {
    //     this.message = "Count should be less than 10 or equal to 10";
    //   }
    //   return count;
    // },
  },
  methods: {
    seeAllMobiles() {
      this.isShow = !this.isShow;
    },
    shownumber() {
      if (this.count !== 10) {
        this.count = this.count + 1;
      } else {
        this.message = "Count should be less than 10 or equal to 10";
      }
    },
  },
};
</script>

<style></style>
>
