<template>
<div id="sidebar">
    <reset></reset>
    <hr>
    <price></price>
    <hr>
    <marques></marques>
    <hr>
    <colors></colors>
    <hr>
</div>
</template>

<script>
//import de mes composants de la sidebar
import reset from '@/components/sidebar/reset.vue'
import price from '@/components/sidebar/price.vue'
import marques from '@/components/sidebar/marques.vue'
import colors from '@/components/sidebar/color.vue'

export default {
    components:{
        reset,
        price,
        marques,
        colors
    }
}
</script>

<style lang="scss" scoped>
#sidebar{
     width: 300px;
     min-width: 300px;
     height: 500px;
     background: #2c3e50;
     border: 4px solid black;
     border-radius: 10px;
     font-weight: bold;
     margin-right: 1%;
 }

 hr{
    
    width: 80%;
    height: 3px;
    margin: auto;
    margin-top: 20px;
    margin-bottom: 10px;
    background: black;
    border: black;
 }
</style>

