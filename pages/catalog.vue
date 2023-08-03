<template>
    <div class="catalog">
        <h1>каталог дизайна</h1>

        <div class="catalog__filters d-flex justify-content-end">
            <div class="sort">
                <button class="d-flex align-items-center" @click="sort = !sort">
                    <span>СОРТИРОВКА</span>
                    <img src="@/assets/img/filterarrow.svg" class="arrow" alt="">
                </button>

                <div class="sort__body" :class="{ filters__active: sort }">
                    <div class="text-center">
                        <small>СНАЧАЛА ДЕШЕВЛЕ</small>
                        <hr>
                        <small>СНАЧАЛА ДОРОЖЕ</small>
                        <hr>
                        <small>САМЫЕ НОВЫЕ</small>
                        <hr>
                        <small>САМЫЕ СТАРЫЕ</small>
                    </div>
                </div>
            </div>
            <div class="filter">
                <button class="d-flex align-items-center" @click="filter = !filter">
                    <span>ФИЛЬТРЫ</span>
                    <img src="@/assets/img/filterarrow.svg" class="arrow" alt="">
                </button>

                <div class="filter__body" :class="[{ 'filters__active': filter }]">
                    <h3>Цена</h3>
                    <div class="price__filter d-flex align-items-center">
                        <input type="number" v-model="minPrice" placeholder="От">
                        <img src="@/assets/img/filterline.svg" alt="">
                        <input type="number" v-model="maxPrice" placeholder="До">
                    </div>

                    <h3 class="mt-4">КАТЕГОРИИ</h3>

                    <div class="d-flex filters__category">
                        <div>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">РАЗВЛЕЧЕНИЯ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ЕДА И РЕСТОРАНЫ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ОБРАЗОВАНИЕ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ОДЕЖДА И МОДА
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">АВТОМОБИЛИ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ПУТЕШЕСТВИЯ
                                </p>
                            </label>
                        </div>
                        <div>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ПИТОМЦЫ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ПРЕДПРИЯТИЯ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">НЕДВИЖИМОСТЬ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">МЕДИЦИНА
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ФИНАНСЫ
                                </p>
                            </label>
                            <label class="custom-checkbox">
                                <input type="checkbox" class="" value="0">
                                <p class="checkbox-text m-0">ТЕХНИКА
                                </p>
                            </label>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="catalog__block">
            <NuxtLink :to="'/product'">
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
            <NuxtLink :to="'/product'">
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
            <NuxtLink :to="'/product'">
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
            <NuxtLink :to="'/product'">
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
            <NuxtLink :to="'/product'">
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
            <NuxtLink :to="'/product'">
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
<script>
export default {
    data() {
        return {
            filter: false,
            sort: false,
        }
    }
}
</script >
<script setup>
useSeoMeta({
    title: 'Каталог | Themes',
    ogTitle: 'Каталог | Themes',
    description: 'Каталог | Themes',
    ogDescription: 'Каталог | Themes',
})
</script>
<style scoped>
hr {
    margin: 10px 0;
}

.sort__body small {
    font-size: 1.25vw;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    color: #000;
    font-family: var(--int);
    white-space: nowrap;
    cursor: pointer;
}

.sort {
    position: relative;
}

.sort__body {
    display: none;
    border-radius: 30px;
    background: #FFF;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    padding: 10px 40px;
    position: absolute;
    width: 16.771vw;
    margin-top: 20px;
    z-index: 50;
}

.filters__category {
    gap: 0px 40px;
}

.custom-checkbox p {
    font-family: var(--int);
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    white-space: nowrap;
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
    margin-bottom: 22px;
}

.custom-checkbox:last-child {
    margin-bottom: 0 !important;
}

.price__filter input {
    border-radius: 10px;
    border: 2px solid #000;
    background: transparent;
    text-align: right;

    font-family: var(--int);
    color: #000;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    max-width: 169px;
    height: 45px;
    padding: 10px 9px;
}

.price__filter input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.price__filter {
    gap: 13px;
}

.filter__body h3 {
    font-family: var(--int);
    color: #000;
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    margin-bottom: 20px;
    text-transform: uppercase;
}

.products__filters button,
.products__filters a {
    padding: 17px 40px;
    background: transparent;
    border-radius: 50px;
    border: 3px solid #000;
    transition: all .3s ease;
    cursor: pointer;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    transition: all .3s ease;

}

.products__filters a:hover {
    color: #fff;
    background: #000;
}

.filter button {
    gap: 0 10px;
}

.filter {
    position: relative;
}

.filter__body {
    position: absolute;
    display: none;
    border-radius: 30px;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    padding: 8px 20px 20px;
    background: #fff;
    left: -120%;
    z-index: 70;
    margin-top: 20px;
}

.filters__active {
    display: block !important;
}

.products__filters {
    gap: 0 20px;
}

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
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    border-radius: 50px;
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
    gap: 0 10px;

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
    padding: 140px 100px 72px;
}
</style>