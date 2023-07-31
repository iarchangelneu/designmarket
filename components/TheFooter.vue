<template>
    <footer v-if="!hideFooterOnPages.includes($route.name)">
        <div class="d-flex justify-content-between">
            <div class="d-flex align-items-center">
                <img src="@/assets/img/footerlogo.svg" alt="">
                <h1>design market.</h1>
            </div>

            <div class="links d-flex">
                <div>
                    <NuxtLink to="/for-designer">для дизайнера</NuxtLink>
                    <NuxtLink to="/terms">пользовательское соглашение</NuxtLink>
                </div>
                <div>
                    <NuxtLink to="/">личный кабинет</NuxtLink>
                    <NuxtLink to="/polytics">политика конфиденциальности</NuxtLink>
                </div>
            </div>
        </div>
        <div class="text-center copyright">
            <p>г. Алматы, пр-кт Республики 13, Почтовый индекс A15X3C5 (050013), +7 775 816 82 48, БИН 210840016943</p>
            <p>Почта поддержки : support@designmarket.kz</p>
        </div>
    </footer>
</template>
<script>
export default {
    data() {
        return {
            hideFooterOnPages: ['login', 'register'],
        };
    },
}
</script>
<style scoped>
.copyright {
    margin-top: 96px;
}

.copyright p {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 150%;
    font-family: var(--int);
    color: #fff;
    margin: 0;
}

.links a {
    display: block;
    color: #fff;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
}

.links a:nth-child(1) {
    margin-bottom: 52px;
}

.links {
    gap: 0 96px;
}

footer h1 {
    font-size: 64px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: lowercase;
    font-family: var(--int);
    color: #fff;
    margin-left: 40px;
    margin-bottom: 0;
}

footer {
    border-radius: 50px 50px 0px 0px;
    background: #000;
    padding: 48px 100px 36px;
}
</style>