<style scoped>
.list_button {
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



.nav-button {
  display: flex;
  justify-content: center;
}

/* CSS */
.button-12 {
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
}

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
import { ref } from 'vue'
import AppHeader from "@/components/AppHeader.vue";
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
const isModalOpen = ref(false);
// useEffect(() => {
//     axios(`https://yts.torrentbay.to/api/v2/list_movies.json?limit=30&&query_term=${searchTerm}&&genre=${genre}&&sort_by=${sortBy}&&page=${page}`).then(res => {
//       const result = res.data.data;
//       console.log(result);
//       setmovies(result.movies);
//       setPageCount(Math.floor(result.movie_count / result.limit) + 1);
//       console.log(pageCount);
//     })
//   }, [page, sortBy, searchTerm, genre, isOpen]);

// const movieList = {
//   movies: [],
//   created() {
//     const fetchData = async () => {
//       const movies = await axios.get('https://yts.torrentbay.to/api/v2/list_movies.json?limit=1');

//       this.movies = movies;
//       console.log(movieList.movies);
//     };

//     fetchData();
// },
// }

//   const url = `https://yts.torrentbay.to/api/v2/list_movies.json?limit=1`
//   fetch(url)
// 		.then(res => res.json())
// 		.then(data => {
// 			movies.value = data.data.movies;
//       console.log(data);
// 		})
// }
export default ({
  components: {
    Carousel,
    Slide,
    Navigation,
    AppHeader,
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
  }),
  methods: {
    async api() {
      let config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      const result = await axios.get('https://yts.torrentbay.to/api/v2/list_movies.json?limit=30', config);


      console.log(this.movies = result.data.data.movies);
    }

  },
  mounted() {
    this.api();
  },
})
</script>
<template>

  <AppHeader />
  <div>
    <Carousel :items-to-show="9" :wrap-around="true" class="mb-2">
      <Slide v-for="gerne in Gernes" :key="gerne.name">
        <div class="carousel__item">{{ gerne.name }}</div>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>

    <div class="movie-list">
      <div v-for="movie in movies" class='movie-container'>
        <div class='image-container' :id="movie.id">
          <img class='movie-background-image' :src="movie.background_image" :alt="movie.title + 'background image'"
            @click="isModalOpen = true" />
        </div>

        <div class='detail'>
          <span>{{ movie.title }}</span>
          <span class='right'><img alt="star" class='detail-icon' src="./images/rating.png" />{{ movie.rating }} <img
              alt='clock' class='detail-icon' src="./images/clock.png" />{{ Math.floor(movie.runtime / 60) + "h" +
                  movie.runtime % 60 + 'm'
              }}</span>
        </div>
        <Teleport to="#modal" :data="movie">

          <div className='modal' v-if="isModalOpen">
            <div className='info-container'>
              <div className='info'>
                <div className='movie1 Text-Style-19'>{{ movie.title }}</div>
                <div className='movie2'>{{ movie.year }}</div>
                <div className='movie3'>{{ movie.rating + "/10 - " + Math.floor(movie.runtime / 60) + "h" +
                    movie.runtime % 60 + 'm'
                }}</div>
              </div>

              <div className='genre-container'>

                <div v-for="gerne in movie.gernes" class="gerne">{{ gerne }}</div>
              </div>

            </div>

            <div className='horizontal-rule'></div>

            <img v-if="!movie.yt_trailer_code" alt="large_cover" :src="movie.large_cover_image" />
            <div v-if="movie.yt_trailer_code">
              <iframe :src="'https://www.youtube.com/embed/' + movie.yt_trailer_code"></iframe>
            </div>


            <div className='summary'>
              {{ movie.summary }}
            </div>

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movie.slug.toLowerCase().split('-').join('_') + '/medium-screenshot1.jpg'" />

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movie.slug.toLowerCase().split('-').join('_') + '/medium-screenshot2.jpg'" />

            <img alt='cover_1' :src="'https://yts.torrentbay.to/assets/images/movies/' +
            movie.slug.toLowerCase().split('-').join('_') + '/medium-screenshot3.jpg'" />


          </div>
          <button className='button close' onClick={onClose}>X</button>
          <button className='button next' onClick={nextMovie}>ᐳ</button>
          <button className='button prev' onClick={prevMovie}>ᐸ</button>
        </Teleport>
      </div>
    </div>


  </div>


</template>