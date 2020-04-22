<template>
  <main>
    <section id="section__top" my-0>
      <div class="section__image">
        <v-img
          :src="sectionImage.url"
          :alt="sectionImage.alt"
          class="grey lighten-2"
          height="100%"
          lazy-src="https://picsum.photos/id/11/100/60"
        >
          <template v-slot:placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="blue"
              ></v-progress-circular>
            </v-row>
          </template>
        </v-img>
      </div>
      <div class="section__carousel">
        <v-carousel
          cycle
          height="100%"
          hide-delimiters
          hide-delimiter-background
          show-arrows-on-hover
        >
          <v-carousel-item v-for="(slide, i) in slides" :key="i">
            <v-card
              class="mx-auto"
              :color="colors[i]"
              height="100%"
              elevation="6"
            >
              <v-card-text>
                <div>Word of the Day</div>
                <p class="display-1 text--primary">be•nev•o•lent</p>
                <p>adjective</p>
                <div class="text--primary">{{ slide }}</div>
              </v-card-text>
              <v-card-actions>
                <v-btn text color="deep-purple accent-4">Learn More</v-btn>
              </v-card-actions>
            </v-card>
          </v-carousel-item>
        </v-carousel>
      </div>
    </section>
    <section id="feature">
      <div
        class="title feature__header subtitle-1 text-uppercase grey--text lighten-4"
      >
        Featured Article
      </div>
      <v-row>
        <v-col sm="12" md="8" class="pt-0">
          <v-row v-for="i in 3" :key="i" no-gutters>
            <v-col sm="12" md="8">
              <div class="feature__cards">
                <v-card class="mx-auto" flat>
                  <v-img
                    :src="card.url"
                    :alt="card.alt"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="100%"
                    lazy-src="https://picsum.photos/id/11/100/60"
                  >
                    <v-card-title
                      class="py-0 pl-2"
                      v-text="card.title"
                    ></v-card-title>
                    <v-card-actions>
                      <v-btn fab x-small>
                        <v-icon small class="red--text">mdi-heart</v-icon>
                      </v-btn>
                    </v-card-actions>
                  </v-img>
                </v-card>
              </div>
            </v-col>
            <v-col sm="12" md="4">
              <div class="feature__content text-uppercase">
                <a href="#" class="feature__category overline"
                  >feature category</a
                >
                <h3 class="feature__title headline">
                  <a href="#">some big header</a>
                </h3>
                <p class="feature__subtitle subtitle-2">
                  feature card__subtitle
                </p>
                <a href class="feature__readmore caption">readmore</a>
              </div>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="4">advert</v-col>
      </v-row>
    </section>
    <section id="workout">
      <div>
        <h2 class="workout__header display-2 grey--text lighten-2">
          <span>Workout</span>
        </h2>
        <v-row>
          <v-col sm="12" md="6">
            <v-card flat>
              <v-img
                class="white--text align-end"
                height="200px"
                :src="card.url2"
                :alt="card.alt2"
              >
                <v-card-title>Top 10 Australian beaches</v-card-title>
              </v-img>

              <v-card-subtitle class="pb-0 px-0">Number 10</v-card-subtitle>

              <v-card-text class="text--primary px-0">
                <div>Whitehaven Beach</div>

                <div>Whitsunday Island, Whitsunday Islands</div>
              </v-card-text>

              <v-card-actions class="px-0">
                <v-btn color="orange" text>
                  Share
                </v-btn>

                <v-btn color="orange" text>
                  Explore
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col sm="12" md="6">
            <v-card v-for="n in 3" :key="n" color="white" flat>
              <div class="d-flex flex-no-wrap justify-space-around">
                <div>
                  <v-card-title
                    class="headline px-0"
                    v-text="'some head line'"
                  ></v-card-title>

                  <v-card-subtitle
                    class="px-0"
                    v-text="'the artise'"
                  ></v-card-subtitle>
                </div>

                <v-avatar class="ma-3" size="100" tile>
                  <v-img :src="card.url2" :alt="card.alt2"></v-img>
                </v-avatar>
              </div>
            </v-card>
            <v-btn block outlined color="info">
              <span class="cation">View more</span>
            </v-btn>
          </v-col>
        </v-row>
      </div>
    </section>
    <section id="email__setup">
      <v-form v-model="valid">
        <v-container>
          <v-row>
            <v-col sm="12" md="4">
              <v-text-field
                v-model="email"
                :rules="emailRules"
                label="E-mail"
                required
              ></v-text-field>
            </v-col>
            <v-col sm="12" md="2">
              <v-btn class="info" large>subscribe</v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      valid: null,
      email: '',
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      sectionImage: {
        url: 'man-holding-black-dumbbell.jpg',
        alt: 'man-holding-black-dumbbell'
      },
      card: {
        title: 'card title',
        url: 'three-women-kneeling-on-floor.jpg',
        alt: 'three-women-kneeling-on-floor',
        url2:
          'person-wearing-black-shorts-and-blue-lace-up-low-top-sneaker.jpg',
        alt2: 'person-wearing-black-shorts-and-blue-lace-up-low-top-sneaker'
      },
      colors: [
        'indigo',
        'warning',
        'pink darken-2',
        'red lighten-1',
        'deep-purple accent-4'
      ],
      slides: [
        'lorem dklaskdfk slklkdlf k akdkd fkk adk d kid',
        'Second',
        'Third',
        'Fourth',
        'Fifth'
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
#section__top {
  display: grid;
  grid-template-columns: 2em 1fr;
  grid-template-rows: repeat(5, 5rem);
  gap: 0px !important;

  .section__image {
    grid-row: 1 / span 3;
    grid-column: 1/-1;
  }
  .section__carousel {
    grid-row: 3 / span 3;
    grid-column: 2;
  }
}
#feature {
  @include globalView;
  .feature__cards {
    padding-top: calculateRem(10px);
  }
  .feature__content {
    padding-bottom: calculateRem(16px) !important;
    border-bottom: 1px solid #9e9e9e;
    padding-top: calculateRem(10px);
    .feature__header {
      padding-bottom: calculateRem(20px);
    }
    .feature__subtitle {
      padding-bottom: 3px !important;
    }
  }
}
#workout {
  @include globalView;
  .workout__header {
    width: 100%;
    overflow: hidden;
    margin-bottom: 33px;
  }
  .workout__header span {
    position: relative;
    text-transform: uppercase;
  }
  .workout__header span:after {
    content: '';
    width: 100vw;
    height: 8px;
    background: #f01616;
    position: absolute;
    top: calc(50% - 4px);
    left: calc(100% + 30px);
  }
}
</style>
