<template>
  <div>
    <div class="carousel-wrapper ">
      <VueSlickCarousel v-bind="slickOptions">
        <div v-for="i in 1" :key="i" class="img-wrapper">
          <img
            class="img-fluid"
            src="https://cdn-plat.apidigi.com/plat/prd/Img/partners/1102/banner/1920-1008%20Pragmatic%20Play.png"
          />
        </div>
      </VueSlickCarousel>
    </div>
    <div class="container-fluid px-4 body-section" style="margin-top: -320px">
      <div class="row mb-3 d-none">
        <div class="col-md-4 col-lg-4">
          <nuxt-link to="/" class="tl_landing_banner">
            <div class="card border-0 rounded-3">
              <img
                class="card-img-top"
                src="https://crashcasinos.com/wp-content/uploads/2020/08/crash-entry-cfec08.jpg"
                alt=""
              />
            </div>
          </nuxt-link>
        </div>
        <div class="col-md-4 col-lg-4">
          <nuxt-link to="/" class="">
            <div
              class="card border-0 rounded-3"
              style="height: 170px; object-fit: contain"
            >
              <img
                class="card-img-top"
                src="https://cdn-plat.apidigi.com/plat/prd/Img/partners/1102/banner/516-302 Games.png"
                alt=""
              />
            </div>
          </nuxt-link>
        </div>
        <div class="col-md-4 col-lg-4">
          <nuxt-link to="/" class="tl_landing_banner">
            <div
              class="card border-0 rounded-3"
              style="height: 170px; object-fit: contain"
            >
              <img
                class="card-img-top"
                src="https://cdn-plat.apidigi.com/plat/prd/Img/partners/1102/banner/516-302 Statistiques.png"
                alt=""
              />
            </div>
          </nuxt-link>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-6 col-lg-2 mb-2 pr-sm-2 pr-0">
          <nuxt-link to="">
            <div class="card landing-card">
              <div class="card-body  d-flex align-items-center flex-column">
                <img src="~/assets/img/Sport.png" />
                <p class="mb-0 mt-auto">SPORT</p>
              </div>
            </div>
          </nuxt-link>
        </div>
        <div class="col-6 col-lg-2 mb-2">
          <nuxt-link to="">
            <div class="card landing-card">
              <div class="card-body d-flex align-items-center flex-column">
                <img src="~/assets/img/live.png" />
                <p class="mb-0 mt-auto">LIVE</p>
              </div>
            </div>
          </nuxt-link>
        </div>
        <div class="col-6 col-lg-2 mb-2 pr-sm-2 pr-0">
          <nuxt-link to="">
            <div class="card landing-card">
              <div class="card-body d-flex align-items-center flex-column">
                <img src="~/assets/img/Games.png" />
                <p class="mb-0 mt-auto">GAMES</p>
              </div>
            </div>
          </nuxt-link>
        </div>
        <div class="col-6 col-lg-2 mb-2">
          <div class="card landing-card">
            <div class="card-body d-flex align-items-center flex-column">
              <img
                style="height: 38px; width: auto"
                src="~/assets/img/Virtual.png"
              />
              <p class="mb-0 mt-auto">VIRTUAL</p>
            </div>
          </div>
        </div>
        <div class="col-6 col-lg-2 mb-2 pr-sm-2 pr-0">
          <nuxt-link to="">
            <div class="card landing-card">
              <div class="card-body d-flex align-items-center flex-column">
                <img src="~/assets/img/Casino.png" />
                <p class="mb-0 mt-auto">CASINO</p>
              </div>
            </div>
          </nuxt-link>
        </div>
        <div class="col-6 col-lg-2">
          <nuxt-link to="">
            <div class="card landing-card">
              <div class="card-body d-flex align-items-center flex-column">
                <img src="~/assets/img/Lucky-balls.png" />
                <p class="mt-auto mb-0">LUCKY BALLS</p>
              </div>
            </div>
          </nuxt-link>
        </div>
      </div>

      <Highlights />
      <div class="casino">
        <div class="px-0 col-12 mb-3">
          <nuxt-link
            to="/"
            id=""
            class="btn bg-black border-white text-uppercase font-weight-bold"
            href="#"
            role="button"
            style="color: #fea62b; font-size: 13px"
            >Top Casino Games</nuxt-link
          >
        </div>
        <div class="row justify-content-center mb-3">
          <div class="col-12 mb-3">
            <nuxt-link to="/" class="tl_games_slider_game">
              <div class="card border-0 rounded-3">
                <img
                  class="card-img-top"
                  src="~/assets/img/spaceman.png"
                  alt=""
                />
              </div>
            </nuxt-link>
          </div>
          <div class="col-12 mb-3">
            <nuxt-link to="/" class="tl_games_slider_game">
              <div class="card border-0 rounded-3">
                <img

                  src="~/assets/img/rocketman.png"
                  alt=""
                />
              </div>
            </nuxt-link>
          </div>
          <div class="col-12 mb-3">
            <nuxt-link to="/" class="tl_games_slider_game">
              <div class="card border-0 rounded-3">
                <img
                  class="card-img-top"
                  src="https://cdn-plat.apidigi.com/plat/prd/Img/partners/1102/banner/Casino_Game_4.png"
                  alt=""
                />
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Highlights from '~/components/Highlights'
export default {
  components: { Highlights },
  name: 'home',
  layout: 'default',

  data() {
    return {
      slickOptions: {
        dots: false,
        arrows: false,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
      },
    }
  },
}
</script>

<style>
.carousel-wrapper {
  padding: 0px 0px;
}
.img-wrapper img {
  margin: auto;
  width: 100%;
  height: 700px;
  background-image: linear-gradient(gray 100%, transparent 0);
}

@media screen and (max-width: 568px) {
  .img-wrapper img {
    width: 100%;
    height: 700px;
    object-fit: cover;
    position: relative;
    object-position: top 50%;
    left: 0;
  }
}

.bg-black {
  background: #000;
}

.tl_games_slider_game img
{
  height: 320px;
  width: 100%;
  object-fit: cover;
}

.landing-card {
  background-color: #333;
  color: white;
  height: 120px;
}

.landing-card img {
  width: 50px;
}

</style>
