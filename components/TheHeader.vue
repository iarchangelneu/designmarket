<template>
    <header>
        <div class="d-flex align-items-center justify-content-between w-100">
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
    </header>

    <TheOutModal></TheOutModal>
    <TheInModal></TheInModal>
</template>
<script>
export default {
    data() {
        return {
            cartOpen: false,
            isAuth: false,
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
</style>