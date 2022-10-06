<template>
  <div class="row my-3">
    <div class="col-12">
      <div class="d-flex align-items-center">
        <!-- <a name="" id="" class="btn btn-black label text-white border-white rounded mb-3 mr-3" href="#" role="button">TOP MATCHES</a> -->
        <ul class="nav nav-tabs float-end top-matches mb-3">
          <!-- <li class="nav-item">
            <a href="#" class="nav-link active sport-label">TOP MATCHES</a>
          </li> -->
          <li class="nav-item">
            <a href="#" class="nav-link font-weight-bold p-2 active-sport mr-1"
              >⚽️ <span class="sport_name"><i>FOOTBALL</i></span></a
            >
          </li>
          <li class="nav-item disabled">
            <a href="#" class="nav-link text-white p-2 rounded mr-1"
              >BASKETBALL <span class="sport_name"></span
            ></a>
          </li>
          <li class="nav-item disabled mb-3">
            <a href="#" class="nav-link text-white p-2 rounded mr-1"
              >TENNIS <span class="sport_name"></span
            ></a>
          </li>
          <li class="nav-item disabled">
            <a href="#" class="nav-link text-white p-2 rounded"
              >VOLLEYBALL <span class="sport_name"></span
            ></a>
          </li>
        </ul>
      </div>
      <div class="tab-content">
        <div v-if="!loading" class="tab-pane active">
          <div class="row row-cols-1 row-cols-md-3 g-4" v-if="fixtures.length">
            <!-- <p>{{ fixtures }}</p> -->
            <div
              class="col-4 mb-3"
              v-for="(sp, index) in fixtures"
              :key="index"
            >
              <div class="card h-100">
                <div class="card-body d-flex flex-column">
                  <p class="text-left mb-4">
                    <span class="flag"></span> {{ sp.sport_category_name }} •
                    {{ sp.sport_tournament_name }}
                  </p>
                  <div class="d-flex align-items-center justify-content-between">
                    <div class="col-4 team_a">
                      <h6>{{ sp.team_a }}</h6>
                    </div>
                    <div class="col-4 text-center match_time team_a">
                      <span class="h6">{{ sp.event_time }} </span>
                      <span>{{ sp.event_date }}</span>
                    </div>
                    <div class="col-4 text-right team_b">
                      <h6>{{ sp.team_b }}</h6>
                    </div>
                  </div>
                  <div class="card-footer mt-auto p-0">
                    <div class="d-flex justify-space-between align-items-center">
                    <Odds
                      v-for="o in sp.odds"
                      :key="o.id"
                      v-bind:odds="o.odds"
                      v-bind:name="o.name"
                      v-bind:active="o.active"
                    />
                  </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <p class="text-center" v-if="fixtures.length < 1">No data available</p>
        <div v-if="loading" class="col-12 text-center loading">
          <b-spinner type="spin"></b-spinner>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Odds from './Odds.vue'
export default {
  components: { Odds },
  name: 'highlights',
  data() {
    return {
      fixtures: [],
      // odds: [],
      loading: false,
      slickOptions: {
        dots: false,
        arrows: false,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
      },
    }
  },
  // computed:{

  // },

  methods: {
    getSports() {
      this.loading = true
      this.$axios
        .get(
          'https://sports-api.sportsbookengine.com/api/sports/mobile/highlights'
        )
        .then((res) => {
          this.fixtures = res.data[0].fixtures

          // console.log(res.data[0])
          this.loading = false
        })
    },
  },
  mounted() {
    this.getSports()
  },
}
</script>

<style scoped>
ul.nav.nav-tabs.top-matches {
  border-bottom: 0 !important;
}

a.label {
  font-size: 14px;
  font-weight: 400;
}
.top-matches .sport-label {
  background-color: black !important;
  color: white !important;
  border-radius: 0.25rem !important;
}

.top-matches a.nav-link.active-sport {
  background-color: #000 !important;
  color: #fea62b !important;
  border-radius: 0.25rem !important;
  border-color: white;
}

.top-matches a.nav-link.active-sport span.sport_name {
  display: inline;
}

.top-matches a.nav-link {
  color: #545454;
  background-color: #000;
  box-shadow: inset 0.5px 0.5px 2px #545454, 0 2px 4px rgb(26 26 26 / 50%);
}

.top-matches a.nav-link span.sport_name {
  display: none;
}

.tab-content .tab-pane .card {
  border-radius: 8px;
  padding-left: 0px;
  padding-right: 0px;
  background-color: #020202;
  color: #fff;
}

.match_logo {
  width: 52px;
  height: 52px;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
  -webkit-box-pack: center;
  justify-content: center;
  flex-shrink: 0;
  margin-left: auto;
  margin-right: auto;
  border-radius: 50%;
  box-shadow: inset 0.5px 0.5px 2px #545454, 0 2px 4px rgb(26 26 26 / 50%);
  background-color: #393939;
}

.match_logo > img {
  max-width: 28px;
  max-height: 28px;
  object-fit: contain;
}

.team_a h6, .team_b h6{
  color: #fea62b;
}

.match_time {
  width: 98px;
  display: flex;
  flex-direction: column;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
}
</style>
