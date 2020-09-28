<template>
  <div class="about">
    <div class="logo"><img alt="app logo" src="../img/logo.png"></div>
    <div class="intro ani"><p>ココロとカラダの健康状態を入力し<br>
      仲間の体調の確認ができるアプリです。<br>
      健康状態を見て<br>
      全員での予防意識を高めましょう。
    </p></div>
    <div class="btn ania"><router-link to="/form">体温入力</router-link></div> 
    <div class="btn ania"><router-link to="/index">グラフ画面</router-link></div> 
  </div>
</template>

<style>
.intro p{
  margin:20px 10px;
  line-height: 2.0;
  letter-spacing: 0.06em;
}
.ani {
   opacity: 0;
   animation-name: fadein-bottom;
   animation-duration: 1.5s;
   animation-timing-function: ease-out;
   animation-fill-mode: forwards;
}
.ania{
  opacity: 0;
   animation-name: fadein-bottom;
   animation-delay:0.5s;
   animation-duration: 1.5s;
   animation-timing-function: ease-out;
   animation-fill-mode: forwards;
}
@keyframes fadein-bottom {
   0% {
      opacity: 0;
      transform: translateY(20px);
   }
   100% {
      opacity: 1;
      transform: translateY(0);
   }
}

</style>
