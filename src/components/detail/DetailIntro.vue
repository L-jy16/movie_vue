<template>
    <div class="detail__intro"
        :style="{ 'background-image': 'url(https://image.tmdb.org/t/p/w500' + movieBasic.backdrop_path + ')' }">
        <div class="container">
            <div class="deintro__cont">
                <div class="deintro__poster">
                    <a><img :src="'https://image.tmdb.org/t/p/w500' + movieBasic.poster_path"
                            alt="{{ movieBasic.title }}"></a>
                </div>
                <div class="deintro__video">
                    <h3 class="vidoedeintro__title">
                        {{ movieBasic.title }}
                    </h3>
                    <div class="vidoedeintro__cont">
                        <div class="vidoedeintro__desc">
                            {{ movieBasic.tagline }}
                        </div>
                        <div class="vidoedeintro__date">
                            개봉일 : {{ movieBasic.release_date }}
                        </div>
                        <div class="vidoedeintro__review">
                            평점 : {{ movieBasic.vote_average }}
                        </div>
                        <div class="vidoedeintro__runtime">
                            상영 시간 : {{ movieBasic.runtime }}분
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movieBasic: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss">
.detail__intro {
    width: 100%;
    position: relative;
    overflow: hidden;
    background-position: center center;
    background-size: cover;
    display: flex;
    align-items: center;
    background-repeat: no-repeat;
    box-sizing: border-box;

    &::after {
        content: '';
        top: 0;
        left: 0;
        position: absolute;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.3);
        backdrop-filter: blur(15px);
        z-index: 1;
    }




    .deintro__cont {
        position: relative;
        width: 100%;
        display: flex;
        justify-content: space-between;
        padding: 30px 30px;
        box-sizing: border-box;
        z-index: 2;
        align-items: center;


        .deintro__poster {
            width: 35%;
        }

        .deintro__video {
            width: 55%;




            .vidoedeintro__title {
                font-size: 3rem;
                font-weight: bold;
                padding: 25px 0;
                border-bottom: 1px dashed var(--black500);
            }

            .vidoedeintro__cont {
                padding: 25px 0;

                .vidoedeintro__desc {
                    font-size: 1.8rem;
                    margin-top: 10px;
                    word-break: keep-all;
                }

                .vidoedeintro__date {
                    color: var(--black500);
                    margin-top: 10px;
                    word-break: keep-all;
                    font-size: 1rem;
                }

                .vidoedeintro__review {
                    color: var(--black500);
                    margin-top: 10px;
                    word-break: keep-all;
                    font-size: 1rem;
                }

                .vidoedeintro__runtime {
                    color: var(--black500);
                    margin-top: 10px;
                    word-break: keep-all;
                    font-size: 1rem;
                }
            }

        }
    }
}

@media (max-width: 900px) {
    .detail__intro {
        .deintro__cont {
            .deintro__poster {}

            .deintro__video {

                .vidoedeintro__title {
                    font-size: 2.8rem;
                }

                .vidoedeintro__cont {
                    // padding: 25px 0;

                    .vidoedeintro__desc {
                        font-size: 1.6rem;
                        margin-top: 5px;

                    }

                    .vidoedeintro__date {
                        margin-top: 5px;
                    }

                    .vidoedeintro__review {
                        margin-top: 5px;
                    }

                    .vidoedeintro__runtime {
                        margin-top: 5px;
                    }
                }
            }
        }
    }
}

@media (max-width: 670px) {
    .detail__intro {

        .deintro__cont {
            justify-content: center;
            flex-direction: column;

            .deintro__poster {
                width: 100%;
                align-items: center;
                text-align: center;

                a {

                    img {
                        width: 40%;
                    }
                }
            }

            .deintro__video {
                width: 100%;
                text-align: center;

                .vidoedeintro__title {
                    font-size: 2rem;
                    padding: 18px 0;
                }

                .vidoedeintro__cont {
                    // padding: 25px 0;
                    padding: 15px 0;

                    .vidoedeintro__desc {
                        font-size: 1.3rem;
                    }

                    .vidoedeintro__date {
                        font-size: 0.8rem;
                    }

                    .vidoedeintro__review {
                        font-size: 0.8rem;
                    }

                    .vidoedeintro__runtime {
                        font-size: 0.8rem;
                    }
                }
            }
        }
    }
}
</style>