<template> 
<div class="container">
  <button class="page-up-button" @click="toUp()"></button>

  <div class="light-block">
    <div class="light-block-container">
      <MainMenu  />
      <h1>Техническая поддержка сайтов, CRM систем и мобильных приложений</h1>
      <p>Профессиональное техническое сопровождение и обслуживание сайтов: полный комплекс услуг от опытных экспертов</p>
      <UserButton class="connection-button" title="Подключиться" />
      <UserButton class="page-down-button" @click="toBottom()" />

      <img class="analitic-image" src="./assets/img2.svg" alt="Analitic image">

    </div>

  </div>

  <div class="dark-block">
    <ContactsMenu />
    <img class="todolist-image" src="./assets/img1.svg" alt="Todo list image">

  </div>


  
 
</div>

  
</template>

<script>
import MainMenu from './components/MainMenu.vue'
import ContactsMenu from './components/ContactsMenu.vue'
import UserButton from './components/UserButton.vue'


export default {
  name: 'App',
  components: {
    MainMenu,
    ContactsMenu,
    UserButton,
    
  },

  methods:{
    toBottom(){
      window.scrollTo(0, 50000);
    },

    toUp(){
      window.scrollTo(0, 0);
    }
  }
}
</script>

<style lang="scss">

.container {
  max-width: 1440px;
  margin: 50px auto;

  min-height: 800px;
  height: 100%;
  display: flex;
}

.light-block {
  position: relative;
  flex-grow: 2;
  background: #F5F9FF;

  &-container {
    padding-left: 135px;
  }

  h1 {
    margin-bottom: 60px;
    max-width: 570px;
    color:  #08123A;
    font-family: 'SF Pro Display';
    font-size: 48px;
    font-weight: 600;
    line-height: 58px; 
  }

   p {
    margin-bottom: 60px;
    max-width: 560px;
    color:  #5F6B77;
    font-family: Inter;
    font-size: 20px;

    font-weight: 400;
    line-height: 28px; 
   }

   .connection-button {
    margin-bottom: 45px;
    padding: 15px 25px;
    border-radius: 10px;
    background:#506CCF;
    box-shadow: 0px 20px 35px 0px #DFE8F4;

    color: #FFF;
    text-align: center;

    font-family: SF Pro Text;
    font-size: 16px;

    font-weight: 500;
    line-height: 22px;
   }

   &::after {
    position: absolute;
    content: '';
    width: 10px;
    height: 10px;
    background-color: #3453C2;
    top: 102px;
    right: 130px;
    border-radius: 50%;
   }
}

.dark-block {
  min-width: 460px;
  //flex-grow: 1;
  background: linear-gradient(45deg, #506CCF 0%, #3453C2 100%);

  position: relative;

   &::before {
    position: absolute;
    content: '';
    width: 14px;
    height: 14px;
    background-color: #FF8B8B;
    border-radius: 50%;
    top: 300px;
    left: 46px;
  }

  &::after {
    position: absolute;
    content: '';
    width: 22px;
    height: 22px;
    background-color: #FFC86F;
    border-radius: 50%;
    bottom: 44px;
    left: 143px;
  }
}

.page-down-button,
   .page-up-button {
    min-width: 54px;
    min-height: 54px;
    padding: 11px;
    border-radius: 8px;
    border: 1px solid #E9EAF0;

    background-image: url("data:image/svg+xml, %3Csvg width='32' height='32' viewBox='0 0 32 32' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16 8C16.2653 8 16.5196 8.10536 16.7072 8.29289C16.8947 8.48043 17 8.73478 17 9V20.586L21.292 16.292C21.385 16.199 21.4954 16.1253 21.6169 16.075C21.7384 16.0246 21.8686 15.9987 22 15.9987C22.1315 15.9987 22.2617 16.0246 22.3832 16.075C22.5047 16.1253 22.6151 16.199 22.708 16.292C22.801 16.385 22.8748 16.4954 22.9251 16.6168C22.9754 16.7383 23.0013 16.8685 23.0013 17C23.0013 17.1315 22.9754 17.2617 22.9251 17.3832C22.8748 17.5046 22.801 17.615 22.708 17.708L16.708 23.708C16.6152 23.8011 16.5048 23.875 16.3833 23.9254C16.2618 23.9758 16.1316 24.0018 16 24.0018C15.8685 24.0018 15.7383 23.9758 15.6168 23.9254C15.4953 23.875 15.3849 23.8011 15.292 23.708L9.29204 17.708C9.19907 17.615 9.12531 17.5046 9.075 17.3832C9.02468 17.2617 8.99878 17.1315 8.99878 17C8.99878 16.8685 9.02468 16.7383 9.075 16.6168C9.12531 16.4954 9.19907 16.385 9.29204 16.292C9.47982 16.1042 9.73449 15.9987 10 15.9987C10.1315 15.9987 10.2617 16.0246 10.3832 16.075C10.5047 16.1253 10.6151 16.199 10.708 16.292L15 20.586V9C15 8.73478 15.1054 8.48043 15.2929 8.29289C15.4805 8.10536 15.7348 8 16 8Z' fill='%235F6B77'/%3E%3C/svg%3E");
    background-position: center;
    background-repeat: no-repeat;

    &:hover {
      border: 1px solid #8c8d94;
      background-size: 80%;
    }
   }

.page-up-button {
  position: absolute;
  bottom: 20px;
  transform: rotate(180deg);
  border: 3px solid red;
}

.todolist-image {
  position: absolute;
  right: 0;
  bottom: 0;
}

.analitic-image {
  position: absolute;
  z-index: 10;
  right: -175px;
  bottom: 80px;
  
}
</style>
