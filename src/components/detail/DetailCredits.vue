<template>
    <div class="detail__creadits">
        <div class="container">
            <h3>등장 인물</h3>
            <ul class="creadit__wrap scroll_style">
                <li class="creadit__member" v-for="creadit in movieCredits.cast" :key="creadit.id">
                    <img :src="'https://image.tmdb.org/t/p/w500' + creadit.profile_path" alt={{creadit.name}}>
                    <span>{{ creadit.name }}</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movieCredits: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss">
.detail__creadits {
    // padding: 20px;

    h3 {
        font-size: 1.8rem;
        margin-bottom: 20px;
        color: var(--black500);
    }

    .creadit__wrap {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        max-width: 100%; 
        margin-bottom: -20px;
        

        .creadit__member {
            // width: %;
            padding: 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
            img {
                width: auto;
                height: 200px;
                object-position: center;
            }

            span {
                margin-top: 10px;
            }
        }
    }
}
@media (max-width: 800px){
    .detail__creadits {

    h3 {
        font-size: 1.5rem;
    }

    .creadit__wrap {   
        .creadit__member {
            img {
                width: auto;
                height: 150px;
                object-position: center;
            }

            span {
                text-align: center;
                word-break: keep-all;
                margin-top: 10px;
                font-size: 0.8rme;
            }
        }
    }
}
}
</style>