<template>
  <div class="echarts"></div>
</template>
<script>
import * as echarts from 'echarts/core'
import { CanvasRenderer } from 'echarts/renderers'
echarts.use([CanvasRenderer])
export default {
  name: 'vue-echarts',
  props: {
    options: {
      type: Object,
      required: true
    }
  },
  methods: {
    init (opt) {
      if (!this.chart) {
        this.chart = echarts.init(this.$el)
      }
      this.chart.setOption(this.options)
    },
    setChartOption (opt) {
      if (this.chart && opt) {
        this.chart.setOption(opt)
      }
    }
  },
  mounted () {
    this.init()
  }
}
</script>
<style lang="scss" scoped>
.echarts {
  width: 100%;
  height: 100%;
}
</style>
