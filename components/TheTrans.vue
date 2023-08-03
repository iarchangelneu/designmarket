<template>
    <div class="transactions" v-if="!test">
        <table class="table table-borderless text-center">
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
</style>