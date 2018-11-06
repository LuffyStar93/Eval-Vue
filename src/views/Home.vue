<template>
  <div class="home">
    <h1>Bienvenue sur TeeShirtz</h1>
    <p>Entreprise privée @ P3 Simplon Aulnay <br>
        Evaluation Challenge T-shirts <br>
        Maxime Chagnon</p>

        <button onclick="window.location.href='/shop'">Clique pour voir le Shop</button>
  </div>
</template>

<style lang="scss" scoped>
.home{
  padding-top: 100px;
  h1{
    font-size: 40px;
  }
  p{
    font-weight: bold;
    font-size: 22px;
  }

  button{
    margin-top: 30px;
    width: 300px;
    height: 150px;
    border: 3px solid #2c3e50;
    border-radius:10px;
    cursor: pointer;
    background: #42b983;
    color: #2c3e50;
    font-weight: bold;
    font-size: 22px;
    text-transform: uppercase;
    transition: 1s;

    &:hover{
      background:#2c3e50;
      border: 3px solid #42b983;
      border-radius: 50%;
      color:#42b983;
    }
  }
}
</style>

