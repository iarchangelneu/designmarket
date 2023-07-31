<template>
    <div class="catalog">
        <h1>каталог дизайна</h1>

        <div class="catalog__filters d-flex justify-content-end">
            <button class="d-flex align-items-center">
                <span>СОРТИРОВКА</span>
                <img src="@/assets/img/filterarrow.svg" class="arrow" alt="">
            </button>
            <button class="d-flex align-items-center">
                <span>ФИЛЬТРЫ</span>
                <img src="@/assets/img/filterarrow.svg" class="arrow" alt="">
            </button>
        </div>

        <div class="catalog__block">
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>доставка еды</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop1.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>автосалон</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop2.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>уходовая косметика</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop3.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>школа программирования</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop4.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>доставка еды</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop1.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
            <NuxtLink :to="'/'">
                <div class="catalog__item">
                    <div class="category">
                        <div class="text-center">
                            <h2>автосалон</h2>
                        </div>
                    </div>
                    <img src="@/assets/img/shop2.png" alt="">
                    <div class="price">
                        11 540 ₸
                    </div>
                </div>
            </NuxtLink>
        </div>

        <div class="text-center showmore">
            <button>показать еще</button>
        </div>
    </div>
</template>
<script setup>
useSeoMeta({
    title: 'Каталог | Design Market',
    ogTitle: 'Каталог | Design Market',
    description: 'Каталог | Design Market',
    ogDescription: 'Каталог | Design Market',
})
</script>
<style scoped>
.showmore button {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 13px 44px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    transition: all .3s ease;
}

.showmore button:hover {
    color: #fff;
    background: #000;
}

.showmore {
    margin-top: 40px;
}

.price {
    position: absolute;
    bottom: 0;
    right: 0;
    padding: 5px 14px;

    font-size: 26.458px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
}

.catalog__item {
    position: relative;
}

.category h2 {
    margin: 0;
    font-size: 18px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #fff;
}

.category {
    border-radius: 33.073px 33.073px 0px 0px;
    background: #000;
    padding: 8px 0;
}

.catalog__block {
    margin-top: 40px;
    display: flex;
    flex-wrap: wrap;
    gap: 26px;
}

.catalog__filters button {
    border-radius: 51px;
    border: 3px solid #000;
    padding: 15px 40px;
    background: transparent;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;
}

/* .catalog__filters button:hover {
    color: #fff;
    background: #000;
}

.catalog__filters button:hover .arrow {
    filter: grayscale(100%);
} */

.catalog__filters {
    gap: 0 20px;
}

.catalog h1 {
    font-size: 80px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
    margin-bottom: 40px;
}

.catalog {
    padding: 120px 100px 72px;
}
</style>