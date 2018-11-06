<template>
<div>
  <h1>T-shirt Challenge</h1>
    <div class="shop">
      <sidebar></sidebar>
      <main-content :tshirts="tshirts"></main-content>
    </div>
    <myfooter></myfooter>
</div>
</template>

<script>
//Import de mes 2 composants globaux
import Sidebar from '@/components/sidebar/sidebar.vue'
import MainContent from '@/components/main/maincontent.vue'
import myfooter from '@/components/footer.vue'

export default { 
    components:{
      Sidebar,
      MainContent,
      myfooter
    }
}
</script>

<style lang="scss" scoped>

h1{
  padding-top: 100px;
  padding-bottom: 20px;
}

.shop{
  display: flex;

  margin: 0px 3% 0px 2%;
}
</style>


