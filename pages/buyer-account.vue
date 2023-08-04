<template>
    <div class="account">
        <h1>личный кабинет</h1>
        <div class="d-flex justify-content-between w-100 crack">
            <div v-if="tabs != 4"></div>
            <div class="backtochat" v-if="tabs == 4">
                <button @click="tabs = 2">
                    <img src="@/assets/img/backarrow.svg" alt="">
                    НАЗАД
                </button>
            </div>
            <div class="tabs d-flex align-items-center justify-content-end pc">

                <button :class="[{ 'active': tabs == 0 }]" @click="tabs = 0">МОИ ПОКУПКИ</button>
                <button :class="[{ 'active': tabs == 1 }]" @click="tabs = 1">ТРАНЗАКЦИИ</button>
                <button :class="[{ 'active': tabs == 2 }, { 'active': tabs == 4 }]" @click="tabs = 2">ОБРАТНАЯ
                    СВЯЗЬ</button>
                <button :class="[{ 'active': tabs == 3 }]" @click="tabs = 3">АККАУНТ</button>
            </div>
        </div>

        <div class="tabs mob">
            <div>
                <button :class="[{ 'active': tabs == 0 }]" @click="tabs = 0">МОИ ПОКУПКИ</button>
                <button :class="[{ 'active': tabs == 1 }]" @click="tabs = 1">ТРАНЗАКЦИИ</button>
            </div>
            <div>
                <button :class="[{ 'active': tabs == 2 }, { 'active': tabs == 4 }]" @click="tabs = 2">ОБРАТНАЯ
                    СВЯЗЬ</button>
                <button :class="[{ 'active': tabs == 3 }]" @click="tabs = 3">АККАУНТ</button>
            </div>

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

        <form class="user" v-if="tabs == 3">
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
.backtochat button {
    border-radius: 10px;
    border: 3px solid #000;
    background: transparent;
    display: flex;
    align-items: center;
    gap: 10px;

    padding: 17px 40px;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
}

.mob {
    display: none;
}

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
    white-space: nowrap;

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
    padding: 140px 100px 72px;
}

@media (max-width: 1440px) {
    .account {
        padding: 140px 50px 72px;
    }
}

@media (max-width: 1400px) {
    .products__list span {
        margin-right: 20px;
        font-size: 20px;
    }

    .product__desc p {
        font-size: 20px;
    }

    .product__desc small {
        font-size: 27px;
    }

    .product__desc {
        margin-left: 20px;
    }

    .product__img img {
        max-width: 100%;
        height: auto;
    }

    .product__img {
        height: fit-content;
    }

    .product__links {
        margin-top: 25px;
    }

    .product__links a {
        font-size: 20px;
        padding: 14px 50px;
        white-space: nowrap;
    }

    .products__filters button,
    .products__filters a {
        font-size: 20px;
        padding: 15px 35px;
    }

    .tabs button {
        font-size: 20px;
        padding: 15px;
    }

    .products__item:last-child {
        margin-bottom: 0;
    }

    .chatlist {
        justify-content: center;
        margin-top: 20px;
    }

    .chatlist__item {
        width: 100%;
    }

    .user__info label {
        font-size: 20px;
    }

    .user__info {
        gap: 20px;

    }

}

@media (max-width: 1024px) {
    .user__info {
        flex-direction: column;
    }

    .user__info label {
        font-size: 16px;
    }

    .user__info input,
    .user__info textarea {
        width: 100%;
        font-size: 16px;
        margin-bottom: 20px;
        border: 2px solid #000;
    }

    .form__footer {

        margin-top: 0;
        flex-direction: column;
        gap: 20px;
    }

    .form__footer button {
        flex: none;
        padding: 13px 16px;
        border: 2px solid #000;
        font-size: 16px;
    }

    .crack {
        flex-direction: column;
    }

    .backtochat button {
        margin-bottom: 10px;
        font-size: 16px;
        border: 2px solid #000;
        width: 100%;
        padding: 15px;
        flex: 1;
        justify-content: space-between;
    }

    .mob {
        display: block;
    }

    .account {
        padding: 140px 20px 50px;
    }

    .pc {
        display: none !important;
    }

    .account h1 {
        font-size: 32px;
    }

    .products__list span {
        display: none;
    }

    .products__item {
        flex-direction: column;
    }

    .product__img img {
        width: 100%;
        max-height: 165px;
    }

    .product__img img {}

    .product__desc {
        margin-left: 0;
        margin-top: 10px;
    }

    .products__list span:last-child {
        display: block !important;
        font-size: 16px !important;
    }

    .product__desc small {
        font-size: 20px;
    }

    .product__links {
        justify-content: space-between !important;
        gap: 10px;
    }

    .product__links a {
        flex: 1;
        text-align: center;
        border: 2px solid #000;
        padding: 13px 15px;
        font-size: 14px;
        text-transform: none;
    }

    .product__desc div:first-child {
        align-items: flex-end;
    }

    .product__desc p {
        margin-bottom: 10px;
        font-size: 16px;
    }

    .products__filters button,
    .products__filters a {
        padding: 13px 17px;
        font-size: 14px;
        border: 2px solid #000;
        font-weight: 400;
        flex: 1;
        text-align: center;
        white-space: normal;
    }

    .products__list {
        margin-top: 30px;
    }

    .tabs div {
        display: flex;
        margin-bottom: 10px;
        /* justify-content: center; */
    }

    .tabs button {
        font-size: 16px;
        border: 2px solid #000;
        flex: 1;
        max-width: unset;
    }

    .products {
        margin-top: 20px;
    }

    .filter__body {
        left: -130%;
        padding: 20px 20px 0;
        width: 350px;
    }

    .filters__category {
        flex-direction: column;
    }

    .filters__category label {
        display: block;
    }

    .custom-checkbox:last-child {
        margin-bottom: 26px !important;
    }

    .custom-checkbox {
        margin-bottom: 26px;
    }

    .price__filter input {
        max-width: 145px;
        font-size: 20px;
    }

    .price__filter {
        gap: 4px;
    }

    .filter__body h3 {
        font-size: 20px;
        margin-bottom: 20px;
    }

    .custom-checkbox p {
        font-size: 16px;
    }

    .chatlist__item h3 {
        font-size: 20px;
        margin: 0;
    }

    .chatlist__item small {
        font-size: 16px;
    }

    .chatlist__item button {
        font-size: 20px;
        padding: 15px 30px;
        border: 2px solid #000;
    }

    .chatlist__item {
        padding: 20px;
    }

    .chatlist__item .text {
        gap: 20px;
    }

    .chatlist {
        gap: 20px;
    }

    .user button {
        margin-top: 20px;
        font-size: 20px;
        border: 2px solid #000;
        width: 100%;
        padding: 15px 0;
    }

    .user__info input {
        margin-bottom: 10px;
    }

    .user {
        margin-top: 20px;
    }
}

@media (max-width: 500px) {
    .chatlist__item .text {
        gap: 20px;
        flex-direction: column;
    }

    .chatlist__item button {
        margin-top: 20px;
    }
}

@media (max-width: 380px) {
    .filter__body {
        left: -125%;
        padding: 20px 20px 0;
        width: 350px;
    }

    .products__filters button,
    .products__filters a {
        font-size: 14px;
        flex: 1;
    }

    .products__list span:last-child {
        display: block !important;
        font-size: 14px !important;
    }

    .product__desc small {
        font-size: 18px;
    }

    .product__desc p {
        margin-bottom: 10px;
        font-size: 14px;
    }
}
</style>