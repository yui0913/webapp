<script>
import { Bar } from 'vue-chartjs';
export default {
  extends: Bar,
  name: 'chart',
  data () {
    return {
      data: {
        labels: ['~35.9', '36.0~36.9', '37.0~37.9', '38.0~38.9', '39.0'],
        datasets: [
          {
            label: '人数',
            data: [3, 20, 0, 0, 0],
            backgroundColor: [
              '#F9AE53',
              '#F9AE53',
              '#F9AE53',
              '#F9AE53',
              '#F9AE53'
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