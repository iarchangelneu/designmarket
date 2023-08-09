<template>
    <div class="modal fade" id="outModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modalbody">
                    <div class="text-center">
                        <h1>
                            Вывод средств
                        </h1>
                    </div>
                    <p>Порядок действий для вывода средств</p>
                    <p>1. Подтвердите Ваше согласие с правилами нашей системы</p>
                    <label class="custom-checkbox">
                        <input type="checkbox" class="" value="0">
                        <p class="checkbox-text m-0">Я согласен с <NuxtLink to='/terms'>пользовательским соглашением
                            </NuxtLink> и <NuxtLink to='/polytics'>политикой
                                конфиденциальности</NuxtLink>
                        </p>
                    </label>
                    <p>2. Введите сумму, которую Вы хотите вывести с личного счета, и нажмите на кнопку “Вывести”. Вы будете
                        переадресованы на сайт платежной системы, где сможете завершить операцию.</p>

                    <form class="d-flex sendMoney">
                        <input type="text" v-model="count" name="count" id="count" placeholder="100 ₸">
                        <input type="number" name="card" id="card" v-model="card_number">
                        <button type="button" @click="outMoney()">ВЫВЕСТИ</button>
                    </form>

                    <div class="modalfooter d-flex">
                        <button :class="{ active: count == 100 }" @click="count = 100">100 ₸</button>
                        <button :class="{ active: count == 1000 }" @click="count = 1000">1000 ₸</button>
                        <button :class="{ active: count == 2000 }" @click="count = 2000">2000 ₸</button>
                        <button :class="{ active: count == 5000 }" @click="count = 5000">5000 ₸</button>
                        <button :class="{ active: count == 10000 }" @click="count = 10000">10000 ₸</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import global from '~/mixins/global';
import axios from 'axios'
export default {
    mixins: [global],
    data() {
        return {
            count: null,
            pathUrl: 'http://127.0.0.1:8000',
            card_number: null,
        }
    },
    methods: {
        outMoney() {
            const token = this.getAuthorizationCookie()
            const path = `${this.pathUrl}/api/money/pay-return`
            axios.defaults.headers.common['Authorization'] = `Token ${token}`;

            axios
                .post(path, {
                    amount: this.count,
                    card_number: this.card_number
                })
                .then(response => {
                    console.log(response)

                })
                .catch(error => {
                    console.error(error)
                })
        },
    }
}
</script>
<style scoped>
.modalfooter {
    gap: 10px;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 25px;
}

.modalfooter button {
    padding: 12px;
    background: transparent;
    border-radius: 30px;
    border: 2px solid #000;
    transition: all .3s ease;
    max-width: 108px;
    white-space: nowrap;

    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
}

.modalfooter button:hover {
    color: #fff;
    background: #000;
}

.active {
    color: #fff !important;
    background: #000 !important;
}

.sendMoney button {
    width: 100%;
    border-radius: 30px;
    border: 2px solid #000;
    background: transparent;
    padding: 17px 0;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.sendMoney button:hover {
    color: #fff;
    background: #000;
}

.sendMoney input {
    border-radius: 15px;
    border: 2px solid #000;
    background: transparent;
    padding: 10px;
    text-align: right;

    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    color: #000;
    font-family: var(--int);
    max-width: 227px;
}

.sendMoney input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.sendMoney {
    gap: 0 20px;
}

.custom-checkbox a {
    margin-bottom: 0;
    color: #000;
    text-decoration: underline !important;
}

.custom-checkbox input[type="checkbox"] {
    opacity: 0;
    position: absolute;
    border-radius: 4px;
}

.custom-checkbox .checkbox-text:before {
    content: url('@/assets/img/check.svg');
    display: inline-block;
    vertical-align: middle;
    width: 20px;
    height: 20px;
    margin-right: 10px;
    border: 1px solid #000;
    border-radius: 4px;
    margin-bottom: 4px;
}

.custom-checkbox input[type="checkbox"]:checked+.checkbox-text:before {
    content: url('@/assets/img/check.svg');
    font-size: 16px;
    color: black;
    text-align: center;
    line-height: 20px;
    background: #000;
}

.custom-checkbox {
    margin-bottom: 25px;
}

.custom-checkbox:last-child {
    margin-bottom: 0 !important;
}

.modalbody p {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
    margin-bottom: 25px;
}

.modalbody h1 {
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 25px;
}

.modalbody {
    padding: 38px;
}

.modal-content {
    border-radius: 30px;
    background: #FFF;
    border: 0;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
}

@media (min-width: 576px) {
    .modal-dialog {
        max-width: 611px;
        margin: 1.75rem auto;
    }
}

@media (max-width: 500px) {
    .modalbody {
        padding: 18px;
    }

    .modalbody h1 {
        font-size: 20px;
        margin-bottom: 20px;
    }

    .modalbody p {
        font-size: 16px;
        margin-bottom: 10px;
    }

    .sendMoney input {
        max-width: 147px;
        height: 45px;
        font-size: 20px;
    }

    .sendMoney button {
        font-size: 16px;
        padding: 12px 34px;
    }

    .modalfooter button {
        font-size: 16px;
    }

    .modal-dialog {
        display: -ms-flexbox;
        display: flex;
        -ms-flex-align: center;
        align-items: center;
        min-height: calc(100% - 1rem)
    }

}
</style>