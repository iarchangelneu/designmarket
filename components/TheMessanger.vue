<template>
    <div class="messanger d-flex">
        <div class="messanger__list">
            <div class="messanger__item">
                <div class="name d-flex align-items-center">
                    <h3 class="mb-0">alex.ivanov@gmail.com</h3>
                    <small>14:47</small>
                </div>
                <p class="mb-0" v-if="message.length <= 50">{{ message }}</p>
                <p class="mb-0" v-else>{{ message.slice(0, 50) + '...' }}</p>
            </div>
            <div class="messanger__item">
                <div class="name d-flex align-items-center">
                    <h3 class="mb-0">alex.ivanov@gmail.com</h3>
                    <small>14:47</small>
                </div>
                <p class="mb-0" v-if="message.length <= 50">{{ message }}</p>
                <p class="mb-0" v-else>{{ message.slice(0, 50) + '...' }}</p>
            </div>
            <div class="messanger__item">
                <div class="name d-flex align-items-center">
                    <h3 class="mb-0">alex.ivanov@gmail.com</h3>
                    <small>14:47</small>
                </div>
                <p class="mb-0" v-if="message.length <= 50">{{ message }}</p>
                <p class="mb-0" v-else>{{ message.slice(0, 50) + '...' }}</p>
            </div>
            <div class="messanger__item">
                <div class="name d-flex align-items-center">
                    <h3 class="mb-0">alex.ivanov@gmail.com</h3>
                    <small>14:47</small>
                </div>
                <p class="mb-0" v-if="message.length <= 50">{{ message }}</p>
                <p class="mb-0" v-else>{{ message.slice(0, 50) + '...' }}</p>
            </div>
            <div class="messanger__item">
                <div class="name d-flex align-items-center">
                    <h3 class="mb-0">alex.ivanov@gmail.com</h3>
                    <small>14:47</small>
                </div>
                <p class="mb-0" v-if="message.length <= 50">{{ message }}</p>
                <p class="mb-0" v-else>{{ message.slice(0, 50) + '...' }}</p>
            </div>
        </div>

        <div class="messanger__chatbox">
            <h3>alex.ivanov@gmail.com</h3>
            <div class="message__form" ref="messageContainer">
                <!-- <div class=" message__from">
                    <div>
                        <div class="message">
                            <div class="message__item from">
                                <p class="mb-0">
                                    Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum
                                    Lorem
                                    ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem
                                    ipsum
                                    Lorem ipsum Lorem ipsum Lorem ipsum
                                </p>
                            </div>
                            <div class="time">
                                <small>14:46</small>
                            </div>
                        </div>
                    </div>
                </div> -->

                <div v-for="message in messages" :key="message.time"
                    :class="{ message__to: !message.isFrom, message__from: message.isFrom }">
                    <div>
                        <div class="message">
                            <div class="message__item" :class="{ to: !message.isFrom, from: message.isFrom }">
                                <p class="mb-0">{{ message.text }}</p>
                            </div>
                            <div class="time" :class="{ 'text-right': !message.isFrom, 'text-left': message.isFrom }">
                                <small>{{ message.time }}</small>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

            <div class="messanger__send d-flex">
                <input type="text" class="w-100" v-model="textMessage" placeholder="Введите сообщение..."
                    @keydown.enter.prevent="sendMessage">
                <button @click="sendMessage"><img src="@/assets/img/send.svg" alt=""></button>
            </div>
            <div class="d-flex align-items-center mt-4">
                <label class="toggle mb-0">
                    <input type="checkbox" v-model="isTest" />
                    <span class="slider"></span>
                </label>

                <span class="ml-3">Переключи для смены отправителя сообщений (Только для теста)</span>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            message: 'Lorem Ipsum Lorem Ipsum Lorem Ipsum Lorem Ipsum Ipsum Ipsum Ipsum Ipsum',
            textMessage: '',
            textMessage2: '',
            messages: [
                {
                    text: 'Кто цыгане?',
                    time: '0:30',
                    isFrom: true,
                },
                {
                    text: '3.14doorы',
                    time: '0:30',
                    isFrom: false,
                }
            ],
            isTest: false,

        }
    },
    methods: {
        sendMessage() {
            if (this.textMessage.trim() !== '') {
                const currentTime = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
                const newMessage = {
                    text: this.textMessage,
                    time: currentTime,
                    isFrom: this.isTest // Для определения отправителя
                };
                this.messages.push(newMessage);
                this.textMessage = ''; // Сбросить инпут после отправки
                this.$nextTick(() => {
                    this.scrollToBottom();
                });
            }
        },
        scrollToBottom() {
            const container = this.$refs.messageContainer;
            container.scrollTop = container.scrollHeight;
        }
    }
}
</script>
<style scoped>
.toggle {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 24px;
}

