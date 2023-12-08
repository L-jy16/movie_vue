<template>
    <div class="detail__info">
        <div class="container">
            <div class="deinfo__cont">
                <div class="vidoedeinfo__right">
                    <h3 class="vidoedeinfo__title">
                        {{ movieInfo.title }}
                    </h3>

                    <div class="vidoedeinfo__date">
                        {{ movieInfo.release_date }}
                    </div>
                    <div class="vidoedeinfo__review">
                        ♥ {{ movieInfo.vote_average }}
                    </div>
                    <div class="vidoedeinfo__runtime">
                        {{ movieInfo.runtime }}분
                    </div>
                </div>
                <div class="vidoedeinfo__desc">
                    {{ movieInfo.overview }}
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    props: {
        movieInfo: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss">
.detail__info {
    margin-top: 30px;

    .deinfo__cont {
        padding: 20px;

        .vidoedeinfo__right {
            display: flex;
            align-items: flex-end;

            .vidoedeinfo__title {
                font-size: 3rem;
                font-weight: bold;
                margin-right: 1vw;
            }

            .vidoedeinfo__date {
                font-size: 1.2rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }

            .vidoedeinfo__review {
                font-size: 1.2rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }

            .vidoedeinfo__runtime {
                font-size: 1.2rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }
        }

        .vidoedeinfo__desc {
            font-size: 1.8rem;
            margin-top: 20px;
            line-height: 1.6;
            word-break: keep-all;
        }
    }
}

@media (max-width: 1450px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                .vidoedeinfo__title {
                    font-size: 2.8rem;
                }

                .vidoedeinfo__date {
                    font-size: 1.2rem;
                }

                .vidoedeinfo__review {
                    font-size: 1.2rem;

                }

                .vidoedeinfo__runtime {
                    font-size: 1.2rem;

                }
            }

            .vidoedeinfo__desc {
                font-size: 1.6rem;

            }
        }
    }
}

@media (max-width: 900px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                .vidoedeinfo__title {
                    font-size: 2.6rem;
                }

                .vidoedeinfo__date {
                    font-size: 1rem;
                }

                .vidoedeinfo__review {
                    font-size: 1rem;

                }

                .vidoedeinfo__runtime {
                    font-size: 1rem;

                }
            }

            .vidoedeinfo__desc {
                font-size: 1.3rem;

            }
        }
    }
}

@media (max-width: 670px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                flex-wrap: wrap;

                .vidoedeinfo__title {
                    width: 100%;
                    font-size: 2.2rem;
                }

                .vidoedeinfo__date {
                    margin-top: 10px;
                    font-size: 0.8rem;
                }

                .vidoedeinfo__review {
                    font-size: 0.8rem;
                    margin-top: 10px;
                }

                .vidoedeinfo__runtime {
                    font-size: 0.8rem;
                    margin-top: 10px;
                }
            }

            .vidoedeinfo__desc {
                font-size: 1rem;
                margin-top: 10px;
            }
        }
    }
}
</style>