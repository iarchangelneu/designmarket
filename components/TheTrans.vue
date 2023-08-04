<template>
    <div class="transactions" v-if="!test">
        <table class="table table-borderless text-center pc">
            <thead>
                <tr>
                    <th>Тип</th>
                    <th>Цена</th>
                    <th>Дата</th>
                    <th>Время</th>
                    <th>Статус</th>
                    <th>Состояние счета</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Продажа</td>
                    <td>+ 8 000 ₸</td>
                    <td>05.12.22</td>
                    <td>15:47</td>
                    <td class="success">Совершено</td>
                    <td>18 000 ₸</td>
                </tr>
                <tr>
                    <td>Продажа</td>
                    <td>+ 8 000 ₸</td>
                    <td>05.12.22</td>
                    <td>15:47</td>
                    <td class="failure">Отменено</td>
                    <td>18 000 ₸</td>
                </tr>

            </tbody>
        </table>
        <div class="mob">
            <div class="transa">
                <div class="trans__item">
                    <div class="d-flex align-items-center justify-content-between">
                        <span>Пополнение</span>
                        <small>05.12.22</small>
                        <small>15:47</small>
                        <img src="@/assets/img/succes.svg" alt="">
                    </div>
                    <div class="d-flex justify-content-between prices">
                        <div>
                            <span>Цена</span>
                            <small>+ 8 000 ₸</small>
                        </div>
                        <div>
                            <span>Состояние счета</span>
                            <small>18 000 ₸</small>
                        </div>
                    </div>
                </div>
            </div>
            <div class="transa">
                <div class="trans__item">
                    <div class="d-flex align-items-center justify-content-between">
                        <span>Покупка</span>
                        <small>05.12.22</small>
                        <small>15:47</small>
                        <img src="@/assets/img/failure.svg" alt="">
                    </div>
                    <div class="d-flex justify-content-between prices">
                        <div>
                            <span>Цена</span>
                            <small>+ 8 000 ₸</small>
                        </div>
                        <div>
                            <span>Состояние счета</span>
                            <small>18 000 ₸</small>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="empty" v-else>
        <h2>СПИСОК ТРАНЗАКЦИЙ ОТОБРАЗИТСЯ ПОСЛЕ<br> ПЕРВОЙ ПОКУПКИ</h2>
    </div>
</template>
<script>
export default {
    data() {
        return {
            test: false,
        }
    }
}
</script>
<style scoped>
.transa {
    border-bottom: 1px solid #ECECEC;
}

.transa:last-child {
    border-bottom: 0 !important;
}

.prices {
    margin-top: 15px;
}

.prices span {
    margin-bottom: 10px;
}

.trans__item span {
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    opacity: 0.5;
    display: block;
}

.trans__item small {
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    color: #000;
    font-family: var(--int);
}

.mob {
    display: none;
}

.empty {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 180px 0;
}

.empty h2 {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}

.transactions td {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
}

.transactions th {
    font-size: 20px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    opacity: 0.5;
}

.success {
    color: #03B820 !important;
}

.failure {
    color: #EA0505 !important;
}

.transactions {
    border-radius: 50px;
    background: #FFF;
    box-shadow: 0px 0px 15px 0px rgba(47, 59, 163, 0.20);
    padding: 50px 100px;
    margin-top: 40px;
}

@media (max-width: 1400px) {
    .transactions {
        padding: 50px;
    }
}

@media (max-width: 1024px) {
    .pc {
        display: none;
    }

    .mob {
        display: block;
    }

    .transactions {
        padding: 0;
    }

    .trans__item {
        padding: 30px;
    }
}
</style>