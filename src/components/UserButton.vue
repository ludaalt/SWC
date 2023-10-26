<template>
<button>{{title}}</button>
 
</template>

<script>
export default {
  name: 'UserButton',
  props: {
    title: String
  }
}
</script>


<style lang="scss">
button {
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    background: none;
    cursor: pointer;
}


</style>
