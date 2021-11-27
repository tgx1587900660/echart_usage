# 柱形图(bar)
#### 首先初始化echarts实例对象
    const echartInstance = echarts.init(dom, 'chalk') // dom 为网页元素, 'chalk' 为使用的主题(不传则用默认主题)

#### 标题 option.title = {}
    option.title.left = 20 // 距离左侧位置
    option.title.top = 20 // 距离顶部位置

    option.title.text = '商家销售统计'

    option.title.textStyle = {} // 标题样式
    option.title.textStyle.fontSize = 20
    
#### 位置 option.grid = {}
    option.grid.top = '20%'
    option.grid.left = '3%'
    option.grid.right = '6%'
    option.grid.bottom = '3%'

    option.grid.containLabel = true // 距离是否要包含坐标轴文字

#### 鼠标提示信息 option.tooltip = {}
    option.tooltip.trigger = 'axis' // 触发模式

    option.tooltip.axisPointer = {} // 指示器设置
    option.tooltip.axisPointer.type = 'line' // 线条
    option.tooltip.axisPointer.z = 0 // 层级

    option.tooltip.axisPointer.lineStyle = {} // 指示器线条样式
    option.tooltip.axisPointer.lineStyle.color = '#2d3443'width
    option.tooltip.axisPointer.lineStyle.width = 20

#### 区域缩放 option.dataZoom = {}
    option.dataZoom.show = true // 显示区域缩放

    // 筛选10条数据
    option.dataZoom.startValue = 0 // 开始位置
    option.dataZoom.endValue = 9 // 结束位置

#### x 轴的配置 xAxis = {}
    xAxis.type = 'value' // value为数值类型, category为类目轴

#### y 轴的配置 yAxis = {}
    yAxis.type = 'category' // category 为类目轴
    yAxis.data = ['商家8', '商家4', '商家14', '商家7', '商家3'] // 数组

#### 系列的配置 series = [{}, {}, {}....]
    series[0].type = 'bar' // bar 表示柱状图

    series[0].label = {} // 柱子上文字配置
    series[0].label.show = true // 是否显示文字
    series[0].label.position = 'right' // 显示位置
    series[0].label.color = '#fff' // 文字颜色barWidth: titleFontSize,

    series[0].barWidth = 15 // 柱子宽度

    series[0].itemStyle = {} // 柱子样式
    series[0].itemStyle.barBorderRadius = [0, 15, 15, 0] // 柱子圆角
    // 多种配置颜色的方式
    series[0].itemStyle.color = '#fff' // 文字颜色
    series[0].itemStyle.color = {
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
    series[0].itemStyle.color = new this.$echarts.graphic.LinearGradient(0, 0, 1, 0, [
        { offset: 0, color: '#5052ee' },
        { offset: 1, color: '#ab6ee5' }
    ])

    series[0].data = [23, 49, 57, 76, 83] // 对应类目的数据
    
#### 事件
    echartInstance.on('mouseover', () => {}) // mouseover 代表鼠标进入柱子时触发 

#### 最后一步(渲染图形)
    echartInstance.setOption(option)
