# 柱形图(bar)

##### 1.设置标题 option.title = {}
###### ● 标题内容
    option.title.text = '商家销售统计'
    option.title.textStyle = {} // 
    option.title.textStyle.fontSize = 20

###### ● 标题位置
    option.title.left = 20
    option.title.top = 20

##### 2.设置图形位置 option.grid = {}
###### ● 上下左右间距
    option.grid.top = '20%'

    option.grid.left = '3%'

    option.grid.right = '6%'

    option.grid.bottom = '3%'

###### ● 距离是否要包含坐标轴文字

    option.grid.containLabel = true

##### 3.设置鼠标提示信息 option.tooltip = {}
###### ● 触发模式

    option.tooltip.trigger = 'axis'

###### ● 指示器设置
    option.tooltip.axisPointer = {}
    option.tooltip.axisPointer.type = 'line' // 线条
    option.tooltip.axisPointer.z = 0 // 层级
    option.tooltip.axisPointer.lineStyle = {} // 指示器线条样式
    option.tooltip.axisPointer.lineStyle.color = '#2d3443'width
    option.tooltip.axisPointer.lineStyle.width = 20

##### 4. x 轴的配置 xAxis = {}
######  ● 轴的类型

    xAxis.type = 'value' // value为数值类型, category为类目轴

##### 5. y 轴的配置 yAxis = {}
######  ● 轴的类型
    yAxis.type = 'value' // value为数值类型, category为类目轴
    yAxis.data = sellerNames // 数组 []

##### 6. 系列的配置 series = [{}, {}, {}....]
######  ● 图形类型
    series[0].type = 'bar' // bar 表示柱状图

######  ● 柱子上文字配置
    series[0].label = {}
    series[0].label.show = true // 是否显示文字
    series[0].label.position = 'right' // 显示位置
    series[0].label.color = '#fff' // 文字颜色barWidth: titleFontSize,
######  ● 柱子宽度
    series[0].barWidth = 15
######  ● 柱子样式
    series[0].itemStyle = {}
    series[0].itemStyle.barBorderRadius = [0, 15, 15, 0] // 柱子圆角
    series[0].itemStyle.color = '#fff' // 文字颜色
    series[0].itemStyle.color = {
        // 线性渐变, x1, y1, x2, y2表示2个点(x轴向右, y轴向下, 这2点确定一个方向, 范围从 0 - 1)
        type: 'linear',
        x1: 0,
        y1: 0,
        x2: 1,
        y2: 0,
        colorStops: [
            // 0% 处的颜色
            { offset: 0, color: '#5052ee' },
            // 100% 处的颜色
            { offset: 1, color: '#ab6ee5' }
        ]
    }
    // 也可以通过 实例对象的线性函数 设置
    series[0].itemStyle.color = new this.$echarts.graphic.LinearGradient(0, 0, 1, 0, [
        { offset: 0, color: '#5052ee' },
        { offset: 1, color: '#ab6ee5' }
    ])
######  ● 数据
    series[0].data = [] // 数组
######  ● 事件
    echartInstance.on('mouseover', () => {}) // mouseover 代表鼠标进入柱子时触发

##### 最后一步(渲染图形)
    echartInstance.setOption(option)
