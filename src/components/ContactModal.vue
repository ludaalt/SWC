<template>
    <div class="modal-wrapper" v-if="isShown"  @click="hideModal">
        <div class="modal-body">
            <h3>Контактная информация</h3>
            <div class="modal-body-block">
                <p class="grey-text center-text"><span class="icon location-icon"></span>Наш офис</p>
                <p>Санкт-Петербург, ул. Такая-то, д. 1</p>
                <a href="#">Показать на карте</a>
            </div>
            <div class="modal-body-block modal-body-block_flex">
                <div>
                    <p>
                        <span class="grey-text">Звоните: </span>+7 (495) 123-45-67
                    </p>
                    <p>
                        <span class="grey-text">Пишите: </span>info@test.ru
                    </p>
                </div>
                <button class="call-order-button grey-text">Заказать звонок</button>                
            </div>
            <div class="modal-body-block">
                <p class="grey-text center-text"><span class="icon time-icon"></span>Режим работы:</p>
                <p>
                    Пн-Пт — с 10:00 до 18:00<br />
                    Сб-Вс — выходной
                </p>
            </div>
            <div>
                <p class="grey-text">Мы в соцсетях</p>
                <ul class="social-list">
                    <li class="social-link social-link-tg"><a href="#"></a></li>
                    <li class="social-link social-link-vk"><a href="#"></a></li>
                    <li class="social-link social-link-zen"><a href="#"></a></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ContactsMenu',
  props: ['isShown'],

  methods:{
    changeLanguage(){
      this.lang = this.lang === "En" ? 'Ru' : 'En'
    },

    hideModal() {
        this.$emit('updateVisible', {
          isShown: !this.isShown,
        })
    }
  }
}
</script>

<style scoped lang="scss">
.modal-wrapper {    
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.6);
    z-index: 20;
}

.modal-body {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-width: 557px;
    background-color: #fff;
    border-radius: 11px;
    padding: 40px;
    font-family: 'Inter', 'Arial', sans-serif;
    font-size: 16px;
    font-weight: 600;
    line-height: 20px;

  h3 {
    margin-bottom: 30px;
    color: #08123A;
    text-align: center;
    font-family: 'Inter', 'Arial', sans-serif;
    font-size: 20px;
    line-height: 22px;
    }

    .icon {
        display: inline-block;
        min-width: 24px;
        min-height: 24px;
        margin-right: 7px;
        background-repeat: no-repeat;
        background-position: center;
    }

    .location-icon {
     background-image: url('../assets/location.svg');
    }

    .time-icon {
        background-image: url('../assets/time.svg');
    }

    .grey-text {
        color: #5F6B77;
    }

    .center-text {
        display: flex;
        align-items: center;
    }

    a {
        color: #506CCF;
        text-decoration-line: underline;
    }

    &-block {
        margin-bottom: 40px;

        &_flex {
            margin-bottom: 30px;
            display: flex;
            justify-content: space-between;
        }

        p {
            margin-bottom: 10px;
        }
     }

    .call-order-button {
        max-height: 54px;
        border: 2px solid #5F6B77;
        border-radius: 10px;
        padding: 2px 25px;
        font-size: 16px;
        font-family: 'Inter', 'Arial', sans-serif;
        font-weight: 600;
    }

    .social-list {
        display: flex;
        margin-top: 12px;
    }

     .social-link {
        border-radius: 10px;
        border: 2px solid  #E9EAF0;
        width: 40px;
        height: 40px;
        background-position: center;
        background-repeat: no-repeat;

        &:not(:last-child) {
            margin-right: 18px;
        }

        &:hover {
            opacity: 0.8;
            border: 2px solid #514f4f;
            transform: scale(1.1);
        }

        &-tg {
            background-image: url('../assets/tg.svg');
        }

         &-vk {
            background-image: url('../assets/vk.svg');
        }

        &-zen {
            background-image: url('../assets/zen.svg');
        }
    }
}
</style>