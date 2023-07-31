<template>
    <div class="login d-flex">
        <div class="login__form">
            <div class="form__body">
                <div>
                    <div class="text-center">
                        <h1>Регистрация</h1>
                    </div>
                    <input type="email" name="email" id="" placeholder="E-mail">
                    <input type="password" name="password" id="" placeholder="Пароль">
                    <input type="password" name="repeat-password" id="" placeholder="Повторите пароль">
                    <div class="switch-button">
                        <span class="active" :style="{ left: activeSwitchPosition }"></span>
                        <button type="button" class="switch-button-case left"
                            :class="{ 'active-case': activeSwitchPosition === '0%' }"
                            @click="switchLeft">ПОКУПАТЕЛЬ</button>
                        <button type="button" class="switch-button-case right"
                            :class="{ 'active-case': activeSwitchPosition === '50%' }"
                            @click="switchRight">ПРОДАВЕЦ</button>
                    </div>
                    <button class="w-100 register">ЗАРЕГИСТРИРОВАТЬСЯ</button>
                    <div class="text-center">
                        <span>Уже есть аккаунт? <NuxtLink to='/login'>Войти</NuxtLink></span>
                    </div>
                </div>
            </div>
        </div>

        <div class="logo">
            <div class="img">
                <img src="@/assets/img/logoform.svg" class="img-fluid" alt="">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            activeSwitchPosition: '50%',
        }
    },
    methods: {
        switchLeft() {
            this.activeSwitchPosition = '0%';
        },
        switchRight() {
            this.activeSwitchPosition = '50%';
        },
    },
}
</script>
<script setup>
useSeoMeta({
    title: 'Регистрация | Design Market',
    ogTitle: 'Регистрация | Design Market',
    description: 'Регистрация | Design Market',
    ogDescription: 'Регистрация | Design Market',
})
</script>
<style scoped>
.switch-button {
    width: 100%;
    height: 60px;
    text-align: center;
    position: relative;
    left: 50%;
    -webkit-transform: translate3D(-50%, -50%, 0);
    transform: translate3D(-50%, -50%, 0);
    will-change: transform;
    z-index: 197 !important;
    cursor: pointer;
    transition: .3s ease all;
    border: 3px solid #000;
    background: #fff;
    border-radius: 8px;
    margin-top: 50px;
}

.switch-button-case {
    display: inline-block;
    background: none;
    width: 50%;
    height: 100%;
    color: #36589f;
    position: relative;
    border: none;
    transition: .3s ease all;

    padding-bottom: 1px;

    font-style: normal;
    font-weight: 300;
    font-size: 24px;
    line-height: 110%;
    text-transform: uppercase;
    color: #000;
    font-family: var(--int);
}

.switch-button-case:hover {
    color: grey;
    cursor: pointer;
}

.switch-button-case:focus {
    outline: none;
}

.switch-button .active {
    color: #fff;
    background-color: #000;
    box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1), 0px 1px 2px rgba(0, 0, 0, 0.06);
    border-radius: 6px;
    position: absolute;
    left: 0;
    top: 0;
    width: 50%;
    height: 100%;

    z-index: -1 !important;
    margin-top: 0;
    margin-left: 0;
    transition: .3s ease-out all;
}

.switch-button .active-case {
    color: #fff;
}

.logo {
    background: #F6F5F3;
    width: 100%;
}

.form__body span a {
    color: #000;
    text-decoration: underline !important;
}

.form__body span {
    display: block;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    font-family: var(--int);
    margin-top: 20px;
}

.register {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 17px 0;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.register:hover {
    background: #000;
    color: #fff;
}

.form__body input {
    display: block;
    width: 100%;
    margin-bottom: 20px;
    border-radius: 10px;
    border: 3px solid #000;
    background: transparent;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;

    padding: 17px 23px;
}

.form__body input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.form__body h1 {
    font-size: 56px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 30px;
}

.login__form {
    padding: 0 47px;
}

.login {
    height: 100vh;
}

.login__form,
.logo {
    display: flex;
    justify-content: center;
    align-items: center;
}

.form__body,
.img {
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>