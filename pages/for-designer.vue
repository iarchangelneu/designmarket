<template>
    <div class="designer">
        <div class="d-flex designer__block">
            <img src="@/assets/img/designer.png" alt="">
            <div>
                <h1>Заработай на своих навыках в дизайне</h1>

                <p>Themes - это современная платформа, которая дает дизайнерам возможность превратить свои работы в
                    пассивный заработок</p>

                <ol>
                    <li>Зарегистрируйся как продавец на Themes</li>
                    <li>Создай шаблон дизайна сайта</li>
                    <li>Используй в своей работе Auto Layout, компоненты, и другие возможности Figma, упрощающие дальнейшую
                        работу с шаблоном</li>
                    <li>“Почисти” файл от ненужных элементов, подпиши названия страниц, секций, фреймов и других элементов
                    </li>
                    <li>В Личном кабинете нашей платформы создай новый товар</li>
                    <li>Загрузи иллюстрации своего дизайна</li>
                    <li>Напиши описание для своего товара (расскажи какой стиль используется, кому подойдет такой сайт и
                        т.д.)</li>
                    <li>Опубликуй и ожидай продаж твоих шаблонов!</li>
                </ol>

                <NuxtLink to="/register">ЗАРЕГИСТРИРОВАТЬСЯ</NuxtLink>
            </div>
        </div>
    </div>
</template>
<script setup>
useSeoMeta({
    title: 'Для дизайнера | Themes',
    ogTitle: 'Для дизайнера | Themes',
    description: 'Для дизайнера | Themes',
    ogDescription: 'Для дизайнера | Themes',
})
</script>
<style scoped>
.designer__block a {
    margin-top: 48px;
    display: block;
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 17px 103px;

    font-family: var(--int);
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    max-width: 494px;
    transition: all .3s ease;
}

.designer__block a:hover {
    color: #fff;
    background: #000;
}

.designer__block p {
    margin-bottom: 20px;
}

.designer__block li {
    margin-bottom: 10px;
}

.designer__block p,
ul,
li,
ol {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
}

.designer__block h1 {
    font-size: 80px;
    font-style: normal;
    font-weight: 500;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    margin-bottom: 48px;
}

.designer__block {
    gap: 0 40px;
}

.designer {
    padding: 120px 100px 72px;
}
</style>