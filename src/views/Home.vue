<template>
  <v-container class="pa-0 ma-0" fluid>
    <v-row>
      <v-col sm="" md="" lg="" xl="10" class="mx-auto">
        <v-carousel hide-delimiters height="615">
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
          >
            <v-overlay
              absolute
              :opacity=".5"
              class="overlay"
            >
            <h2 class="display-2 font-weight-light">{{item.text}}</h2>
            </v-overlay>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
    <WorkType />
    <About />
    <Contact />
    </v-container>
</template>

<script>
import WorkType from '../components/WorkType'
import About from '../components/About'
import Contact from '../components/Contact'
export default {
  components:{
    WorkType,
    About,
    Contact,
  },
  name: 'Home',
  data() {
    return {
      items: [
          {
            src: 'http://northalpinephoto.com/img/Untitled_HDR-39.jpg',
            text: 'Enhance Your Listing'
          },
          {
            src: 'http://northalpinephoto.com/img/Untitled_HDR-24.jpg',
            text: 'Professional Listing Photography'
          },
          {
            src: 'http://northalpinephoto.com/img/Untitled_HDR-2.jpg',
            text: 'Let Your House Been Noticed'
          },
          {
            src: 'http://northalpinephoto.com/img/Untitled_HDR-42.jpg',
            text: 'Attract the Right Buyer'
          },
        ],
    }
  },
  methods: {
    openSocial(item){
      window.open(item)
    },
  }
}
</script>

<style scoped>

.overlay {
  height: 650px;
}
</style>