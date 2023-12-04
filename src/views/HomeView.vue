<!-- 메인 이미지 https://www.pinterest.co.kr/pin/696861742370290071/ -->

<script setup>
import { ref, onMounted, watch } from 'vue';
import axios from 'axios';


const movies = ref([]);
const searchKeyword = ref('');

const fetchMovies = async (category) => {
  let url = 'https://api.themoviedb.org/3/movie/popular';

  switch (category) {
    case 'latest':
      url = 'https://api.themoviedb.org/3/movie/now_playing';
      break;
    case 'popular':
      url = 'https://api.themoviedb.org/3/movie/popular';
      break;
    case 'upcoming':
      url = 'https://api.themoviedb.org/3/movie/upcoming'
      break;
    case 'toprated':
      url = 'https://api.themoviedb.org/3/movie/top_rated'
      break;
  }

  try {
    const response = await axios.get(url, {
      params: {
        api_key: '0c4dd2f0f12354d7b0874a5d69824380',
        language: 'ko-KR',
        page: '1',
      }
    })
    console.log(response)
    movies.value = response.data.results;
    console.log(movies)
  } catch (err) {
    console.log(err)
  }
}
const serachMovies = async () => {
  try {
    const response = await axios.get('https://api.themoviedb.org/3/search/movie', {
      params: {
        api_key: '0c4dd2f0f12354d7b0874a5d69824380',
        language: 'ko-KR',
        query: searchKeyword.value
      }
    });
    movies.value = response.data.results;
  } catch (err) {
    console.error(err);
  }
}

onMounted(async () => {
  await fetchMovies('latest');
});
</script>

<template>
  <HeaderSection />
  <main id="main" role="main">
    <div class="container">
      <div class="movie__inner">

        <section class="movie__search">
          <h2 class="blind">검색하기</h2>
          <input type="search" v-model="searchKeyword" placeholder="검색어를 입력해주세요!" @keyup.enter="serachMovies">
          <button type="submit" @click="serachMovies">검색</button>
        </section>
        <!-- //movie__search -->

        <div class="movie__tag">
          <ul>
            <li><a href="#" @click="fetchMovies('latest')">최신 영화</a></li>
            <li><a href="#" @click="fetchMovies('popular')">인기 영화</a></li>
            <li><a href="#" @click="fetchMovies('upcoming')">개봉 예정</a></li>
            <li><a href="#" @click="fetchMovies('toprated')">최고 평점</a></li>
          </ul>
        </div>
        <!-- //movie__tag -->

        <section class="movie__cont">
          <h2 class="blind">영화</h2>
          <div class="movie play__icon" v-for="movie in movies" :key="movie.id">
            <a :href="'/detail/' + movie.id">
              <img :src="'https://image.tmdb.org/t/p/w500' + movie.poster_path" :alt="movie.title">
            </a>
          </div>
        </section>
        <!-- //movie__cont -->

      </div>
    </div>
  </main>
  <FooterSection />
</template>

<script>
import HeaderSection from '@/components/section/HeaderSection.vue';
import FooterSection from '@/components/section/FooterSection.vue';

import MovieSearch from '@/components/contents/MovieSearch.vue';
import MovieTag from '@/components/contents/MovieTag.vue';
import MovieCont from '@/components/contents/MovieCont.vue';

export default {
  name: "MovieHomepage",
  components: {
    HeaderSection,
    FooterSection,
    MovieSearch,
    MovieTag,
    MovieCont
  },
  data() {
    return {
      movies: [],

    }
  },
  methods: {
    async search(query) {
      try {
        const response = await fetch(`https://api.themoviedb.org/3/search/movie>api_key=0c4dd2f0f12354d7b0874a5d69824380&language:ko-KR&query=${query}`)
        const result = await response.json();
        console.log(result);
      } catch (error) {
        console.log(error);
      }
    },
    async tags(query) {
      try {
        const response = await fetch(`https://api.themoviedb.org/3/search/movie>api_key=0c4dd2f0f12354d7b0874a5d69824380&language:ko-KR&query=${query}`)
        const result = await response.json();
        console.log(result);
      } catch (error) {
        console.log(error);
      }
    }
  }
}
</script>

<style lang="scss">
.movie__inner {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;

  .movie__search {
    width: 48%;
    margin: 20px 10px 20px 0px;
    display: flex;
    justify-content: flex-end;
    position: relative;


    input {
      padding: 1rem 2rem;
      width: 100%;
      background-color: var(--black);
      color: var(--white);
      border: 1px solid var(--black500);
      border-radius: 50px;
    }

    button {
      background-color: var(--black);
      color: var(--white);
      position: absolute;
      content: '';
      top: 18px;
      right: 20px;

      &:hover {
        color: var(--black500);
      }
    }
  }

  .movie__tag {
    width: 48%;

    ul {
      display: flex;

      li {
        a {
          display: inline-block;
          margin: 20px 10px 20px 0;
          padding: 0.5rem 1rem;
          color: var(--black500);

          &:hover {
            color: var(--white);
            border-bottom: 3px solid var(--red);
            box-sizing: border-box;
          }
        }
      }
    }
  }

  .movie__cont {
    width: 100%;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;

    .movie {
      width: 24%;
      margin-bottom: 20px;

    }
  }
}
</style>