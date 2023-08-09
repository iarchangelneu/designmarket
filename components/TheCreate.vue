<template>
    <div class="createproduct">
        <div class="creat__body w-100">
            <div class="d-flex creat__body w-100">

                <div>
                    <label for="name">Название товара</label>
                    <input type="text" id="name" name="name" v-model="name" placeholder="Введите название товара" required>

                    <div class="d-flex align-items-end category__select">
                        <div>
                            <label for="category">Выберите категорию</label>
                            <select name="add_category" id="category" v-model="selectedCategory"
                                :disabled="hasSelectedCategory" required>
                                <option value="" disabled>Выбор категории</option>
                                <option v-for="(category, index) in categories" :value="index" :key="index">{{ category
                                                                    }}
                                </option>
                            </select>
                        </div>

                        <div class="selected__cat" v-if="selectedCategories.length > 0">
                            <span class="d-flex align-items-start justify-content-between">
                                {{ categories[selectedCategories[0]] }}
                                <img src="@/assets/img/del.svg" @click="removeCategory"
                                    style="cursor: pointer; margin-left: 10px;">

                            </span>
                        </div>
                    </div>

                    <div class="d-flex align-items-center discount mt-4">
                        <div>
                            <label for="price">Введите цену</label>
                            <input type="number" id="price" name="price" v-model="price" placeholder="Цена за товар"
                                required>
                        </div>
                        <div>
                            <label for="discount">Скидка, %</label>
                            <input type="number" v-model="discount"
                                oninput="javascript: if (this.value > 100) this.value = 100;" id="discount" name="discount"
                                placeholder="% скидки">
                        </div>
                    </div>

                    <div class="mt-4">
                        <label for="file">Загрузка изображения</label>
                        <label class="custom-file-upload" :class="{ 'dragging': isDraggingFile }"
                            @dragover.prevent="handleDragOver" @dragleave="handleDragLeave" @drop="handleDrop">
                            <input type="file" id="file" name="main_image" @change="handleFileUpload">
                            <div class="d-flex align-items-center justify-content-between">
                                <small>{{ selectedFileName || 'Перетащите файл сюда или откройте вручную' }}</small>
                                <span>Открыть</span>
                            </div>
                        </label>
                    </div>
                </div>

                <div>
                    <div>
                        <label for="desc">Описание дизайна</label>
                        <textarea name="description_1" v-model="description" id="desc" cols="30"
                            placeholder="Введите описание товара"></textarea>
                    </div>
                    <div class="mt-3">
                        <label for="design">Загрузка файла дизайна</label>
                        <label class="custom-file-upload" :class="{ 'dragging': isDraggingFile2 }"
                            @dragover.prevent="handleDragOver2" @dragleave="handleDragLeave2" @drop="handleDrop2">
                            <input type="file" id="design" name="main_file" @change="handleFileUpload2">
                            <div class="d-flex align-items-center justify-content-between">
                                <small>{{ selectedDesignName || 'Перетащите файл сюда или откройте вручную' }}</small>
                                <span>Открыть</span>
                            </div>
                        </label>
                    </div>
                </div>
            </div>
            <div class="text-center">
                <button @click="submitForm" ref="createProduct">ОПУБЛИКОВАТЬ ТОВАР</button>
            </div>
        </div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            discount: 0,
            price: null,
            name: '',
            description: '',
            categories: [
                "Развлечения",
                "Еда и рестораны",
                "Образование",
                "Одежда и мода",
                "Автомобили",
                "Путешествия",
                "Питомцы",
                "Предприятия",
                "Недвижимость",
                "Медицина",
                "Финансы",
                "Техника",
            ],
            selectedCategory: null,
            selectedCategories: [],
            fileUpload: null,
            selectedFileName: '',
            selectedFile: [],
            selectedPhoto: {},
            isDraggingFile: false,
            selectedDesignName: '',
            selectedDesign: [],
            isDraggingFile2: false,
            pathUrl: 'http://127.0.0.1:8000',
        }
    },

    computed: {
        hasSelectedCategory() {
            return this.selectedCategories.length > 0;
        },
    },
    methods: {
        removeCategory() {
            this.selectedCategories.splice(0, 1);
            this.selectedCategory = null;
        },
        handleFileUpload(event) {
            const file = event.target.files[0];
            this.handleFile(file);
        },
        handleDragOver(event) {
            event.preventDefault();
            this.isDraggingFile = true;
        },
        handleDragLeave(event) {
            event.preventDefault();
            this.isDraggingFile = false;
        },
        handleDrop(event) {
            event.preventDefault();
            this.isDraggingFile = false;
            const file = event.dataTransfer.files[0];
            this.handleFile(file);
        },
        handleFile(file) {
            this.selectedFileName = file ? file.name : '';
            this.selectedFile = file;
        },
        handleFileUpload2(event) {
            const file = event.target.files[0];
            this.handleFile2(file);
        },
        handleDragOver2(event) {
            event.preventDefault();
            this.isDraggingFile2 = true;
        },
        handleDragLeave2(event) {
            event.preventDefault();
            this.isDraggingFile2 = false;
        },
        handleDrop2(event) {
            event.preventDefault();
            this.isDraggingFile2 = false;
            const file = event.dataTransfer.files[0];
            this.handleFile2(file);
        },
        handleFile2(file) {
            this.selectedDesignName = file ? file.name : '';
            this.selectedDesign = file;
        },
        async submitForm() {
            const path = `${this.pathUrl}/api/seller/seller-lk/add-product/`
            const formData = new FormData();
            formData.append('name', this.name);
            formData.append('category', this.selectedCategory + 1);
            formData.append('price', this.price);
            formData.append('discount', this.discount);
            formData.append('main_image', this.selectedFile);
            formData.append('description_1', this.description);
            formData.append('main_file', this.selectedDesign);
            this.$refs.createProduct.disabled = true
            this.$refs.createProduct.innerHTML = 'СОЗДАЕМ ЗАКАЗ'

            try {
                const response = await axios.post(path, formData);
                console.log('Форма успешно отправлена', response);
                if (response.status == 201) {
                    this.$refs.createProduct.disabled = false
                    this.$refs.createProduct.innerHTML = 'Заказ успешно создан!'
                }
            } catch (error) {
                console.error('Ошибка при отправке формы', error);
                this.$refs.createProduct.disabled = false
                this.$refs.createProduct.innerHTML = 'Ошибка при создании заказа'
            }
        },
    },
    watch: {
        selectedCategory(newVal) {
            if (newVal !== null) {
                this.selectedCategories = [newVal];
            }
        },
    },
}
</script>
<script setup>

