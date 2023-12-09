<template>
    <div class="detail__trailer">
        <div class="detail__video">
            <!-- <iframe v-if="DetailVideoFind" width="100%" height="500" :src="DetailVideoUrl" frameborder="0" allowfullscreen></iframe> -->          
        </div>
    </div>
</template>
  
<script>

export default {
    props: {
        movieVideo: {
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
            return officialTrailer ? `https://www.themoviedb.org/video/play?key=${officialTrailer.key}` : '';
        }
    },
    methods: {
        getVedioId(url) {
            const match = url.match(/[?&]v=([^&]+)/);
            return match ? match[1] : '';
        }
    }
}
</script>
  
<style lang="scss">
.detail__trailer {


    .detail__video {
        width: 100%;
        overflow: hidden;
    }
}
</style>