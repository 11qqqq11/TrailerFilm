<style scoped>
.search_box {
  width: clamp(200px, 70vw, 660px);
  height: 36px;
  background-color: #070707;
  border: 0px;
  border-bottom: 1px solid #8f8f8f;
  padding-left: 26px;
  color: #fff;
}

input::placeholder {
  font-family: Montserrat;
  font-size: 14px;
  color: #fff;
}

textarea:focus,
input:focus {
  outline: none;
}

/* .list_button {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin: 30px 21px 0px 20px;
}

.list_button .left {
  display: flex;
  text-align: left;
}

.list_button .left p {
  margin-left: 31px;
}

.list_button .left .movie1 {
  border-bottom: 2px solid #070707;
  font-weight: 900;
  color: #070707;
}

.list_button .left button {
  background-color: #fff;
  border: none;
  font-family: Montserrat;
  font-size: 18px;
  font-weight: 300;
  margin-left: 31px;
} */
iframe {
  width: 100%;
}

.iframe-container {
  display: flex;
  width: 100%;
}

.overlay {
  position: fixed;
  overflow-y: auto;
  top: 0px;
  left: 0px;
  right: 0px;
  bottom: 0px;
  background-color: black;
  opacity: 7%;
  z-index: 20;
}

.modal {
  position: fixed;
  top: 0px;
  left: 50%;
  transform: translate(-50%);
  background-color: #FFF;
  z-index: 20;
  display: flex;
  flex-direction: column;
  width: 75%;
}

.info-container {
  margin: 40px 60px 0px 60px;
}

.info {
  width: clamp(100%, 50%, 50%);
  display: grid;
  grid-template-columns: 1fr 8fr;
  color: #070707;
  font-family: Montserrat;
  font-size: 15.5px;
  font-weight: 300;
}

.info .item1 {
  grid-column-start: 1;
  grid-column-end: 3;
  font-family: Montserrat;
  font-size: 30px;
  font-weight: 500;
}

.info .item3 {
  color: #8c8c8c;
}

.genre-container {
  display: flex;
}

.genre {
  width: 142px;
  height: 40px;
  border: solid 1px var(--black-three);
  background-color: #070707;
  color: #FFF;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px 5px 0px 0px;
}

.modal iframe {
  border: none;
  width: 1fr;
  height: 30vw;
  margin: 0px 60px;
}

.summary {
  font-size: 14px;
  font-family: Montserrat;
  padding: 40px clamp(20px, 5vw, 60px) 100px clamp(20px, 5vw, 60px);
}

.modal img {
  width: 80%;
  margin: 0px auto 70px auto;
}

.button {
  position: fixed;
  z-index: 20;
  background-color: transparent;
  background-repeat: no-repeat;
  border: none;
  cursor: pointer;
  overflow: hidden;
  outline: none;
  color: #FFF;
}

.button.close {
  top: 20px;
  right: 20px;
  font-size: 18px;
}

.button.next {
  top: 50%;
  right: 5%;
  font-size: clamp(10px, 5vw, 74px);
}

.button.prev {
  top: 50%;
  left: 5%;
  font-size: clamp(10px, 5vw, 74px);
}

.movie-list {
  display: grid;
  grid-column-gap: 15px;
  grid-template-columns: repeat(auto-fit, 360px);
  margin: 30px 21px 0px 20px;
  justify-content: center;
}

.movie-container {
  position: relative;
  z-index: 10;
  width: fit-content;
  margin-bottom: 30px;
}

.movie-container .image-container {
  position: relative;
  width: 360px;
  height: 204px;
  z-index: initial;
}

.movie-container .movie-background-image {
  position: relative;
  width: 360px;
  height: 204px;
  z-index: -1;
}

.detail {
  display: grid;
  grid-template-columns: 70% 1fr;
  justify-content: center;
  align-items: center;
  margin: 10px auto 10px auto;
}

.right {
  text-align: right;
  justify-content: center;
}

.detail-icon {
  width: 12px;
  height: 12px;
}



/* .nav-button {
  display: flex;
  justify-content: center;
} */

/* CSS */
/* .button-12 {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 6px 14px;
  font-size: 20px;
  border-radius: 6px;
  border: none;
  margin: 0px 10px 60px 10px;
  background: #070707;
  box-shadow: 0px 0.5px 1px rgba(0, 0, 0, 0.1), inset 0px 0.5px 0.5px rgba(255, 255, 255, 0.5), 0px 0px 0px 0.5px rgba(0, 0, 0, 0.12);
  color: #DFDEDF;
}

.red {
  background-color: #ff2e43;
} */

.carousel__item {
  color: white;
  width: 200px;
  height: 80px;
  font-size: 18px;
  font-weight: 500;
  line-height: 1.11;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #070707;
  /* margin-left: 10px;
    margin-right: 26px; */
}

.movie-container {
  position: relative;
  z-index: 10;
  width: fit-content;
  margin-bottom: 30px;
}

