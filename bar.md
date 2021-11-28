# 柱形图(bar)
#### 首先初始化echarts实例对象
    const echartInstance = echarts.init(dom, 'chalk') // dom 为网页元素, 'chalk' 为使用的主题(不传则用默认主题)

#### x 轴的配置 option.xAxis = {}
    option.xAxis.type = 'value' // value为数值类型, category为类目轴

#### y 轴的配置 option.yAxis = {}
    option.yAxis.type = 'category' // category 为类目轴
    option.yAxis.data = ['商家8', '商家4', '商家14', '商家7', '商家3'] // 数组

#### 系列的配置 option.series = [{}, {}, {}....]
    option.series[0].type = 'bar' // bar 表示柱状图

    option.series[0].label = {} // 柱子上文字配置
    option.series[0].label.show = true // 是否显示文字
    option.series[0].label.position = 'right' // 显示位置
    option.series[0].label.color = '#fff' // 文字颜色barWidth: titleFontSize,

    option.series[0].barWidth = 15 // 柱子宽度

    option.series[0].itemStyle = {} // 柱子样式
    option.series[0].itemStyle.barBorderRadius = [0, 15, 15, 0] // 柱子圆角
    // 多种配置颜色的方式
    option.series[0].itemStyle.color = '#fff' // 文字颜色
    option.series[0].itemStyle.color = {
        // 线性渐变, x1, y1, x2, y2表示2个点(x轴向右, y轴向下, 这2点确定一个方向, 范围从 0 - 1)
        type: 'linear',
        x1: 0,
        y1: 0,
        x2: 1,
        y2: 0,
        colorStops: [
            { offset: 0, color: '#5052ee' }, // 0% 处的颜色
            { offset: 1, color: '#ab6ee5' } // 100% 处的颜色
        ]
    }
    // 也可以通过 实例对象的线性函数 设置
    option.series[0].itemStyle.color = new this.$echarts.graphic.LinearGradient(0, 0, 1, 0, [
        { offset: 0, color: '#5052ee' },
        { offset: 1, color: '#ab6ee5' }
    ])

    option.series[0].data = [23, 49, 57, 76, 83] // 对应类目的数据

#### 最后一步(渲染图形)
    echartInstance.setOption(option)
