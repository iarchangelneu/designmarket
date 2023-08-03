<template>
    <section>
        <div class="main">
            <swiper :slidesPerView="1" :pagination="pagination" :modules="modules" class="mySwiper" :navigation="navigation"
                ref="swiper">
                <!-- Слайды -->
                <swiper-slide>
                    <div class="d-flex">
                        <img class="img-fluid" src="@/assets/img/mainsl.png" alt="" style="">

                        <div class="ml-5">
                            <h1>Шаблон сайта строительной компании</h1>

                            <div>
                                <button>ПОДРОБНЕЕ</button>
                            </div>
                        </div>
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="d-flex">
                        <img class="img-fluid" src="@/assets/img/mainsl.png" alt="" style="">

                        <div class="ml-5">
                            <h1>Шаблон сайта строительной компании</h1>

                            <div>
                                <button>ПОДРОБНЕЕ</button>
                            </div>
                        </div>
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="d-flex">
                        <img class="img-fluid" src="@/assets/img/mainsl.png" alt="" style="">

                        <div class="ml-5">
                            <h1>Шаблон сайта строительной компании</h1>

                            <div>
                                <button>ПОДРОБНЕЕ</button>
                            </div>
                        </div>
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="d-flex">
                        <img class="img-fluid" src="@/assets/img/mainsl.png" alt="" style="">

                        <div class="ml-5">
                            <h1>Шаблон сайта строительной компании</h1>

                            <div>
                                <button>ПОДРОБНЕЕ</button>
                            </div>
                        </div>
                    </div>
                </swiper-slide>


                <!-- Навигация -->
                <div class="navslider d-flex align-items-center">
                    <div class="swiper-button-prev2">
                        <img class="img-fluid" src="@/assets/img/prev.svg">
                    </div>
                    <div class="cal">
                        <div class="swiper-pagination2"></div>
                    </div>


                    <div class="swiper-button-next2">
                        <img class="img-fluid" src="@/assets/img/next.svg">
                    </div>
                </div>
            </swiper>
        </div>

        <div class="sales">
            <h1>Акции и предложения</h1>
            <swiper :slidesPerView="1" :pagination="pagination__sales" :modules="modules" class="mySwiper2">
                <swiper-slide>
                    <div class="d-flex">
                        <div class="bigimg">
                            <img src="@/assets/img/sale1.png" alt="">
                            <div class="smallhover">
                                <div class="hvrbtn">
                                    <button class="lala">ПОДРОБНЕЕ</button>
                                </div>
                                <div class="sale2">
                                    <span>30%</span>
                                </div>
                            </div>
                        </div>
                        <div class="smallimgs">
                            <div class="smallsh">
                                <img src="@/assets/img/sale2.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale3.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale4.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale5.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                </swiper-slide>
                <swiper-slide>
                    <div class="d-flex">
                        <div class="bigimg">
                            <img src="@/assets/img/sale1.png" alt="">
                            <div class="smallhover">
                                <div class="hvrbtn">
                                    <button class="lala">ПОДРОБНЕЕ</button>
                                </div>
                                <div class="sale2">
                                    <span>30%</span>
                                </div>
                            </div>
                        </div>
                        <div class="smallimgs">
                            <div class="smallsh">
                                <img src="@/assets/img/sale2.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale3.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale4.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>
                            <div class="smallsh">
                                <img src="@/assets/img/sale5.png" alt="">
                                <div class="smallhover">
                                    <div class="hvrbtn">
                                        <button>ПОДРОБНЕЕ</button>
                                    </div>
                                    <div class="sale">
                                        <span>30%</span>
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                </swiper-slide>


            </swiper>
            <div class="sales-pagination"></div>
        </div>

        <div class="categories">
            <h1>категории</h1>

            <div class="category d-flex">
                <div class="cats">
                    <div class="cat d-flex align-items-center">

                        <img class="img-fluid" src="@/assets/img/cat1.svg" alt="">
                        <span>ОДЕЖДА И МОДА</span>
                    </div>
                    <div class="cat d-flex align-items-center">
                        <img class="img-fluid" src="@/assets/img/cat2.svg" alt="">
                        <span>ПРЕДПРИЯТИЯ</span>
                    </div>
                </div>
                <div class="bigcat">
                    <div class="text-center">
                        <img class="img-fluid" src="@/assets/img/cat3.svg" alt="">
                        <span class="d-block">ЕДА И РЕСТОРАНЫ</span>
                    </div>
                </div>
                <div class="cats">
                    <div class="cat d-flex align-items-center">

                        <img class="img-fluid" src="@/assets/img/cat4.svg" alt="">
                        <span>ОБРАЗОВАНИЕ</span>
                    </div>
                    <div class="cat d-flex align-items-center">
                        <img class="img-fluid" src="@/assets/img/cat5.svg" alt="">
                        <span>ПУТЕШЕСТВИЯ</span>
                    </div>
                </div>
                <div class="bigcat mr-0">
                    <div class="text-center">
                        <img class="img-fluid" src="@/assets/img/cat6.svg" alt="">
                        <span class="d-block">РАЗВЛЕЧЕНИЯ</span>
                    </div>
                </div>
            </div>

            <div class="category d-flex" style="margin-top: 17px;">
                <div class="bigcat ml-0">
                    <div class="text-center">
                        <img class="img-fluid" src="@/assets/img/cat3.svg" alt="">
                        <span class="d-block">ЕДА И РЕСТОРАНЫ</span>
                    </div>
                </div>
                <div class="cats">
                    <div class="cat d-flex align-items-center">

                        <img class="img-fluid" src="@/assets/img/cat1.svg" alt="">
                        <span>ОДЕЖДА И МОДА</span>
                    </div>
                    <div class="cat d-flex align-items-center">
                        <img class="img-fluid" src="@/assets/img/cat2.svg" alt="">
                        <span>ПРЕДПРИЯТИЯ</span>
                    </div>
                </div>
                <div class="bigcat">
                    <div class="text-center">
                        <img class="img-fluid" src="@/assets/img/cat6.svg" alt="">
                        <span class="d-block">РАЗВЛЕЧЕНИЯ</span>
                    </div>
                </div>
                <div class="cats">
                    <div class="cat d-flex align-items-center">

                        <img class="img-fluid" src="@/assets/img/cat4.svg" alt="">
                        <span>ОБРАЗОВАНИЕ</span>
                    </div>
                    <div class="cat d-flex align-items-center">
                        <img class="img-fluid" src="@/assets/img/cat5.svg" alt="">
                        <span>ПУТЕШЕСТВИЯ</span>
                    </div>
                </div>

            </div>
        </div>

        <div class="textblock d-flex">
            <img src="@/assets/img/textblock.png" class="img-fluid" alt="">

            <div>
                <h2>Зарабатывайте с помощью своих дизайнов на нашей платформе</h2>
                <p>Themes поможет дизайнерам успешно монетизировать свои уникальные работы.
                </p>
                <p> Простой интерфейс позволит быстро загрузить работу и начать продажи шаблонов дизайна, не прерывая
                    творческий процесс.</p>

                <button>узнать подробнее</button>
            </div>
        </div>

        <div class="popular">
            <h1>популярные дизайны</h1>

            <div class="popular__block d-flex">
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>доставка еды</h3>
                    </div>
                    <img src="@/assets/img/pop1.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>автосалон</h3>
                    </div>
                    <img src="@/assets/img/pop2.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>уходовая косметика</h3>
                    </div>
                    <img src="@/assets/img/pop3.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>школа программирования</h3>
                    </div>
                    <img src="@/assets/img/pop4.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>доставка еды</h3>
                    </div>
                    <img src="@/assets/img/pop1.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>
                <NuxtLink to="/" class="popular__item">
                    <div class="w-100 text-center pop__type">
                        <h3>автосалон</h3>
                    </div>
                    <img src="@/assets/img/pop2.png" alt="">

                    <div class="price">
                        11 540 ₸
                    </div>
                </NuxtLink>

            </div>

            <div class="text-center linktoshop">
                <NuxtLink to="/">Посмотреть все</NuxtLink>
            </div>
        </div>


    </section>
