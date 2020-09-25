<template>
<div>
          <a href="../views/Index.vue" v-on:click="store" 
          ><div class="sosin"><img src="./img/sosin.png"></div></a>
      <div class="in">
      <p style="display:inline">ユーザー名</p>
      <input type="text" v-model="userid">
      </div>
      <div class="in">
      <p style="display:inline">体温</p>
      <input type="tel" v-model="bodytem" placeholder="36.0" 
      required maxlength="4" size="10">
      </div>
      <div class="in">
      <p>こころ</p>
      <div class="heartcon">
      <label><input type="radio" id="m_excellent" name="mind" value="m_excellent" v-model="sin"><img src="./img/face_5.2.png" class="radio_image" ></label>
      <label><input type="radio" id="m_good" name="mind" value="m_good" v-model="sin"><img src="./img/face_4.2.png" class="radio_image"></label>
      <label><input type="radio" id="m_nomal" name="mind" value="m_nomal" v-model="sin"><img src="./img/face_3.2.png" class="radio_image"></label>
      <label><input type="radio" id="m_bad" name="mind" value="m_bad" v-model="sin"><img src="./img/face_2.2.png" class="radio_image"></label>
      <label><input type="radio" id="m_worst" name="mind" value="m_worst" v-model="sin"><img src="./img/face_1.2.png" class="radio_image"></label>
      </div>
      </div>
      <div class="in">
      <p>からだ</p>
      <div class="heartcon">
      <label><input type="radio" id="h_excellent" name="health" value="h_excellent" v-model="tai"><img src="./img/face_5.2.png" class="radio_image"></label>
      <label><input type="radio" id="h_good" name="health" value="h_good" v-model="tai"><img src="./img/face_4.2.png" class="radio_image"></label>
      <label><input type="radio" id="h_nomal" name="health" value="h_nomal" v-model="tai"><img src="./img/face_3.2.png" class="radio_image"></label>
      <label><input type="radio" id="h_bad" name="health" value="h_bad" v-model="tai"><img src="./img/face_2.2.png" class="radio_image"></label>
      <label><input type="radio" id="h_worst" name="health" value="h_worst" v-model="tai"><img src="./img/face_1.2.png" class="radio_image"></label>
          </div>
      </div>
      <div class="in">
        <div class="detail">
       <label><input type="radio" id="cold" name="sick" value="cold" v-model="down"><img src="./img/kaze_g.png" class="radio_image"></label>
       <label><input type="radio" id="menstrual" name="sick" value="menstrual" v-model="down"><img src="./img/seri_g.png" class="radio_image"></label>
       <label><input type="radio" id="sleep" name="sick" value="sleep" v-model="down"><img src="./img/nebusoku_g.png" class="radio_image"></label>
       <label><input type="radio" id="climate" name="sick" value="climate" v-model="down"><img src="./img/kikou_g.png" class="radio_image"></label>
      <label><input type="radio" id="other" name="sick" value="other" v-model="down"><img src="./img/sonota_g.png" class="radio_image"></label>
        </div>
      </div>
      <p>{{ message }}</p>
      <p>備考</p>
      <textarea v-model="message" placeholder="備考"></textarea>
</div>
</template>
<style>
  .radio_image{
    width:45px;
  }
#m_excellent,#m_good,#m_nomal,#m_bad,#m_worst,#h_excellent,#h_good,#h_nomal,#h_bad,#h_worst,#cold,#menstrual,#sleep,#climate,#other {
	display: none;
}
#m_excellent:checked + .radio_image,
#m_good:checked + .radio_image,
#m_nomal:checked + .radio_image,
#m_bad:checked + .radio_image,
#m_worst:checked + .radio_image,
#h_excellent:checked + .radio_image,
#h_good:checked + .radio_image,
#h_nomal:checked + .radio_image,
#h_bad:checked + .radio_image,
#h_worst:checked + .radio_image,
#cold:checked + .radio_image,
#menstrual:checked + .radio_image,
#sleep:checked + .radio_image,
#climate:checked + .radio_image,
#other:checked + .radio_image
 {
	border: 3px #ff0000 solid;
  border-radius:100px;
}
.sosin{
  text-align:right;
}
.in{
margin-left:20px;
margin-right:20px;
}
.face img{
  width: 45px;
  height: 45px;
}
.sick img{
  height: 20px;
}
</style>
          <!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/7.18.0/firebase-app.js"></script>
<!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
<script>
import firebase from 'firebase'
  export default{
    data() {
      return {
        title: '20200922',
        bodytem: this.bodytem,
        tai: this.tai,
        sin: this.sin,
        down: this.down,
        message: this.message,
        userid: this.userid,
      }
    },
    methods:{
      store(){
      var db = firebase.firestore();
        db.collection(this.userid).doc(this.title).set({
    temp: this.bodytem,
    bodycon: this.tai,
    heartcon: this.sin,
    sick: this.down,
    msg: this.message
})
.then(function() {
    console.log("Document successfully written!");
})
.catch(function(error) {
    console.error("Error writing document: ", error);
})
if(event){
  alert("入力が完了しました。ご協力ありがとうございます。")
}
}
      }
    }
</script>