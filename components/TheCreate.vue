<template>
    <div class="createproduct">
        <form class="creat__body w-100">
            <div class="d-flex creat__body w-100">

                <div>
                    <label for="name">Название товара</label>
                    <input type="text" id="name" name="name" placeholder="Введите название товара" required>

                    <div class="d-flex align-items-end category__select">
                        <div>
                            <label for="category">Выберите категорию</label>
                            <select name="category" id="category" v-model="selectedCategory" :disabled="hasSelectedCategory"
                                required>
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
                        <label for="file">Название товара</label>
                        <label class="custom-file-upload" :class="{ 'dragging': isDraggingFile }"
                            @dragover.prevent="handleDragOver" @dragleave="handleDragLeave" @drop="handleDrop">
                            <input type="file" id="file" name="file" @change="handleFileUpload">
                            <div class="d-flex align-items-center justify-content-between">
                                <small>{{ selectedFileName || 'Перетащите файл сюда или откройте вручную' }}</small>
                                <span>Открыть</span>
                            </div>
                        </label>
                    </div>
                </div>

                <div>
                    <div>
                        <label for="desc">Загрузка файла дизайна</label>
                        <textarea name="desc" id="desc" cols="30" placeholder="Введите описание товара"></textarea>
                    </div>
                    <div class="mt-3">
                        <label for="design">Загрузка файла дизайна</label>
                        <label class="custom-file-upload" :class="{ 'dragging': isDraggingFile2 }"
                            @dragover.prevent="handleDragOver2" @dragleave="handleDragLeave2" @drop="handleDrop2">
                            <input type="file" id="design" name="design" @change="handleFileUpload2">
                            <div class="d-flex align-items-center justify-content-between">
                                <small>{{ selectedDesignName || 'Перетащите файл сюда или откройте вручную' }}</small>
                                <span>Открыть</span>
                            </div>
                        </label>
                    </div>
                </div>
            </div>
            <div class="text-center">
                <button>ОПУБЛИКОВАТЬ ТОВАР</button>
            </div>
        </form>
    </div>
</template>
<script>
export default {
    data() {
        return {
            discount: null,
            price: null,
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
            isDraggingFile: false,
            selectedDesignName: '',
            isDraggingFile2: false,
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
            // хуесос
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
            // хуесос
        }
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
</style>