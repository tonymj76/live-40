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
      <div class="feature__header text-uppercase grey--text lighten-4">
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
              <div class="feature__content">
                <a href="#" class="l__texture overline">News</a>
                <h3 class="l__title headline">
                  <a href="#">7 Things to Know About HIIT</a>
                </h3>
                <p class="feature__subtitle subtitle-1">
                  Check out the scientific research behind HIIT and get hooked.
                </p>
                <a href class="l__readmore text-uppercase">Read More</a>
              </div>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="4">advert</v-col>
      </v-row>
    </section>
    <section id="workout">
      <div>
        <h2 class="workout__header display-2 grey--text lighten-4">
          <span>Workout</span>
        </h2>
        <v-row>
          <v-col sm="12" md="6">
            <v-card flat>
              <v-img
                class="white--text align-end"
                height="200px"
                :src="card.urlwork"
                :alt="card.altwork"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                lazy-src="https://picsum.photos/id/11/100/60"
              >
                <v-card-title>this should be coming from the api</v-card-title>
              </v-img>

              <v-card-subtitle
                class="pb-0 px-0 overline l__texture text-uppcase"
              >
                workout tips
              </v-card-subtitle>

              <v-card-text class="text--primary px-0">
                <h3 class="l__title headline">
                  <a href="#">
                    The Best Bodyweight Exercises to Train Your Abs and Obliques
                  </a>
                </h3>

                <div>
                  <p class="l__subtitle subtitle-1">
                    Check out the scientific research behind HIIT and get
                    hooked.
                  </p>
                </div>
              </v-card-text>

              <v-card-actions class="px-0">
                <a href="#" class="l__readmore text-uppercase">
                  Read More
                </a>

                <v-btn color="orange" text>
                  Share
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col sm="12" md="6" class="pl-md-12">
            <article
              v-for="n in 3"
              :key="n"
              color="white"
              class="d-flex flex-row pb-2"
            >
              <n-link to="/">
                <v-img
                  :src="card.urlworkArt"
                  :alt="card.altworkArt"
                  height="72"
                  width="128"
                ></v-img>
              </n-link>

              <div class="article__content pl-5">
                <v-card-subtitle
                  class="pa-0 l__texture overline"
                  v-text="'the artise'"
                ></v-card-subtitle>
                <h4
                  class="article__title headline px-0 pt-0"
                  v-text="'Build Massive Muscles with Time Under Tension'"
                ></h4>
              </div>
            </article>
            <v-btn block outlined color="info">
              <span class="cation">View more</span>
            </v-btn>
          </v-col>
        </v-row>
      </div>
    </section>
    <section id="nutrition">
      <div>
        <h2 class="workout__header display-2 grey--text lighten-4">
          <span>Nutrition</span>
        </h2>
        <v-row>
          <v-col sm="12" md="6">
            <v-card flat>
              <v-img
                class="white--text align-end"
                height="200px"
                :src="card.urlnut"
                :alt="card.altnut"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                lazy-src="https://picsum.photos/id/11/100/60"
              >
                <v-card-title>this should be coming from the api</v-card-title>
              </v-img>

              <v-card-subtitle
                class="pb-0 px-0 overline l__texture text-uppcase"
              >
                workout tips
              </v-card-subtitle>

              <v-card-text class="text--primary px-0">
                <h3 class="l__title headline">
                  <a href="#">
                    The Best Bodyweight Exercises to Train Your Abs and Obliques
                  </a>
                </h3>

                <div>
                  <p class="l__subtitle subtitle-1">
                    Check out the scientific research behind HIIT and get
                    hooked.
                  </p>
                </div>
              </v-card-text>

              <v-card-actions class="px-0">
                <a href="#" class="l__readmore text-uppercase">
                  Read More
                </a>

                <v-btn color="orange" text>
                  Share
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col sm="12" md="6" class="pl-md-12">
            <article
              v-for="n in 3"
              :key="n"
              color="white"
              class="d-flex flex-row pb-2"
            >
              <n-link to="/">
                <v-img
                  :src="card.urlnutArt"
                  :alt="card.altnutArt"
                  height="72"
                  width="128"
                ></v-img>
              </n-link>

              <div class="article__content pl-5">
                <v-card-subtitle
                  class="pa-0 l__texture overline"
                  v-text="'the artise'"
                ></v-card-subtitle>
                <h4
                  class="article__title headline px-0 pt-0"
                  v-text="'Build Massive Muscles with Time Under Tension'"
                ></h4>
              </div>
            </article>
            <v-btn block outlined color="info">
              <span class="cation">View more</span>
            </v-btn>
          </v-col>
        </v-row>
      </div>
    </section>
    <section id="video"></section>
    <section id="subscribe__form">
      <v-card class="subscribe__card mx-auto" max-width="344">
        <v-container class="pb-0">
          <v-row>
            <v-col>
              <v-row justify="center">
                <v-avatar color="red">
                  <span class="white--text headline">SB</span>
                </v-avatar>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
        <v-card-title class="text-center">
          Subscribe For Latest Updates and you must
        </v-card-title>
        <v-card-subtitle class="text-center">
          Signup for our newsletters and get notified when we publish new
          article for free
        </v-card-subtitle>
        <v-form v-model="valid">
          <v-container class="py-0">
            <v-col sm="12" md="12" class="py-0">
              <v-text-field
                v-model="email"
                :rules="emailRules"
                label="E-mail"
                class="pt-0"
                required
              ></v-text-field>
            </v-col>
            <v-col sm="6" class="mx-auto pt-0">
              <v-row justify="center">
                <v-btn class="info pt-0" large>subscribe</v-btn>
              </v-row>
            </v-col>
          </v-container>
        </v-form>
      </v-card>
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
      subscribeForm: {
        url: 'p.png',
        alt: 'profile'
      },
      card: {
        title: '',
        url: 'three-women-kneeling-on-floor.jpg',
        alt: 'three-women-kneeling-on-floor',
        urlwork:
          'person-wearing-black-shorts-and-blue-lace-up-low-top-sneaker.jpg',
        altwork: 'person-wearing-black-shorts-and-blue-lace-up-low-top-sneaker',
        urlworkArt: 'woman-lifting-barbell.jpg',
        altworkArt: 'woman-lifting-barbell',
        urlnut: 'agriculture-beans-corn-food.jpg',
        altnut: 'agriculture-beans-corn-food',
        urlnutArt: 'agriculture-beans-tomato.jpg',
        altnutArt: 'agriculture-beans-tomato'
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
.l__texture {
  color: #2a2a2a;
  background: transparent;
}
article {
  border-bottom: 1px solid #7f7f7f53;
  margin-bottom: 8px !important;
}

a {
  text-decoration: none;
  transition: color 0.2s, background 0.2s, opacity 0.2s;
}

.l__title > a {
  font-family: givefont('convergence') !important;
  color: #2a2a2a;
  max-height: 2.2em;
  text-overflow: ellipsis;
  line-height: 1.063;
  transition: opacity 0.2s;
  text-transform: uppercase;
  letter-spacing: -1px;
  @include fontSize(26px);
}

.article__title {
  font-family: givefont('convergence') !important;
  color: #2a2a2a;
  max-height: 5.2em;
  text-overflow: ellipsis;
  line-height: 1;
  transition: opacity 0.2s;
  letter-spacing: -1px;
  text-transform: capitalize;
  @include fontSize(18px);
}

.l__readmore {
  font-family: givefont('roboto') !important;
  font-weight: 400;
  @include fontSize(12px);
  letter-spacing: 4px;
  line-height: 21px;
  position: relative;
  &:after {
    content: '';
    display: block;
    width: 25px;
    height: 3px;
    background: #f01616;
    position: absolute;
    top: 100%;
    left: 0;
    transition: width 0.2s ease-out;
  }
  &:hover:after {
    width: 100px;
  }
}

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
  .feature__header {
    font-family: givefont('convergence') !important;
    font-weight: 400;
    font-size: 21px;
    letter-spacing: -1px;
    line-height: 36px;
  }
  .feature__content {
    padding-bottom: calculateRem(16px) !important;
    border-bottom: 1px solid #9e9e9e;
    padding-top: calculateRem(10px);
    .feature__subtitle {
      max-height: 90px !important;
      padding-bottom: 3px !important;
      line-height: calculateRem(22px) !important;
    }
  }
}
#workout {
  @include globalView;
  .grey--text {
    color: #9e9e9e5e !important;
  }
  .workout__header {
    width: 100%;
    overflow: hidden;
    margin-bottom: 33px;
    span {
      font-family: givefont('convergence');
      font-weight: 600 !important;
    }
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
#nutrition {
  @include globalView;
  .grey--text {
    color: #9e9e9e5e !important;
  }
  .workout__header {
    width: 100%;
    overflow: hidden;
    margin-bottom: 33px;
    span {
      font-family: givefont('convergence');
      font-weight: 600 !important;
    }
  }
  .workout__header span {
    position: relative;
    text-transform: uppercase;
  }
  .workout__header span:after {
    content: '';
    width: 100vw;
    height: 8px;
    background: #16f0ab;
    position: absolute;
    top: calc(50% - 4px);
    left: calc(100% + 30px);
  }
}

#subscribe__form {
}
</style>
