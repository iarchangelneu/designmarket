<template>
    <header v-if="!hideFooterOnPages.includes($route.name)">
        <div class="d-flex align-items-center justify-content-between w-100 pc">
            <div class="first">
                <NuxtLink to="/catalog">Каталог</NuxtLink>
                <NuxtLink to="/">Поиск</NuxtLink>
            </div>

            <NuxtLink to="/" class="logo">
                <img src="@/assets/img/headerlogo.svg" alt="">
            </NuxtLink>

            <div class="first">
                <img src="@/assets/img/cart.svg" style="cursor: pointer;" alt="" @click="openHeader">
                <div class="first" v-if="isAuth">
                    <NuxtLink to="/login">Войти</NuxtLink>
                    <NuxtLink to="/register">регистрация</NuxtLink>
                </div>
                <div v-else class="first">
                    <NuxtLink style="cursor:pointer" data-toggle="modal" data-target="#outModal">23 000 ₸</NuxtLink>
                    <NuxtLink to="/seller-account">личный кабинет</NuxtLink>
                </div>
            </div>

        </div>
        <div class="mob">
            <div class="d-flex justify-content-between">
                <img src="@/assets/img/headermob.svg" alt="">
                <div class="d-flex burg">
                    <img src="@/assets/img/cart.svg" style="cursor: pointer;" alt="" @click="openHeader">

                    <div>
                        <input id="menu__toggle" type="checkbox" />
                        <label class="menu__btn" for="menu__toggle">
                            <span></span>
                        </label>


                        <ul class="menu__box">
                            <div class="mobmenu">
                                <div class="links">
                                    <div v-if="isAuth">
                                        <NuxtLink to="/login">Войти</NuxtLink>
                                        <NuxtLink to="/register">регистрация</NuxtLink>
                                    </div>
                                    <div v-else>
                                        <NuxtLink style="cursor: pointer;" alt="" data-toggle="modal"
                                            data-target="#outModal">23 000 ₸</NuxtLink>
                                        <NuxtLink to="/seller-account">Личный кабинет</NuxtLink>
                                    </div>
                                    <NuxtLink to="/catalog">Каталог</NuxtLink>
                                    <NuxtLink to="/catalog">поиск</NuxtLink>

                                    <div class="text-center">
                                        <img src="@/assets/img/mobcal.svg" alt="">
                                    </div>
                                </div>
                            </div>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <TheOutModal></TheOutModal>
    <TheInModal></TheInModal>
</template>
<script>
export default {
    data() {
        return {
            cartOpen: false,
            isAuth: true,
            hideFooterOnPages: ['login', 'register'],
        }
    },
    methods: {
        openHeader() {
            let sc = $(".cart")[0];
            sc.style.right = 0;
        },
    }
}
</script>
<style scoped>
.mobmenu .links img {
    margin-top: 150px;
}

.mobmenu .links a {
    display: block;
    margin-bottom: 40px;
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}


.menu__box a:hover {
    background: transparent;
}

#menu__toggle {
    opacity: 0;
}

.menu__btn {
    display: flex;
    /* используем flex для центрирования содержимого */
    align-items: center;
    /* центрируем содержимое кнопки */
    width: 40px;
    height: 20px;
    cursor: pointer;
    z-index: 100000000;
    color: #fff;
    position: relative;
    transform: rotate(180deg);
}

.menu__btn>span {
    display: block;
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: #000;
}

.menu__btn>span::before,
.menu__btn>span::after {
    display: block;
    position: absolute;
    width: 120%;
    height: 2px;
    background-color: #000;
}

.menu__btn>span::before {
    content: '';
    top: -8px;
}

.menu__btn>span::after {
    content: '';
    top: 8px;
}

.menu__box {
    display: block;
    position: fixed;
    visibility: hidden;
    top: -100%;
    left: 0;
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 20px 0;
    list-style: none;
    text-align: left;
    background: #F6F5F3;
    box-shadow: 1px 0px 6px rgba(0, 0, 0, .2);
}

/* элементы меню */
.menu__item {
    display: block;
    padding: 12px 24px;
    color: #333;
    font-family: 'Roboto', sans-serif;
    font-size: 20px;
    font-weight: 600;
    text-decoration: none;
    z-index: 100000;
}

.menu__item:hover {
    background-color: #CFD8DC;
}

#menu__toggle:checked~.menu__btn>span {
    transform: rotate(45deg);
    background-color: #000;
    border-radius: 10px;

}

#menu__toggle:checked~.menu__btn>span::before {
    top: 0;
    transform: rotate(0);
    background-color: #000;
    border-radius: 10px;

}

#menu__toggle:checked~.menu__btn>span::after {
    top: 0;
    transform: rotate(90deg);
    background-color: #000;
    border-radius: 10px;
}

#menu__toggle:checked~.menu__box {
    visibility: visible;
    top: 0;
}

.menu__btn>span,
.menu__btn>span::before,
.menu__btn>span::after {
    transition-duration: .25s;
}

.menu__box {
    transition-duration: .25s;
    z-index: 100000;
}

.menu__item {
    transition-duration: .25s;
}

.mobmenu {
    padding: 75px 40px 0;
}

.burg {
    gap: 0 30px;
}

.logo {
    margin-left: 10%;
}

header a {
    text-decoration: none !important;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.first {
    display: flex;
    align-items: center;
    gap: 0 72px;
}

header {
    padding: 25px 100px;
    width: 100%;
    position: fixed;
    background: #F6F5F3;
    z-index: 200;
}

.mob {
    display: none;
}

@media (max-width: 1670px) {
    header {
        padding: 25px 50px;
    }
}

@media (max-width: 1025px) {
    header {
        padding: 25px 30px;
    }

    .first {
        gap: 0 30px;
    }

    header a {
        font-size: 18px;
    }
}

@media (max-width: 1024px) {
    .pc {
        display: none !important;
    }

    .mob {
        display: block;
    }
}

@media (max-width: 380px) {
    .mobmenu {
        padding: 75px 20px 0;
    }
}
</style>