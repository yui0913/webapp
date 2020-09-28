<template>
  <div class="home">
    <div class="logo"><img alt="app logo" src="../img/logo.png"></div>
    <div class="btn"><router-link to="/about">はじめる</router-link></div> 
  </div>
</template>

<script>

</script>

<style>
.logo img{
  height: 50%;
  width: 50%;
  margin: 50px 0 0 0;
}
.btn{
  margin:30px auto;
  background-color: #F9AE53;
  padding: 2%;
  width: 40%;
}
.btn a{
  text-decoration: none;
  color:#333333;
  letter-spacing: 0.08em;
}
</style>