</template>
  
<script>
import { Navigation, Pagination } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    data() {
        return {
            modules: [Navigation, Pagination],
            navigation: {
                prevEl: '.swiper-button-prev2',
                nextEl: '.swiper-button-next2',
            },
            pagination: {
                el: '.swiper-pagination2',
                type: 'fraction',

            },
            pagination__sales: {
                el: '.sales-pagination',
                clickable: true,
            },
            currentSlideIndex: 0,
            totalSlides: 0,
        };
    },
    methods: {

    },
    watch: {

    },


};
</script>
<script setup>
useSeoMeta({
    title: 'Главная | Themes',
    ogTitle: 'Главная | Themes',
    description: 'Главная | Themes',
    ogDescription: 'Главная | Themes',
})
</script>
<style>
.lala {
    border-radius: 50px !important;
    border: 3px solid #FFF !important;
    padding: 16px 41px !important;

    font-size: 32px !important;
}

.linktoshop {
    margin-top: 48px;
}

.linktoshop a {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 13px 26px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;

    transition: all .3s ease;
}

.linktoshop a:hover {
    color: #fff;
    background: #000;
}

.popular__item {
    position: relative;
}

.price {
    position: absolute;
    right: 0;
    bottom: 0;
    border-radius: 50px 0px;
    background: linear-gradient(90deg, #39007F 0%, #15D0FF 100%);
    padding: 9px 26px;

    color: #fff;
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
}

.pop__type {
    border-radius: 50px 50px 0px 0px;
    background: #000;
    padding: 15px 0;
}

.pop__type h3 {
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #fff;
    margin: 0;
}

a {
    text-decoration: none !important;
}

.popular__block {
    flex-wrap: wrap;
    gap: 40px;
}

.popular {
    margin-top: 72px;
    margin-bottom: 72px;
}

.popular h1 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 48px;
}

