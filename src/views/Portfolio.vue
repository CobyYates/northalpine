<template>
  <v-container fluid>
    <v-row class="justify-center">
      <v-col xl="8">
        <v-item-group mandatory>
          <v-container>
            <v-row>
              <v-col v-for="n in btns" :key="n.i" cols="12" md="3" class="d-flex justify-center">
                <v-item v-slot:default="{ active, toggle }">
                  <v-card
                    :color="active ? 'primary' : ''"
                    class="d-flex align-center justify-center text-center"
                    dark
                    height="50"
                    width="150"
                    @click="toggle; filterBtn(n)"
                  >
                    {{ n.text }}
                    <!-- <v-scroll-y-transition>
                      <div
                        v-if="active"
                        class="display-3 flex-grow-1 text-center"
                      >
                      </div>
                    </v-scroll-y-transition> -->
                  </v-card>
                </v-item>
              </v-col>
            </v-row>
          </v-container>
        </v-item-group>
        <v-row>
          <v-col
            v-for="n in gallery"
            :key="n.i"
            class="d-flex child-flex"
            cols="3"
          >
            <!-- :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`" -->
            <v-img :src="`${n.img}`" aspect-ratio="1" class="grey lighten-2">
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                  ></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-dialog>
        <!-- <v-img :src="`${}`" /> -->
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      btns: [
        { text: "Portrait", value: "portrait" },
        { text: "Interior", value: "interior" },
        { text: "Exterior", value: "exterior" },
        { text: "Drone", value: "drone" },
      ],
      gallery: null,
      galleryImages: [
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/81233469_1015699518790685_2600888924768756994_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=105&_nc_ohc=BD0JftGiqIgAX8p0F7M&oh=5df511308759493c4b23014e63d57872&oe=5FA46030",
          text: "Ginger",
          lazy: "",
          tags: "Portrait",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/e35/s1080x1080/83564155_1478794572275001_8245614526433543684_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=109&_nc_ohc=4VK-ldGP6ikAX83mrhg&_nc_tp=15&oh=a962f8e7b2f7f280b4b1e2deeb9bfbbf&oe=5FA66458",
          text: "",
          lazy: "",
          tags: "Portrait",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/e15/82895609_122805892395416_2068763661368497477_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=108&_nc_ohc=N7ucm7FYku4AX8y01wk&_nc_tp=18&oh=6bd8987b42ee75ad1a73cb9a5803ff86&oe=5FA61EE4",
          text: "",
          lazy: "",
          tags: "Portrait",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/e15/84121322_573445800179540_1689275817234981783_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=108&_nc_ohc=-4SeJMp3-dgAX8yrWuR&_nc_tp=18&oh=9134702d93a2a2424a2477b8295f7c77&oe=5FA5D794",
          text: "",
          lazy: "",
          tags: "Portrait",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118380263_168638361408431_6940271863287786128_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=111&_nc_ohc=ybzJJRAqinwAX-9bFOC&oh=9836de5758681b236f0d316fa5468f21&oe=5FA4177D",
          text: "",
          lazy: "",
          tags: "Exterior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118321232_760201541479455_6488018246016257686_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=103&_nc_ohc=6E80yKcFzLIAX8ShN_Y&oh=bcd39ba3cd2f666530e1b4d060e77be4&oe=5FA65453",
          text: "",
          lazy: "",
          tags: "Exterior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118206387_2640110449639593_7454643859404659522_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=109&_nc_ohc=-QTB-3G_ZB8AX8_FdHe&oh=a34df5d9114f4d7606448134dd44d267&oe=5FA51163",
          text: "",
          lazy: "",
          tags: "Interior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118235404_1417162412008677_6768086232070371316_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=109&_nc_ohc=ayklfxrlHfwAX_h62UY&oh=1bf9820f264083538b477bdada56d15b&oe=5FA4F1E8",
          text: "",
          lazy: "",
          tags: "Interior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118215095_804221263665802_5621234671316709620_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=110&_nc_ohc=TOCOOcv54_gAX9MJlCG&oh=646d1b6d1c0e4daa3214aaabfeb14fcf&oe=5FA53EF3",
          text: "",
          lazy: "",
          tags: "Interior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118289490_2666000333717623_1039895073271158984_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=107&_nc_ohc=7k3ZDkTow0kAX8hULUO&oh=3f96dec06b9de1f4928e7d59358bcdd9&oe=5FA6708D",
          text: "",
          lazy: "",
          tags: "Interior",
        },
        {
          img:
            "https://scontent-den4-1.cdninstagram.com/v/t51.2885-15/fr/e15/s1080x1080/118318641_167850591578615_4087133035434573958_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_cat=111&_nc_ohc=I5ISqg4KyWoAX9nyz_c&oh=920526a7390b63d6469ed08633a8345f&oe=5FA3D8B3",
          text: "",
          lazy: "",
          tags: "Interior",
        },
      ],
    };
  },
  methods: {
      filterBtn(btn){
        this.gallery = this.galleryImages.filter(e => e.tags === btn.text)
        console.log(this.galleryImages.filter(e => e.tags === btn.text))
      }
  },
  mounted() {
    this.gallery = this.galleryImages
  }
};
</script>

<style></style>
