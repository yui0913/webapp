<script>
import { Bar } from 'vue-chartjs';
export default {
  extends: Bar,
  name: 'chart',
  data () {
    return {
      data: {
        labels: [ '~36.9', '37.0~37.4', '37.5~'],
        datasets: [
          {
            label: '人数',
            data: [3, 10, 5],
            backgroundColor: [
              '#9AEA65',
              '#F9E353',
              '#F15D5D'
            ],
          }
        ]
      },
      options: {
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
  }
}
</script>