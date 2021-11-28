# 通用配置项

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
