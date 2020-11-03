<script>
import datas from './assets/フィロソフィーのダンス/ダンス・オア・ダンス/ダンス・オア・ダンス.json'
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  props: ['data', 'options'],

  mounted () {
    this.renderChart({
      labels: [...datas.bars].map(value => value.start),
      datasets: [
        {
          label: 'Data',
          backgroundColor: '#f87979',
           borderDash: [5, 5],
          borderWidth: 1,
          data: [...datas.bars].map(value => value.confidence) 
        }
      ]
    })
  }
}
</script>
<style>
</style>
