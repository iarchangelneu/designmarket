<template>
    <footer v-if="!hideFooterOnPages.includes($route.name)">
        <div class="pc">
            <div class="d-flex justify-content-between align-items-center">
                <div>
                    <img src="@/assets/img/footerlogo.svg" class="img-fluid" alt="">
                </div>

                <div class="links d-flex">
                    <NuxtLink to="/for-designer">для дизайнера</NuxtLink>
                    <NuxtLink to="/terms">пользовательское соглашение</NuxtLink>
                    <NuxtLink :to="this.accountUrl">личный кабинет</NuxtLink>
                    <NuxtLink to="/polytics">политика конфиденциальности</NuxtLink>
                </div>
            </div>
            <div class="text-center copyright">
                <p>ТОО "ABNK.KZ",
                    БИН - 230440033532
                    Республика Казахстан, город Астана,
                    район Алматы, улица Қалибек Қуанышбаев,
                    дом, 15/2, кв. 111</p>
                <p>Почта поддержки : support@themes.kz</p>
            </div>
        </div>
        <div class="mob">
            <div class="links">
                <div class="d-flex justify-content-between align-items-center">
                    <NuxtLink to="/for-designer">для дизайнера</NuxtLink>
                    <img src="@/assets/img/footermob.svg" alt="">
                </div>
                <NuxtLink :to="this.accountUrl">личный кабинет</NuxtLink>
                <NuxtLink to="/terms">пользовательское соглашение</NuxtLink>
                <NuxtLink to="/polytics">политика конфиденциальности</NuxtLink>

                <p class="mb-0">ТОО "ABNK.KZ",
                    БИН - 230440033532
                    Республика Казахстан, город Астана,
                    район Алматы, улица Қалибек Қуанышбаев,
                    дом, 15/2, кв. 111<br>
                    Почта поддержки : <a href="mailto:support@themes.kz">support@themes.kz</a> </p>

            </div>
        </div>
    </footer>
</template>
<script>
import global from '~/mixins/global';
export default {
    mixins: [global],
    data() {
        return {
            hideFooterOnPages: ['login', 'register', 'complete-buy'],
        };
    },
}
</script>
<style scoped>
.mob {
    display: none;
}

.copyright {
    margin-top: 76px;
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


.links {
    gap: 0 68px;
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

@media (max-width: 1600px) {
    footer {
        padding: 30px 50px;
    }

    .links a {
        font-size: 14px;
    }

    .copyright p {
        font-size: 12px;
    }

    .links {
        gap: 0 20px;
    }

    .copyright {
        margin-top: 20px;
    }

}

@media (max-width: 1025px) {
    .links a {
        font-size: 12px;
    }

    .links {
        gap: 0 20px;
    }

    footer img {
        max-width: 50%;
    }

    footer {
        padding: 30px;
    }
}

@media (max-width: 1024px) {
    .pc {
        display: none;
    }

    .mob {
        display: block;
    }

    footer {
        padding: 39px 20px 50px;
    }

    .mob .links a {
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        text-transform: uppercase;
        font-family: var(--int);
        color: #fff;
        margin-bottom: 30px;
    }

    .mob .links a:last-child {
        margin-bottom: 0;
    }

    .links p {
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 140.5%;
        font-family: var(--int);
        color: #fff;
    }

    .links p a {
        text-decoration: underline !important;
        font-size: 16px !important;
        text-transform: none !important;
    }
}
</style>