.movie-container .image-container {
  position: relative;
  width: 360px;
  height: 204px;
  z-index: initial;
}

.movie-container .movie-background-image {
  position: relative;
  width: 360px;
  height: 204px;
  z-index: -1;
}

.movie-list {
  display: grid;
  grid-column-gap: 15px;
  grid-template-columns: repeat(auto-fit, 360px);
  margin: 30px 21px 0px 20px;
  justify-content: center;
}
</style>
<script>
/*eslint-disable */
import axios from 'axios';
// import { ref } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
// import { is } from '@babel/types';
// const isModalOpen = ref(false);
// let input = ref("");

export default ({
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data: () => ({
    Gernes: [
      { name: 'Action' },
      { name: 'Adventure' },
      { name: 'Animation' },
      { name: 'Biography' },
      { name: 'Comedy' },
      { name: 'Crime' },
      { name: 'Documentary' },
      { name: 'Drama' },
      { name: 'Family' },
      { name: 'Fantasy' },
      { name: 'History' },
      { name: 'Horror' },
      { name: 'Music' },
      { name: 'Musical' },
      { name: 'Mystery' },
      { name: 'Romance' },
      { name: 'Sci-Fi' },
      { name: 'Sport' },
      { name: 'Thriller' },
      { name: 'War' },
      { name: 'Western' },
    ],
    movies: '',
    isClicked: false,
    focus: '',
    input: '',
    gerne: 'all',
  }),

  methods: {
    async api() {
      let config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      const url = "https://yts.torrentbay.to/api/v2/list_movies.json?limit=30&&query_term=" + this.input.toLowerCase() +"&&genre=" + this.gerne.toLowerCase();
      const result = await axios.get(url, config);


      console.log(this.movies = result.data.data.movies);
    },
    focusGerne(item) {
      this.gerne = item;
      this.api();
    },
    toggleClick(item) {
      this.isClicked = !this.isClicked;
      console.log(this.focus = item);
    },
    nextFocus(prev) {
      this.isClicked = !this.isClicked;
      this.toggleClick(prev < 29 ? prev + 1 : 0);
    },
    prevFocus(prev) {
      this.isClicked = !this.isClicked;
      this.toggleClick(prev > 0 ? prev - 1 : 29);
    },

  },
  mounted() {
    this.api();
  },
})
</script>
<template>

  <nav class="d-flex justify-content-center align-items-center bg-black mb-2" style="height: 60px;">
    <div>
      <input type="text" class="search_box" placeholder="Search for movie......"  v-model="input" @keyup.enter="api()"/>
    </div>

  </nav>
  <div>
    <Carousel :items-to-show="9" :wrap-around="true" class="mb-2">
      <Slide v-for="gerne in Gernes" :key="gerne.name">
        <div class="carousel__item" @click="focusGerne(gerne.name)">{{ gerne.name }}</div>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>

    <div class="movie-list">
      <div v-for="movie in movies" class='movie-container' @click="toggleClick(movies.indexOf(movie))">
        <div class='image-container' :id="movie.id">
          <img class='movie-background-image' :src="movie.background_image" :alt="movie.title + 'background image'" />
        </div>

        <div class='detail'>
          <span>{{ movie.title }}</span>
          <span class='right'><img alt="star" class='detail-icon' src="./images/rating.png" />{{ movie.rating }} <img
              alt='clock' class='detail-icon' src="./images/clock.png" />{{ Math.floor(movie.runtime / 60) + "h" +
                  movie.runtime % 60 + 'm'
              }}</span>
        </div>
        <Teleport to="#modal">
          <div class='overlay' @click="toggleClick()" v-if="isClicked" />
          <div class='modal' v-if="isClicked">
            <div class='info-container'>
              <div class='info'>
                <div class='movie1 Text-Style-19'>{{ movies[focus].title }}</div>
                <div class='movie2'>{{ movies[focus].year }}</div>
                <div class='movie3'>{{ movies[focus].rating + "/10 - " + Math.floor(movies[focus].runtime / 60) + "h" +
                    movies[focus].runtime % 60 + 'm'
                }}</div>
              </div>



            </div>

            <img alt="large_cover" :src="movies[focus].large_cover_image" />

            <div class='summary'>
              {{ focus.summary }}
            </div>

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movies[focus].slug.toLowerCase().split('-').join('_') + '/medium-screenshot1.jpg'" />

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movies[focus].slug.toLowerCase().split('-').join('_') + '/medium-screenshot2.jpg'" />

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movies[focus].slug.toLowerCase().split('-').join('_') + '/medium-screenshot3.jpg'" />


          </div>
          <button class='button close' @click="toggleClick()">X</button>
          <button class='button next' @click="nextFocus(focus)">ᐳ</button>
          <button class='button prev' @click="prevFocus(focus)">ᐸ</button>
        </Teleport>
      </div>
    </div>


  </div>


</template>