.toggle input {
    opacity: 0;
    width: 0;
    height: 0;
}

.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: 0.4s;
    transition: 0.4s;
    border-radius: 34px;
}

.slider:before {
    position: absolute;
    content: '';
    height: 20px;
    width: 20px;
    left: 2px;
    bottom: 2px;
    background-color: white;
    -webkit-transition: 0.4s;
    transition: 0.4s;
    border-radius: 50%;
}

input:checked+.slider {
    background-color: #000;
}

input:focus+.slider {
    box-shadow: 0 0 1px #000;
}

input:checked+.slider:before {
    -webkit-transform: translateX(26px);
    -ms-transform: translateX(26px);
    transform: translateX(26px);
}

.message__from {
    display: flex;
}

.message__to {
    display: flex;
    justify-content: flex-end;
}

.messanger__send button {
    background: transparent;
    border-radius: 50%;
    padding: 15px;
    border: 3px solid #000;
}

.messanger__send input {
    border-radius: 50px;
    border: 3px solid #000;
    background: transparent;
    padding: 19px 30px;

    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 110%;
    font-family: var(--int);
    color: #000;
}

.messanger__send input::placeholder {
    color: rgba(0, 0, 0, 0.60);
}

.messanger__send {
    margin-top: 10px;
    gap: 20px;
}

.message small {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
}

.message__form {
    margin-top: 45px;
    height: 468px;
    overflow: auto;
}

.message__form::-webkit-scrollbar {
    width: 0px;
    /* в основном для вертикальных полос прокрутки */
    height: 0px;
    /* в основном для горизонтальных полос прокрутки */
}

.message__item p {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
    font-family: var(--int);
    color: #000;
}

.from {
    border-radius: 30px 30px 30px 0px;
}

.to {
    border-radius: 30px 30px 0 30px;
}

.message__item {
    padding: 20px;
    border: 3px solid #000;
    max-width: 543px;
    margin-bottom: 5px;
}

.message {
    margin-bottom: 51px;
}

.messanger__chatbox h3 {
    font-size: 32px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    text-transform: uppercase;
    font-family: var(--int);
    color: #000;
}

.messanger__chatbox {
    border-radius: 30px;
    background: #FFF;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    padding: 20px 40px;
    width: 1110px;
    max-height: 100%;
}

.messanger__item p {
    margin-top: 9px;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: var(--int);
    color: rgba(0, 0, 0, 0.70);
}

.name h3 {
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    font-family: var(--int);
    color: #000;
}

.name small {
    font-family: var(--int);
    color: #000;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 130%;
}

.name {
    gap: 0 187px;
}

.messanger__item {
    border-radius: 30px;
    background: #FFF;
    box-shadow: 0px 0px 20px 0px rgba(47, 59, 163, 0.20);
    padding: 20px 20px 20px 30px;
    margin-bottom: 20px;
    cursor: pointer;
}

.messanger__item:last-child {
    margin-bottom: 0;
}

.messanger {
    margin-top: 54px;
    gap: 0 40px;
}

@media (max-width: 1440px) {
    .messanger__chatbox h3 {
        font-size: 20px;
    }

    .message__item p {
        font-size: 16px;
    }

    .message__item {
        padding: 10px;
    }

    .messanger__chatbox {
        padding: 20px;
    }

    .messanger {
        gap: 20px;
        margin-top: 20px;
    }

    .name h3,
    .name small {
        font-size: 18px;
    }

    .messanger__item p {
        font-size: 14px;
    }

}

@media (max-width: 1024px) {
    .messanger__list {
        display: none;
    }

    .messanger__send input {
        font-size: 16px;
        padding: 15px;
    }

    .message {
        margin-bottom: 20px;
    }
}
</style>