useSeoMeta({
    title: 'Создание товара | Themes',
    ogTitle: 'Создание товара | Themes',
    description: 'Создание товара | Themes',
    ogDescription: 'Создание товара | Themes',
})
</script>
<style scoped>
.creat__body button {
    padding: 17px 65px;
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    margin-top: 54px;
    transition: all .3s ease;
}

.creat__body button:hover {
    color: #fff;
    background: #000;
}

.creat__body textarea {
    width: 45.781vw;
    background: transparent;
    border-radius: 10px;
    border: 3px solid #000;
    padding: 17px 20px;
    min-height: 308px;

    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    color: #000;
    font-family: var(--int);
}

.creat__body textarea::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.dragging {
    border-color: green !important;
}

.custom-file-upload small {
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: rgba(0, 0, 0, 0.60);

}

.custom-file-upload span {
    text-decoration: underline;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
}



.custom-file-upload {
    border-radius: 10px;
    border: 3px solid #000;
    background: transparent;
    padding: 15px 20px;
    width: 100%;
    margin: 0 !important;
    cursor: pointer;
}

/* Скрыть настоящий инпут типа file */
input[type="file"] {
    display: none !important;
}

.discount {
    gap: 0 30px;
}



.selected__cat,
#discount {
    width: 13.906vw;
}

#price {
    width: 26.169vw;
}

#name {
    width: 41.719vw;
}

#category {
    width: 26.169vw;
}

.category__select {
    gap: 0 30px;
}

.selected__cat {
    border-radius: 10px;
    border: 3px solid #000;
    padding: 17px 20px;
    height: 60px;
}

.selected__cat span {
    font-family: var(--int);
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    color: #000;
    white-space: nowrap;
}

.creat__body label {
    display: block;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
    margin-left: 20px;
    margin-bottom: 10px;


}


.creat__body input,
.creat__body select {
    display: block;
    border-radius: 10px;
    border: 3px solid #000;
    background: transparent;
    padding: 15px 20px;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: #000;
    height: 60px;
    width: 100%;
    margin-bottom: 30px;
}

.creat__body select {
    padding: 10px 20px;
}

.creat__body input:last-child {
    margin-bottom: 0;
}

.creat__body select:last-child {
    margin-bottom: 0;
}

.creat__body input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.creat__body {
    gap: 0 40px;
}

.createproduct {
    margin-top: 54px;
}

@media (max-width: 1440px) {
    /* .creat__body label {
        font-size: 20px;
    } */

    .creat__body {
        gap: 20px;
    }

    .custom-file-upload small {
        font-size: 16px;
    }
}

@media (max-width: 1024px) {
    .creat__body {
        flex-direction: column;
    }

    #name {
        width: 100%;
    }

    .category__select {
        width: 100%;
        gap: 10px;
    }

    .discount {
        gap: 10px;
        width: 100%;
    }

    .category__select div:first-child {
        width: 100%;
    }

    .creat__body textarea {
        width: 100%;
    }

    #price {
        width: 100%;
    }

    #discount {
        width: 100%;
    }

    .selected__cat {
        width: 100% !important;
    }

    .creat__body label {
        font-size: 20px;
    }

    input,
    select,
    textarea {
        font-size: 16px !important;
    }

    .custom-file-upload span {
        font-size: 14px;
    }

    .creat__body button {
        margin-top: 20px;
        padding: 15px 0;
        width: 100%;
        font-size: 20px;
        border: 2px solid #000;
    }

    .category__select {
        flex-direction: column;
    }

    #category {
        width: 100%;
    }

    .createproduct {
        margin-top: 20px;
    }
}
</style>