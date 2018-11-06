<template>
<div>
                    <div id="color">
                    <p>Colors :</p>
                    <div id="pickcolor">
                        <div class="colored black" data-value="black" @click="getColor" ></div> 
                        <div class="colored white" data-value="white" @click="getColor"></div>
                        <div class="colored grey" data-value="grey" @click="getColor" ></div>
                        <div class="colored red" data-value="red" @click="getColor" ></div>
                        <div class="colored green" data-value="green" @click="getColor" ></div>
                        <div class="colored turquoise" data-value="turquoise" @click="getColor" ></div>
                    </div>
                </div>

</div>
</template>

   <script>
export default {
  data() {
    return {
      colored: [],
    };
  },
  methods: {
    //pick la couleur selectionné
    getColor(evt) {
      let pickedColor = evt.srcElement.getAttribute("data-value");
      evt.target.classList.toggle("active");
      this.listedColors(pickedColor);
 
    },
    //ajoute ou enleve la couleur selectionné dans colored
    listedColors(color) {
      if (!this.colored.includes(color)) {
        this.colored.push(color);
        this.$ebus.$emit("pickedcolors", this.colored);
      } else {
        let colorIndex = this.colored.indexOf(color);
        this.colored.splice(colorIndex, 1);
        this.$ebus.$emit("pickedcolors", this.colored);
      }
    }
  }
};
</script>


<style lang="scss" scoped>
    #color{
        display: flex;
        flex-direction: column;
        align-items: center;
        

        #pickcolor{
            display: flex;
            
            .colored{
                cursor: pointer;
                height: 25px;
                width: 25px;
                margin-left: 10px;
                border: 2px solid black;
                transition: 1s;
                

                &:nth-child(1){
                    background: black;
                }

                &:nth-child(2){
                    background: white;
                }

                &:nth-child(3){
                    background: grey;
                }

                &:nth-child(4){
                    background: red;
                }
                &:nth-child(5){
                    background: green;
                }
                &:nth-child(6){
                    background: turquoise;
                }
   
            }
            .active{
                border: 3px solid #42b983;
                border-radius: 50%;
            }
        }
    }   



</style>


