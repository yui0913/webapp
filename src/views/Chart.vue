<script>
import { Bar } from 'vue-chartjs';
import firebase from 'firebase';
export default {
  extends: Bar,
  name: 'chart',
  data () {
    return {
      data: {
        labels: [ '~36.9', '37.0~37.4', '37.5~'],
        datasets: [
          {
            data: [15,5,1],
            backgroundColor: [
              '#9AEA65',
              '#F9E353',
              '#F15D5D'
            ],
          }]
      },
      options: {
        legend: {
                display: false
           },
        scales: {
          xAxes: [{
            scaleLabel: {
              display: true,
            }
          }],
          yAxes: [{
            ticks: {
              beginAtZero: true,
              stepSize: 5,
              callback: function (label, index, labels) {
                  return label + '人'; // ラベルに'点'を付ける
                }
            }
          }]
        }
      }
    }
  },
  mounted () {
    this.renderChart(this.data, this.options)
  },
  methods:{
    window:onload = function (){
    var db = firebase.firestore();
    var bodytem = []
    bodytem.map(function (element) { return Number(element); });
    var good = this.good;
    var soso = this.soso;
    var bad = this.bad;
    db.collection("AW").get().then(function(querySnapshot) {
    querySnapshot.forEach(function(doc) {
        // doc.data() is never undefined for query doc snapshots
            bodytem.push(doc.data().temp);
            console.log(bodytem);
    });
var temlength = bodytem.length;
console.log(temlength);
console.log(bodytem);
for (var i = 0; i == temlength ; i++) {
    if(bodytem < 37.0){
      a++
    }
    else if(bodytem > 36.9 && bodytem < 37.5){
      a++
    }
    else if(bodytem > 37.4){
      a++
    }
}
});
  }
  }
}

</script>