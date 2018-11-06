<template>
<div>
     <div id="brands">
        <p>Brands :</p>
        <ul>
            <li>Obey <input type="checkbox" value="Obey" name="Obey"  v-model="checkedBrands"></li>
            <li>Zoo York <input type="checkbox" value="Zoo York" name="Zoo York"  v-model="checkedBrands"></li>
            <li>The Kooples <input type="checkbox" value="The Kooples" name="The Kooples" v-model="checkedBrands"></li>
            <li>Element <input type="checkbox" value="Element" name="Element"  v-model="checkedBrands"></li>
            <li>CBGB <input type="checkbox" value="CBGB" name="CBGB" v-model="checkedBrands"></li>
            <li>Dickies <input type="checkbox" value="Dickies" name="Dickies"  v-model="checkedBrands"></li>
        </ul>
    </div>


</div>
</template>

<script>
export default {
    data() {
        return {
            checkedBrands: []
    };
  },
    updated() {
    this.$ebus.$emit("checkedBrands", this.checkedBrands);
  }
}
</script>


<style lang="scss" scoped>
    #brands{
        display: flex;
        flex-direction: column;
        align-items: center;

        ul{
            list-style: none;
            width: 80%;

            li{
                display: flex;
                justify-content: space-between;
                
            }
        }
    }
    
</style>

