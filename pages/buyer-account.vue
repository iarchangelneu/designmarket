<template>
    <div class="account">
        <h1>личный кабинет</h1>

        <div class="tabs d-flex align-items-center justify-content-end">

            <button :class="[{ 'active': tabs == 0 }]" @click="tabs = 0">МОИ ПОКУПКИ</button>
            <button :class="[{ 'active': tabs == 1 }]" @click="tabs = 1">ТРАНЗАКЦИИ</button>
            <button :class="[{ 'active': tabs == 2 }, { 'active': tabs == 4 }]" @click="tabs = 2">ОБРАТНАЯ СВЯЗЬ</button>
            <button :class="[{ 'active': tabs == 3 }]" @click="tabs = 3">АККАУНТ</button>
        </div>

        <div class="mysales" v-if="tabs == 0">
            <div class="products__list" v-if="test">
                <div class="products__item d-flex">
                    <span>1.</span>
                    <div class="product__img">
                        <img src="@/assets/img/products.png" class="img-fluid" alt="">
                    </div>

                    <div class="product__desc w-100">
                        <div class="d-flex justify-content-between">
                            <div>
                                <p>
                                    шаблон сайта доставка еды
                                </p>
                                <span>Дата покупки: 01.08.23</span>
                                <h3>АВТОР:
                                    <small>Александр Иванов</small>
                                </h3>
                            </div>
                            <small>11 540 ₸</small>
                        </div>
                        <div class="d-flex align-items-center justify-content-end product__links">
                            <NuxtLink @click='tabs = 4' style="cursor: pointer;">ЧАТ С ПРОДАВЦОМ</NuxtLink>
                            <NuxtLink to="/product">СКАЧАТЬ ФАЙЛ</NuxtLink>
                        </div>
                    </div>
                </div>
                <div class="products__item d-flex">
                    <span>2.</span>
                    <div class="product__img">
                        <img src="@/assets/img/products.png" class="img-fluid" alt="">
                    </div>

                    <div class="product__desc w-100">
                        <div class="d-flex justify-content-between">
                            <div>
                                <p>
                                    шаблон сайта доставка еды
                                </p>
                                <span>Дата покупки: 01.08.23</span>
                                <h3>АВТОР:
                                    <small>Александр Иванов</small>
                                </h3>
                            </div>
                            <small>11 540 ₸</small>
                        </div>
                        <div class="d-flex align-items-center justify-content-end product__links">
                            <NuxtLink @click='tabs = 4' style="cursor: pointer;">ЧАТ С ПРОДАВЦОМ</NuxtLink>
                            <NuxtLink to="/product">СКАЧАТЬ ФАЙЛ</NuxtLink>
                        </div>
                    </div>
                </div>
                <div class="products__item d-flex ">
                    <span>3.</span>
                    <div class="product__img">
                        <img src="@/assets/img/products.png" class="img-fluid" alt="">
                    </div>

                    <div class="product__desc w-100">
                        <div class="d-flex justify-content-between">
                            <div>
                                <p>
                                    шаблон сайта доставка еды
                                </p>
                                <span>Дата покупки: 01.08.23</span>
                                <h3>АВТОР:
                                    <small>Александр Иванов</small>
                                </h3>
                            </div>
                            <small>11 540 ₸</small>
                        </div>
                        <div class="d-flex align-items-center justify-content-end product__links">
                            <NuxtLink @click='tabs = 4' style="cursor: pointer;">ЧАТ С ПРОДАВЦОМ</NuxtLink>
                            <NuxtLink to="/product">СКАЧАТЬ ФАЙЛ</NuxtLink>
                        </div>
                    </div>
                </div>
            </div>
            <div class="products__empty" v-if="!test">
                <div class="text-center">
                    <h2>У ВАС ПОКА ЧТО НЕ БЫЛО ПОКУПОК<br>
                        ПЕРЕЙТИ К ПОКУПКАМ</h2>

                    <NuxtLink to="/catalog">
                        Каталог
                    </NuxtLink>
                </div>
            </div>
        </div>
        <div class="chatlist d-flex" v-if="tabs == 2">
            <div class="chatlist__item">
                <div class="d-flex justify-content-between text">
                    <h3>alex.ivanov@gmail.com</h3>
                    <small>23.07.2023 14:47</small>
                </div>

                <div class="text-right">
                    <button @click="tabs = 4">ОТКРЫТЬ ЧАТ</button>
                </div>
            </div>
            <div class="chatlist__item">
                <div class="d-flex justify-content-between text">
                    <h3>alex.ivanov@gmail.com</h3>
                    <small>23.07.2023 14:47</small>
                </div>

                <div class="text-right">
                    <button @click="tabs = 4">ОТКРЫТЬ ЧАТ</button>
                </div>
            </div>
            <div class="chatlist__item">
                <div class="d-flex justify-content-between text">
                    <h3>alex.ivanov@gmail.com</h3>
                    <small>23.07.2023 14:47</small>
                </div>

                <div class="text-right">
                    <button @click="tabs = 4">ОТКРЫТЬ ЧАТ</button>
                </div>
            </div>
            <div class="chatlist__item">
                <div class="d-flex justify-content-between text">
                    <h3>alex.ivanov@gmail.com</h3>
                    <small>23.07.2023 14:47</small>
                </div>

                <div class="text-right">
                    <button @click="tabs = 4">ОТКРЫТЬ ЧАТ</button>
                </div>
            </div>
        </div>
        <div class="chatempty text-center" v-if="!test">
            <h3>У ВАС ПОКА НЕ БЫЛО ЧАТОВ</h3>
        </div>

        <form class="user">
            <div class="user__info d-flex justify-content-center">
                <div>
                    <label for="email">E-mail</label>
                    <input type="email" name="email" id="email" placeholder="Ваш e-mail">
                </div>
                <div>
                    <label for="password">Пароль</label>
                    <input type="password" name="password" id="password" placeholder="Ваш пароль">
                </div>
            </div>
            <div class="text-center">
                <button type="button">ВЫЙТИ ИЗ АККАУНТА</button>
            </div>
        </form>
        <TheTrans v-if="tabs == 1"></TheTrans>
        <TheMessanger v-if="tabs == 4"></TheMessanger>
    </div>
