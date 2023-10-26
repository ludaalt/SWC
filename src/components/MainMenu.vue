<template>
  <nav>
    <a href="#">
      <img alt="Main logo" src="../assets/logo.svg">
    </a>

    <ul>
      <li><a href="#">Преимущества</a></li>
      <li><a href="#">Услуги</a></li>
      <li><a href="#">Виджет</a></li>
      <li><a href="#">Кому</a></li>
      <li><a href="#">Тарифы</a></li>
      <li><a href="#">Блог</a></li>
    </ul>
    
  </nav>
</template>

<script>
export default {
  name: 'MainMenu',
}
</script>


<style scoped lang="scss">
nav {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
  margin-bottom: 160px;
  margin-right: 32px;

  ul {
    display: flex;
    

    li {
      padding: 12px 18px;
      position: relative;

      color:  #5F6B77;

      font-family: 'SF Pro Text', 'Arial', sans-serif;
      font-size: 16px;

      font-weight: 500;
      line-height: 20px; 

      
      &::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        bottom: 5px;
        width: 100%;
        height: 3px;
        background-color: lightblue;
        opacity: 0;
        transition: opacity 300ms, transform 300ms;
      }

      &:hover::after {
        opacity: 1;
        transform: translate3d(0, 0.2em, 0);
      }
    }
  }
}

</style>
