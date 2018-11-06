<template>
    <div id="maincontent">
       <div class="card" v-for="(tshirt, n) in tshirts" :key="n">
           <p> {{ tshirt.nom }}</p>
           <p> {{ tshirt.marque }}</p> 
           <img :src="tshirt.images" :alt="tshirt.nom">
          <p> Prix: {{ tshirt.prix }}€</p>  
        </div>
    </div>
</template>


<script>
export default {
    props: ["tshirts"]

    
}
</script>

<style lang="scss" scoped>
    #maincontent{
        width: 100%;
        display: flex;
        flex-wrap: wrap;
    }
    .card{
        font-weight: bold;
        width: 330px;
        height: 350px;
        min-width: 330px;
        min-height: 350px;
        padding:10px;
        border: 3px solid black;
        border-radius: 10px;
        margin: 1px;
        background: #2c3e50;
        
    }
    h2{
        font-size: 20px;
    }
</style>


