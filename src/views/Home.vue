<template>
  <div class="home">
    <v-row>
      <v-col class="d-flex justify-space-around mx-auto mt-12">
        <p>HOME</p>
        <p>PORTFOLIO</p>
        <!-- <v-img
          height="100"
          src="https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg"
        /> -->
        <p>ABOUT</p>
        <p>CONTACT</p>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="10" class="mx-auto">
        <v-carousel hide-delimiters>
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
          ></v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="8" class="d-flex justify-space-around mx-auto">
        <v-btn text>Book Now</v-btn>
        <v-btn text>Portfolio</v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data() {
    return {
      items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          },
        ],
    }
  }
}
</script>