</template>
<script>
export default {
    data() {
        return {
            tabs: 3,
            test: true,
        }
    }
}
</script>
<script setup>

useSeoMeta({
    title: 'Личный кабинет | Themes',
    ogTitle: 'Личный кабинет | Themes',
    description: 'Личный кабинет | Themes',
    ogDescription: 'Личный кабинет | Themes',
})
</script>
<style scoped>
.user button {
    margin-top: 40px;
    background: transparent;
    border-radius: 50px;
    border: 3px solid #000;
    padding: 17px 73px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.user button:hover {
    color: #fff;
    background: #000;
}

.user__info {
    gap: 0 20px;
}

.user__info label {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    display: block;
}

.user__info input {
    border-radius: 10px;
    border: 3px solid #000;
    background: transparent;
    padding: 17px 20px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    font-family: var(--int);
    height: 60px;
    width: 29.167vw;
}

.user__info input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.user {
    margin-top: 54px;
}

.chatempty h3 {
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: 150%;
    font-family: var(--int);
    color: #000;
}

.chatempty {
    margin: 164px 0;
}

.chatlist__item button {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 17px 78px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    margin-top: 44px;
    transition: all .3s ease;
}

.chatlist__item button:hover {
    color: #fff;
    background: #000;
}

.chatlist__item .text {
    gap: 0 130px;
}

.chatlist__item small {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
}

.chatlist__item h3 {
    font-size: 32px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.chatlist__item {
    border-radius: 50px;
    background: #FFF;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    padding: 30px 42px;
}

.chatlist {
    margin-top: 54px;
    flex-wrap: wrap;
    gap: 40px;
}

.products__empty a {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 17px 5.625vw;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    margin-top: 54px;
    transition: all .3s ease;
}

.products__empty a:hover {
    color: #fff;
    background: #000;
}

.products__empty h2 {
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: 150%;
    font-family: var(--int);
    color: #000;
    margin-top: 107px;
    margin-bottom: 54px;
}

.product__desc h3 {
    white-space: nowrap;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    font-family: var(--int);
    margin-top: 30px;
}

.product__desc h3 small {
    white-space: nowrap;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    font-family: var(--int);
    margin-top: 30px;
    text-decoration: underline;
    text-transform: none;
}

.products__item {
    margin-bottom: 54px;
}

.product__links a {
    border-radius: 50px;
    border: 3px solid #000;
    padding: 17px 65px;
    background: transparent;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.product__links a:hover {
    color: #fff;
    background: #000;
}

.product__links {
    gap: 0 20px;
    margin-top: 100px;
}

.product__desc small {
    font-size: 36px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.product__desc p {
    margin-bottom: 30px;
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.product__desc span {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.product__desc {
    margin-left: 40px;
}

.products__list span {
    margin-right: 40px;
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.products__list {
    margin-top: 54px;
}

.product__img {
    border-radius: 30px;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    height: fit-content;
}

.tabs button {
    border: 3px solid #000;
    padding: 17px;
    background: transparent;
    transition: all .3s ease;
    flex: 1;
    max-width: 250px;

    font-size: 24px;
    font-style: normal;
    font-weight: 300;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
}

.tabs button:nth-child(n + 1) {
    border-left: 0;
}

.tabs button:first-child {
    border-left: 3px solid #000;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
}

.tabs button:last-child {
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
}

.active {
    background: #000 !important;
    color: #fff !important;
}

.account h1 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 54px;
}

.account {
    padding: 120px 100px 72px;
}
</style>