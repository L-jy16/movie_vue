<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <div class="header__title">
                <h1><a href="/">Lee.TV</a></h1>
                <nav>
                    <ul>
                        <li><a href="#">추천 영화 Top10</a></li>
                        <li><a href="#">최신 영화 Top10</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
    <main id="main">
        <DetailIntro v-if="movieBasic" :movieBasic="movieBasic" />
        <div class="Movie__Detail container">
            <div class="movie__detail__info">
                <DetailInfo class="detailinfo" v-if="movieInfo" :movieInfo="movieInfo" />
                <DetailKeyWord class="detailkeyword" v-if="movieKeyWord" :movieKeyWord="movieKeyWord" />
            </div>
            <div class="movie__detail__video">
                <DetailVideo class="detailvideo" v-if="movieVideo" :movieVideo="movieVideo" :movieBasic="movieBasic" />
            </div>
        </div>
        <DetailCredits v-if="movieCredits" :movieCredits="movieCredits" />
        <!-- <DetailReview v-if="movieReview" :movieReview="movieReview" /> -->
    </main>
</template>

<script>
import { onMounted, ref } from "vue"
import { useRoute } from "vue-router"
import axios from "axios";

import DetailIntro from "../components/detail/DetailIntro.vue";
import DetailVideo from "../components/detail/DetailVideo.vue";
import DetailInfo from "../components/detail/DetailInfo.vue";
import DetailKeyWord from "../components/detail/DetailKeyWord.vue";
import DetailCredits from "../components/detail/DetailCredits.vue";
// import DetailReview from "../components/detail/DetailReview.vue";

export default {
    name: "MovieDetailPage",

    components: {
        DetailIntro,
        DetailVideo,
        DetailInfo,
        DetailKeyWord,
        DetailCredits,
        // DetailReview,
    },

    setup() {
        const movieBasic = ref(null);
        const movieVideo = ref(null);
        const movieInfo = ref(null);
        const movieKeyWord = ref(null);
        const movieCredits = ref(null);
        // const movieReview = ref(null);

        const route = useRoute();

        onMounted(async () => {
            const movieId = route.params.movieId;
            const apiKey = import.meta.env.VITE_API_KEY;
            const language = "ko-KR"

            try {
                const resMovieBasic = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}?language=${language}&api_key=${apiKey}`)
                movieBasic.value = resMovieBasic.data;
                console.log(resMovieBasic.data);

                const resMovieVideo = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}/videos?api_key=${apiKey}`)
                movieVideo.value = resMovieVideo.data;
                // console.log(resMovieVideo.data)

                const resMovieInfo = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}?language=${language}&api_key=${apiKey}`)
                movieInfo.value = resMovieInfo.data;
                // console.log(resMovieInfo.data);

                const resMovieKeyWord = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}/keywords?language=${language}&api_key=${apiKey}`)
                movieKeyWord.value = resMovieKeyWord.data;
                // console.log(resMovieKeyWord.data)

                const resMovieCreadits = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}/credits?language=${language}&api_key=${apiKey}`)
                movieCredits.value = resMovieCreadits.data;
                // console.log(resMovieCreadits.data)

                // const resMovieReview = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}/reviews?language=${language}&api_key=${apiKey}`)
                // movieReview.value = resMovieReview.data;
                // // console.log(resMovieReview.data)
            }
            catch (err) {
                console.log(err)
            }
        });
        return {
            movieBasic,
            movieVideo,
            movieInfo,
            movieKeyWord,
            movieCredits,
            // movieReview,
        }
    }
}
</script>

<style lang="scss">
.Movie__Detail {
    display: flex;
    flex-direction: row-reverse;
    justify-content: space-between;
    align-items: center;
    align-content: center;
    padding: 20px;

    .movie__detail__video {
        width: 49%;
        // height: 500px;

        img {
            margin-top: 10px;
        }
    }

    .movie__detail__info {
        width: 50%;
        display: flex;
        flex-direction: column;
    }
}

@media (max-width: 800px) {
    .Movie__Detail {
        display: block;

        .movie__detail__video {
            width: 100%;
            // display: none;
        }

        .movie__detail__info {
            width: 100%;
        }
    }
}
</style>