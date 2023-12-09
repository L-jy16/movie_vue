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

        .vidoedeinfo__right {
            display: flex;
            align-items: flex-end;

            .vidoedeinfo__title {
                font-size: 2.5rem;
                font-weight: bold;
                margin-right: 1vw;
            }

            .vidoedeinfo__date {
                font-size: 1rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }

            .vidoedeinfo__review {
                font-size: 1rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }

            .vidoedeinfo__runtime {
                font-size: 1rem;
                margin-right: 15px;
                word-break: keep-all;
                color: var(--black500);
            }
        }

        .vidoedeinfo__desc {
            font-size: 1.5rem;
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
                    font-size: 2.3rem;
                }

                .vidoedeinfo__date {
                    font-size: 0.8rem;
                }

                .vidoedeinfo__review {
                    font-size: 0.8rem;

                }

                .vidoedeinfo__runtime {
                    font-size: 0.8rem;

                }
            }

            .vidoedeinfo__desc {
                font-size: 1.3rem;

            }
        }
    }
}

@media (max-width: 1130px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                .vidoedeinfo__title {
                    font-size: 2.1rem;
                }

                .vidoedeinfo__date {
                    font-size: 0.7rem;
                }

                .vidoedeinfo__review {
                    font-size: 0.7rem;

                }

                .vidoedeinfo__runtime {
                    font-size: 0.7rem;

                }
            }

            .vidoedeinfo__desc {
                font-size: 1.1rem;

            }
        }
    }
}

@media (max-width: 940px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                .vidoedeinfo__title {
                    font-size: 1.6rem;
                    margin-right: 5px;
                }

                .vidoedeinfo__date {
                    font-size: 0.7rem;
                    margin-right: 5px;
                }

                .vidoedeinfo__review {
                    font-size: 0.7rem;
                    margin-right: 5px;

                }

                .vidoedeinfo__runtime {
                    font-size: 0.7rem;
                    margin-right: 5px;

                }
            }

            .vidoedeinfo__desc {
                font-size: 1.0rem;
                margin-top: 10px;
            }
        }
    }
}

@media (max-width: 800px) {
    .detail__info {
        .deinfo__cont {
            .vidoedeinfo__right {
                flex-wrap: wrap;

                .vidoedeinfo__title {
                    width: 100%;
                    font-size: 2.4rem;
                }

                .vidoedeinfo__date {
                    margin-top: 15px;
                    font-size: 1rem;
                }

                .vidoedeinfo__review {
                    font-size: 1rem;
                    margin-top: 15px;
                }

                .vidoedeinfo__runtime {
                    font-size: 1rem;
                    margin-top: 15px;
                }
            }

            .vidoedeinfo__desc {
                font-size: 1rem;
                margin-top: 20px;
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