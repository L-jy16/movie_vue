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
            <div class="header__intro"
                style="background-image: url(https://image.tmdb.org/t/p/w500/t5zCBSB5xMDKcDqe91qahCOUYVV.jpg);">
                <div class="container">
                    <div class="header__cont">
                        <div class="header__poster play__icon">
                            <a><img src="https://image.tmdb.org/t/p/w500/h3hhfWdBhdb2JLMZprQ1IvBe90h.jpg"
                                    alt="프레드의 피자가게"></a>
                        </div>
                        <div class="header__video">
                            <h3 class="video__title">
                                프레드의 피자가게
                            </h3>
                            <div class="vidoe__cont">
                                <div class="video__desc">
                                    "80년대에 아이들이 실종되고 폐업한지 오래된 프레디의 피자가게 그곳의 야간 경비 알바를 하게 된 ‘마이크'는 캄캄한 어둠만이 존재하는 줄 알았던 피자가게에서
                                    살아 움직이는 피자가게 마스코트 '프레디와 친구들’을 목격한다. 어딘가 기괴하고 섬뜩한 프레디와 친구들이 실체를 드러내기 시작하는데..."
                                </div>
                                <div class="date">
                                    개봉일 : 2023-10-25
                                </div>
                                <div class="review">
                                    평점 : 7.88
                                </div>
                                <div class="video__Characters">
                                    <ul>
                                        <li><img src="https://image.tmdb.org/t/p/w500/mT4nBq136sHYEJBjeoZzRGBIjxt.jpg"
                                                alt="Josh Hutcherson"></li>
                                        <li><img src="https://image.tmdb.org/t/p/w500//x8tDKAgxMKwaNJSd9RB75EIJnOD.jpg"
                                                alt="Piper Rubio"></li>
                                        <li><img src="https://image.tmdb.org/t/p/w500//lDYjEyqojUs2sF3CgdsOZ9vr2KL.jpg"
                                                alt="Elizabeth Lail"></li>
                                        <li><img src="https://image.tmdb.org/t/p/w500/51v6jsvzuAXYirIzdqcjLBp46d6.jpg"
                                                alt="Matthew Lillard"></li>
                                        <li><img src="https://image.tmdb.org/t/p/w500/njHHxFIJutnRsFM1c85PC8FBOzj.jpg"
                                                alt="Mary Stuart Masterson"></li>

                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss">
.header__title {
    display: flex;
    justify-content: space-between;
    padding: 10px 20px;
    align-items: center;

    h1 {
        font-size: 2rem;
        font-weight: bold;
        color: var(--red);
    }

    nav {
        ul {
            display: flex;
            flex-wrap: wrap;

            li {
                margin-left: 10px;

                a {
                    font-size: 1.2rem;
                    color: var(--black500);

                    &:hover {
                        color: var(--white);
                    }
                }
            }
        }
    }
}

.header__intro {
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




    .header__cont {
        position: relative;
        width: 100%;
        display: flex;
        justify-content: space-between;
        padding: 30px 30px;
        box-sizing: border-box;
        z-index: 2;
        align-items: center;


        .header__poster {
            width: 35%;
        }

        .header__video {
            width: 55%;




            .video__title {
                font-size: 2rem;
                font-weight: bold;
                padding: 25px 0;
                border-bottom: 1px dashed var(--black500);
            }

            .vidoe__cont {
                padding: 25px 0;

                .video__desc {
                    font-size: 0.8rem;
                    margin-top: 10px;

                }

                .date {
                    margin-top: 10px;
                }

                .review {
                    margin-top: 10px;
                }

                .video__Characters {
                    padding: 20px 0;

                    ul {
                        display: flex;
                        flex-wrap: wrap;
                        justify-content: space-between;

                        li {
                            width: 18%;
                            // background-color: #fff;
                        }
                    }
                }
            }

        }
    }
}

@media (max-width: 1100px) {
    .header__video {


        .video__title {
            font-size: 1.5rem;
            font-weight: bold;
            padding: 15px 0;
            border-bottom: 1px dashed var(--black500);
        }

        .vidoe__cont {
            // padding: 25px 0;

            .video__desc {
                font-size: 0.4rem;
                margin-top: 5px;

            }

            .date {
                margin-top: 5px;
            }

            .review {
                margin-top: 5px;
            }

            .video__Characters {
                padding: 20px 0;

                ul {
                    display: flex;
                    flex-wrap: wrap;
                    justify-content: space-between;

                    li {
                        width: 18%;
                        // background-color: #fff;
                    }
                }
            }
        }
    }
}

@media (max-width: 800px) {
    .header__title {

        h1 {
            font-size: 2rem;
            font-weight: bold;
            color: var(--red);
        }

        nav {
            ul {
                display: flex;
                flex-wrap: wrap;

                li {
                    margin-left: 10px;

                    a {
                        font-size: 0.8rem;
                        color: var(--black500);

                        &:hover {
                            color: var(--white);
                        }
                    }
                }
            }
        }
    }
}
</style>