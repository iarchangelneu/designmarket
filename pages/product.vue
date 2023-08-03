<template>
    <div class="product d-flex align-items-start">

        <div class="product__preview">
            <img src="@/assets/img/product.png" class="img-fluid" alt="">
        </div>

        <div class="author">
            <div class="text-center">
                <h1>шаблон сайта доставка еды</h1>
            </div>
            <div class="about__author">
                <div class="d-flex justify-content-between align-items-center name">
                    <p class="mb-0">Автор:</p>
                    <span>Design Market</span>
                </div>
                <div class="d-flex justify-content-between align-items-center category">
                    <p class="mb-0">Категория:</p>
                    <span>Еда и рестораны</span>
                </div>

                <p class="mb-0">Описание:</p>

                <small>Универсальный и современный дизайн для создания онлайн-платформы, специализирующейся на доставке еды.
                    Этот шаблон разработан с учетом потребностей и предпочтений пользователей, а также требований
                    ресторанов, кафе и других заведений питания, которые хотят расширить свой бизнес и предоставить удобный
                    сервис заказа еды через интернет.</small>

            </div>

            <div class="author__price d-flex justify-content-between align-items-end">
                <small>
                    18 000 ₸
                    <img src="@/assets/img/saled.svg" alt="">
                </small>
                <span>11 540 ₸</span>
                <div class="gradik">
                    <p class="mb-0">-30%</p>
                </div>
            </div>

            <button class="w-100">В КОРЗИНУ</button>
        </div>
    </div>
</template>
<script setup>
useSeoMeta({
    title: 'Товар хуевар | Design Market',
    ogTitle: 'Товар хуевар  | Design Market',
    description: 'Товар хуевар  | Design Market',
    ogDescription: 'Товар хуевар  | Design Market',
})
</script>
<style scoped>
.author button {
    margin-top: 20px;
    background: transparent;
    border-radius: 50px;
    border: 3px solid #000;
    padding: 17px 0;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

.author button:hover {
    color: #fff;
    background: #000;
}

.gradik {
    background-image: linear-gradient(90deg, #39007F 0%, #15D0FF 100%);
    color: transparent;
    background-clip: text;
}

.author__price p {
    font-size: 20px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    padding: 0 23px;
    border-image: url('@/assets/img/border.svg');
    border-image-slice: 9;
    border-image-width: 8px;
    border-style: solid;

}

.author__price span {
    font-size: 54px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.author__price small img {
    position: absolute;
    left: 2%;
    bottom: 10%;
    /* transform: rotate(5deg); */
}

.author__price small {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    position: relative;
}

.author__price {
    margin-top: 20px;
}

.about__author small {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
    margin-top: 20px;
    display: block;
}

.category {
    margin-bottom: 25px;
}

.name {
    margin-bottom: 30px;
}

.about__author span {
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    font-family: var(--int);
    color: #000;

    border-radius: 20px;
    border: 2px solid #000;
    padding: 5px 15px;
}

.about__author p {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
}

.about__author {
    margin-top: 40px;
}

.author h1 {
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.author {
    border-radius: 50px;
    background: #FFF;
    box-shadow: 0px 0px 15px 0px rgba(47, 59, 163, 0.20);
    padding: 40px;
    max-width: 609px;
}

.product__preview {
    max-width: 1071px;
    border-radius: 50px;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
}

.product {
    padding: 120px 100px 72px;
    gap: 0 40px;
}
</style>