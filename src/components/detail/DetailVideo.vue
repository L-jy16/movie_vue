<template>
    <div class="detail__trailer">
        <div class="detail__video" :style="{ paddingBottom: videoAspectRatio }">
            <iframe v-if="DetailVideoFind" :src="DetailVideoUrl" frameborder="0" allowfullscreen></iframe>
            <img v-else :src="'https://image.tmdb.org/t/p/w500' + movieBasic.backdrop_path" alt="{{ movieBasic.title }}">
        </div>
    </div>
</template>
  
<script>

export default {
    props: {
        movieVideo: {
            type: Object,
            required: true
        },
        movieBasic: {
            type: Object,
            required: true
        }
    },

    computed: {
        DetailVideoFind() {
            return this.movieVideo.results.some(item => item.name === "Official Trailer" && item.type === "Trailer");
        },
        DetailVideoUrl() {
            const officialTrailer = this.movieVideo.results.find(item => item.name === "Official Trailer" && item.type === "Trailer");
            return officialTrailer ? `https://www.youtube.com/embed/${officialTrailer.key}` : '';
        },
        videoAspectRatio() {
            return this.DetailVideoFind ? "56.25%" : "0";
        }
    }
}
</script>
  
<style lang="scss">
.detail__trailer {
    width: 100%;
    height: inherit;

    .detail__video {
        width: 100%;
        position: relative;

        img {
            width: 100%;
        }

        iframe {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
        }

    }
}
</style>