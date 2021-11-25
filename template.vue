<!-- 横向柱状图组件 -->
<template>
    <div class="com-container">
        <div class="com-chart" ref="sellerRef"></div>
    </div>
</template>

<script>
export default {
    name: 'tgx-seller',
    data() {
        return {
            // echarts 实例对象
            chartInstance: null,
            // allData: [
            //     { name: '商家1', value: 99 },
            //     { name: '商家2', value: 102 },
            //     { name: '商家3', value: 83 },
            //     { name: '商家4', value: 49 },
            //     { name: '商家5', value: 200 },
            //     { name: '商家6', value: 152 },
            //     { name: '商家7', value: 76 },
            //     { name: '商家8', value: 23 },
            //     { name: '商家9', value: 87 },
            //     { name: '商家10', value: 223 },
            //     { name: '商家11', value: 145 },
            //     { name: '商家12', value: 187 },
            //     { name: '商家13', value: 127 },
            //     { name: '商家14', value: 57 },
            //     { name: '商家15', value: 99 }
            // ],
            // 所有数据
            allData: []
        }
    },
    mounted() {
        this.initChart()
        this.getData()
        // 自适应屏幕方法
        window.addEventListener('resize', this.screenAdapter)
        // 首次进入需要手动调用一次适应屏幕
        this.screenAdapter()
    },
    beforeDestroy() {
        // 组件销毁时解绑事件
        window.removeEventListener('resize', this.screenAdapter)
    },
    methods: {
        // 初始化 echarts 实例对象
        initChart() {
            this.chartInstance = this.$echarts.init(this.$refs.sellerRef, 'chalk')
            // 初始化固定的配置项
            const initOption = {}
            this.chartInstance.setOption(initOption)
        },
        // 获取图表数据
        async getData() {
            const { data: res } = await this.$http.get('seller')
            this.allData = res
        },
        // 设置图表数据
        updateChart() {
            const dataOption = {}
            this.chartInstance.setOption(dataOption)
        },
        // 屏幕大小变化时调用的函数
        screenAdapter() {
            // const titleFontSize = (this.$refs.sellerRef.offsetWidth / 100) * 3.6
            const adapterOption = {}
            this.chartInstance.setOption(adapterOption)
            this.chartInstance.resize()
        }
    }
}
</script>

<style lang="less" scoped></style>
