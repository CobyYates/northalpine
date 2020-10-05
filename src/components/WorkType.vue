<template>
  <v-container fluid class="d-flex justify-center">
    <v-row class="my-12 mx-auto">
      <v-col sm="" md="" lg="" xl="3" class="d-flex justify-space-around" v-for="item in sections" :key="item.i">
          <v-card tile width="350">
            <v-img width="100%" class="elevation-3" height="500" :src="`${item.img}`">
            <v-overlay absolute :opacity="0.1" class="overlay d-flex align-end">
              <p class="title font-weight-light">{{item.text}}</p>
            </v-overlay>
            </v-img>
          </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      sections: [
        { img: "http://northalpinephoto.com/img/Untitled_HDR-42.jpg", text: "Home Listing", link: "" },
        { img: "https://images.pexels.com/photos/1123972/pexels-photo-1123972.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500", text: "Drone", link: "" },
        { img: "http://northalpinephoto.com/img/Untitled_HDR-42.jpg", text: "Videography", link: "" },
        { img: "http://northalpinephoto.com/img/Untitled_HDR-42.jpg", text: "", link: "" },
      ],
    };
  },
};
</script>

<style>
  .overlay {
    position: absolute;
    bottom: 0;
    
  }
  .overlay p {
    color: white;
  }
</style>