.textblock button {
    margin-top: 58px;
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 13px 26px;

    color: #000;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    transition: all .3s ease;
}

.textblock button:hover {
    color: #fff;
    background: #000;
}

.textblock h2 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: 130%;
    color: #000;
    font-family: var(--int);
    margin-bottom: 48px;
}

.textblock p {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
}

.textblock p:first-of-type {
    margin-bottom: 30px;
}

.textblock {
    gap: 0 40px;
}

.textblock {
    margin-top: 72px;
}

.bigcat {
    width: 21.615vw;
    height: 16.51vw;
    padding: 40px 55px 52px;
    border-radius: 50px;
    background: #FFF;
    box-shadow: 0px 0px 15px 0px rgba(47, 59, 163, 0.20);
    margin: 0 20px;
}

.bigcat span {
    white-space: nowrap;
    margin-top: 30px;
}

svg {
    display: inline-block;
}

stop {
    transition: .4s ease;
}

/* Use the colors to transition to */
svg:hover stop:first-child {
    stop-color: #1EBEE0;
}

svg:hover stop:last-child {
    stop-color: #952491;
}

.bigcat,
.cat {
    cursor: pointer;
}

.cat span,
.bigcat span {
    font-size: 1.667vw;
    font-style: normal;
    font-weight: 400;
    line-height: 140%;
    font-family: var(--int);
    color: #000;
}

.cat {
    gap: 20px;
    border-radius: 50px;
    background: #FFF;
    box-shadow: 0px 0px 15px 0px rgba(47, 59, 163, 0.20);
    padding: 30px 25px 30px 35px;
    width: 21.615vw;
    height: 7.813vw;
}

.cats .cat:nth-child(1) {
    margin-bottom: 17px;
}

.categories h1 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 48px;
}



.sale span {
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    color: #fff;
    font-family: var(--int);
    padding: 7px 25px;
    display: block;
}


.sale {
    border-radius: 0px 40px 0px 50px;
    background: linear-gradient(90deg, #39007F 0%, #15D0FF 100%);
    position: absolute;
    left: 0;
    bottom: 0;
}

.sale2 span {
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    color: #fff;
    font-family: var(--int);
    padding: 7px 25px;
}

.sale2 {
    border-radius: 0px 40px 0px 50px;
    background: linear-gradient(90deg, #39007F 0%, #15D0FF 100%);
    position: absolute;
    left: 0;
    bottom: 0;
}

.hvrbtn {
    display: flex;
    justify-content: center;
    align-items: center;
}

.smallhover {
    display: flex;
    justify-content: center;
    align-items: center;

    position: absolute;
    opacity: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50px;
    backdrop-filter: blur(3.5px);
    transition: all .3s ease;
    overflow: hidden;
}

.smallhover::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.3);
    /* Цвет и прозрачность */
    z-index: -1;
    pointer-events: none;
    /* Чтобы псевдоэлемент не мешал взаимодействию с содержимым */
    transition: all .3s ease;
}

.smallhover button {
    border-radius: 50px;
    border: 3px solid #FFF;
    padding: 16px 41px;
    background: transparent;

    color: #fff;
    text-transform: uppercase;
    transition: all .3s ease;
}

.smallhover button:hover {
    color: #000;
    background: #fff;
}

.smallsh {
    position: relative;
    border-radius: 50px;

}

.bigimg {
    position: relative;
    border-radius: 50px;
}


.smallsh:hover .smallhover,
.bigimg:hover .smallhover {
    opacity: 1;
}

.swiper-pagination-bullet {
    opacity: 1;
    transition: all .3s ease;
    width: 29px;
    border-radius: 20px;
}

.swiper-pagination-bullet-active {
    background: linear-gradient(to right, #39007F, #15D0FF);
    width: 80px;
    border-radius: 20px;
    transition: all .3s ease;
}

.sales-pagination {
    position: absolute;
    right: 0;
    left: auto !important;
    z-index: 100;
    width: auto !important;
}

.smallimgs {
    display: flex;
    flex-wrap: wrap;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    grid-template-areas: ". .";
    margin-left: 20px;
}

.sales h1 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    margin-bottom: 47px;
}

.sales {
    margin-top: 47px;
    padding-bottom: 40px;
    position: relative;
}

.cal {
    margin: 0 20px;
}

.main button {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 18px 80px;

    color: #000;
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    transition: all .3s ease;
}

.main button:hover {
    color: #fff;
    background: #000;
}

.mySwiper,
.mySwiper2 {
    position: relative;
}

.main h1 {
    font-family: var(--int);
    font-size: 80px;
    font-style: normal;
    font-weight: 500;
    line-height: 110%;
    color: #000;
    max-width: 642px;
}

.counter {
    width: 100px;
}

.navslider {
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: 100;
}

.navslider img {
    cursor: pointer;
}

.swiper-pagination2 {
    font-family: var(--int);
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;

}

section {
    padding: 120px 100px 0;
}

.main img {
    max-width: 1060px;
    max-height: 614px;
}
</style>