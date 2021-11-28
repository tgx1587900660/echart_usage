# 折线图(line)

#### 首先初始化echarts实例对象
    const echartInstance = echarts.init(dom, 'chalk') // dom 为网页元素, 'chalk' 为使用的主题(不传则用默认主题)

#### x 轴 option.xAxis = {}
    option.xAxis.type = 'category' // category 表示类目轴
    option.xAxis.boundaryGap = false // 去除边缘间隙(设置贴边)
    option.xAxis.data = ['一月', '二月', '三月', '四月'] // 类目数据

#### y 轴 option.yAxis = {}
    option.yAxis.type = 'value' // 数值轴

#### 系列 option.series = [{},{}...]
    option.series[0].type = 'line' // 折线图
    option.series[0].name = '手机数码' // 这条折线的名字
    option.series[0].stack = 'commodity' // 开启堆叠图(要保证所有成员一致)
    option.series[0].areaStyle = {}
    option.series[0].areaStyle.color = new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [
        { offset: 0, color: colorArr1[index] }, // 渐变颜色, 使用了调色盘遍历
        { offset: 1, color: colorArr2[index] }  // 渐变颜色, 使用了调色盘遍历
    ])

#### 最后一步
    chartInstance.setOption(option)
