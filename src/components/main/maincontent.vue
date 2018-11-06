<template>
<div>
    <produits :tshirts="filter"></produits>
</div>
</template>

<script>
import produits from "@/components/main/tshirts.vue"
export default {
    data(){
      return{
        tshirts:[
              {nom: "Rose",marque: "Obey",images: require("@/assets/obey.png"), prix: 20, couleur:"black"},
              {nom: "Skull & Bones",marque: "CBGB",images: require("@/assets/cbgb.png"), prix: 34, couleur:"black"},
              {nom: "Dickies Logo",marque: "Dickies",images: require("@/assets/dickies.png"), prix: 20, couleur:"white"},
              {nom: "Future",marque: "Element",images: require("@/assets/element.jpeg"), prix: 28, couleur:"turquoise"},
              {nom: "T-rex",marque: "Zoo York",images: require("@/assets/zooyork.png"), prix: 23, couleur:"green"},
              {nom: "Obey x Misfits",marque: "Obey",images: require("@/assets/obey2.jpg"), prix: 40, couleur:"red"},
              {nom: "Better en Noir",marque: "The Kooples",images: require("@/assets/thekoople.png"), prix: 30, couleur:"white"},
              {nom: "CBGB Logo",marque: "CBGB",images: require("@/assets/cbgc2.png"), prix: 25, couleur:"black"},
              {nom: "Ours",marque: "Element",images: require("@/assets/element2.png"), prix: 36, couleur:"grey"}],

        maxprice:"",
        checkedBrands: [],
        pickedcolors: [],
        }
    },
    components:{
        produits
    },
    //Recuperation des ebus
    created() {
        this.$ebus.$on("maxprice", payload => {
          this.maxprice = payload;
        });
        this.$ebus.$on("checkedBrands", payload => {
          this.checkedBrands = payload;
        });
        this.$ebus.$on("pickedcolors", payload => {
          this.pickedcolors = payload;
    });
    },
    computed: {

         filter: function() {
      //Affichage par defaut
      if (
        this.maxprice.length === 0 &&
        this.checkedBrands.length === 0 &&
        this.pickedcolors.length === 0
      ) {
        return this.tshirts;
        // filtrer par prix
      } else if (
        this.maxprice.length !== 0 &&
        this.checkedBrands.length === 0 &&
        this.pickedcolors.length === 0
      ) {
        return this.tshirts.filter(tshirts => {
          return tshirts.prix <= this.maxprice;
        });
        //filtrer par marques
      } else if (
        this.maxprice.length === 0 &&
        this.checkedBrands.length !== 0 &&
        this.pickedcolors.length === 0
      ) {
        return this.tshirts.filter(tshirts => {
          return this.checkedBrands.includes(tshirts.marque);
        });
        //filtrer par couleur
      } else if (
        this.maxprice.length === 0 &&
        this.checkedBrands.length === 0 &&
        this.pickedcolors.length !== 0
      ) {
        return this.tshirts.filter(tshirts => {
          return this.pickedcolors.includes(tshirts.couleur);
        });
        //filtrer par prix et marques
      } else if (
        this.maxprice.length !== 0 &&
        this.checkedBrands.length !== 0 &&
        this.pickedcolors.length === 0
      ) {
        return this.tshirts.filter(tshirts => {
          return (
            tshirts.prix <= this.maxprice &&
            this.checkedBrands.includes(tshirts.marque)
          );
        });
        //filtrer par prix et couleur
      } else if (
        this.maxprice.length !== 0 &&
        this.checkedBrands.length === 0 &&
        this.pickedcolors.length !== 0
      ) {
        return this.tshirts.filter(tshirts => {
          return (
            tshirts.prix <= this.maxprice &&
            this.pickedcolors.includes(tshirts.couleur)
          );
        });
        //filtrer par marques et couleur
      } else if (
        this.maxprice.length === 0 &&
        this.checkedBrands.length !== 0 &&
        this.pickedcolors.length !== 0
      ) {
        return this.tshirts.filter(tshirts => {
          return (
            this.checkedBrands.includes(tshirts.marque) &&
            this.pickedcolors.includes(tshirts.couleur)
          );
        });
        //filtrer par prix, marque et couleur
      } else {
        return this.tshirts.filter(tshirts => {
          return (
            tshirts.prix <= this.maxprice &&
            this.checkedBrands.includes(tshirts.marque) &&
            this.pickedcolors.includes(tshirts.couleur)
          );
        });
      }
    }
    }
}

</script>
