<template>
    <div>
        <div id="price">
            <p>Price Max :</p>
            <input type="range" name="price" id="rangefilter" min="20" max="40" v-model="maxprice">
             <p>{{ maxprice }} €</p>
        </div>
    </div>
</template>

<script>
export default {
     data(){
        return{
            maxprice: 40
        }
    },
    updated() {
    this.$ebus.$emit("maxprice", this.maxprice);
  }
}
</script>


<style lang="scss" scoped>
    #price{
       display: flex;
       flex-direction: column;
       align-items: center;
       margin: 10px;
    }

input[type=range]{
-webkit-appearance: none;
margin: 10px;
}

input[type=range]::-webkit-slider-runnable-track {
    width: 300px;
    height: 3px;
    background: #42b983;
    border: none;
    border-radius: 3px;
}

input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    border: 2px solid black;
    height: 18px;
    width: 18px;
    border-radius: 50%;
    background: white;
    margin-top: -7px;
}

</style>
