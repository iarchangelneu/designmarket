<template>
    <div class="login d-flex">
        <div class="login__form">
            <div class="form__body">
                <div>
                    <div class="text-center">
                        <h1>аВТОРИЗАЦИЯ</h1>
                    </div>
                    <input type="email" name="email" id="email" placeholder="E-mail">
                    <input type="password" name="password" id="password" placeholder="Пароль">

                    <button class="w-100">Войти</button>
                    <div class="text-center">
                        <span>Еще нет аккаунта? <NuxtLink to='/register'>Регистрация</NuxtLink></span>
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
<script setup>
useSeoMeta({
    title: 'Авторизация | Themes',
    ogTitle: 'Авторизация | Themes',
    description: 'Авторизация | Themes',
    ogDescription: 'Авторизация | Themes',
})
</script>
<style scoped>
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

.form__body button {
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

.form__body button:hover {
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
    background: #fff;
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