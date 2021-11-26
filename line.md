# 折线图(bar)

#### 1.位置 option.grid = {}
    见 bar 图

#### 2.提示 option.tooltip = {}
    见 bar 图

#### 3.图例 option.legend = {}
    option.legend.left = 20
    option.legend.top = 20
    option.legend.icon = 'circle' // 图例的形状
    option.legend.data = ['上海', '北京', '深圳', '广州', '重庆'] // 图例数据
    option.legend.itemWidth = 20 // 小圆点的宽
    option.legend.itemHeight = 20 // 小圆点的高
    option.legend.itemGap = 5 // 小圆点之间的间隙
    option.legend.textStyle = {} // 文字样式
    option.legend.textStyle.fontSize = 16

#### 4.x轴 option.xAxis = {}
    option.xAxis.type = 'category' // category 表示类目轴
    option.xAxis.boundaryGap = false // 去除边缘间隙(设置贴边)
    option.xAxis.data = ['一月', '二月', '三月', '四月'] // 类目数据

#### 5.y轴 option.yAxis = {}
    option.yAxis.type = 'value' // 数值轴

#### 6.系列 option.series = [{},{}...]
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
