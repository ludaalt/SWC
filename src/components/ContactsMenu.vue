<template>
    <div class="contacts-menu">        
        <UserButton class="lang-button" :title=lang @click="changeLanguage()" />
        <div class="contacts-container">
            <a href=""></a>
            <a href="tel:+74951234567">+7 (495) 123-45-67</a>
            <UserButton @click="changeModalVisible" class="contacts-button" title="Контакты" />
        </div>        
    </div> 
</template>

<script>
import UserButton from './UserButton.vue'

export default {
  name: 'ContactsMenu',

  components: {
    UserButton
  },

  data() {
    return { 
      lang: "En",
      modalVisible: false
   }
  },

  methods:{
    changeLanguage() {
      this.lang = this.lang === "En" ? 'Ru' : 'En'
    },

    changeModalVisible() {
        this.$emit('updateParent', {
          modalVisible: !this.modalVisible,
        })
    }
  }
}
</script>


<style scoped lang="scss">
.contacts-menu {
    margin-top: 30px;
    padding: 0 42px 0 20px;
    display: flex;
    justify-content: space-between;    
}

.lang-button {
    min-width: 30px;
    color: #8B9FCC;
    font-family: 'SF Pro Text', 'Arial', sans-serif;
    font-size: 16px;
    font-weight: 500;
    line-height: 20px;

    &:hover {
        color: #fff;
    }
}

.contacts-container {
    display: flex;
    align-items: center;

    a {
        display: inline-block;
        margin-right: 15px;
        color: #FFF;
        text-align: center;
        font-family: 'Inter', 'Arial', sans-serif;
        font-size: 16px;
        font-weight: 600;
        line-height: 22px; 

        &:hover {
          text-decoration: underline;
        }
    }
}

.contacts-button {
    padding: 12px 24px;
    background-color: #49A1F1;
    border-radius: 10px;
    color: #FFF;
    text-align: center;
    font-family: 'Inter', 'Arial', sans-serif;
    font-size: 16px;
    font-weight: 600;
    line-height: 22px;
}
</style>
