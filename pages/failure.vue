<template>
    <div class="success">
        <div class="text-center">
            <h1>ПРИ ПРОВЕДЕНИИ ТРАНЗАКЦИИ ПРОИЗОШЛА ОШИБКА
                ПОВТОРИТЕ ЗАПРОС ПОЗДНЕЕ</h1>

            <NuxtLink to="/">НА ГЛАВНУЮ</NuxtLink>
        </div>
    </div>
</template>
<script>
import global from '~/mixins/global';
import axios from 'axios';
export default {
    mixins: [global],
    data() {
        return {
            pathUrl: 'https://themes.kz',
        }
    },
    methods: {
        sendRequest(reference) {
            const token = this.getAuthorizationCookie();
            const path = `${this.pathUrl}/api/money/failure/${reference}`;
            axios.defaults.headers.common['Authorization'] = `Token ${token}`;
            axios
                .get(path)
                .then(response => {
                    console.log(response)
                    if (response.status == 200) {
                        window.location.href = '/'
                    }
                })
                .catch(error => {
                    console.log(error);
                });
        },
    },
    mounted() {
        const url = window.location.href;
        const match = url.match(/order_pay_pr_(\d+)/);

        if (match) {
            this.extractedValue = match[0];
            console.log(this.extractedValue);

            this.sendRequest(match[0])
        }
    },

}
</script >
<script setup>

useSeoMeta({
    title: 'Ошибка | Themes',
    ogTitle: 'Ошибка | Themes',
    description: 'Ошибка | Themes',
    ogDescription: 'Ошибка | Themes',
})
</script>
<style scoped>
.success {
    padding: 140px 100px 72px;
    height: 100vh;
}

.success h1 {
    margin-top: 150px;
    font-size: 40px;
    font-style: normal;
    font-weight: 400;
    line-height: 150%;
    font-family: var(--int);
    margin-bottom: 70px;
}

.success a {
    padding: 13px 31px;
    border-radius: 30px;
    border: 2px solid #000;
    background: transparent;

    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.success a:hover {
    color: #fff;
    background: #000;
}

@media(max-width: 1024px) {
    .success h1 {
        font-size: 20px;
    }

    .success {
        padding: 140px 50px 0;
        height: 100vh;
    }

}
</style>