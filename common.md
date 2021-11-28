# 通用配置项

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

#### 图例 option.legend = {}
    // 位置
    option.legend.left = 20
    option.legend.top = 20

    // 形状、数据
    option.legend.icon = 'circle' // 图例的形状
    option.legend.data = ['上海', '北京', '深圳', '广州', '重庆'] // 图例数据

    // 大小、间隙
    option.legend.itemWidth = 20 // 小圆点的宽
    option.legend.itemHeight = 20 // 小圆点的高
    option.legend.itemGap = 5 // 小圆点之间的间隙

    // 样式
    option.legend.textStyle = {} // 文字样式
    option.legend.textStyle.fontSize = 16

    // 布局
    option.legend.orient = 'vertical' // 图例垂直显示

#### 鼠标提示信息 option.tooltip = {}
    option.tooltip.show = true // 是否显示
    option.tooltip.trigger = 'axis' // 触发模式

    // 自定义提示(针对饼图)
    option.tooltip.formatter = e => {
        const { value: total, children } = e.data // 解构出总数 total
        let tipText = ''
        children.forEach(item => { // 拼接该分类下的所有子分类, 计算出百分比, 使用 <br> 标签换行
            tipText += `${item.name}：${((item.value / total) * 100).toFixed(2)}%<br>`
        })
        return tipText
    }

    // 针对柱状图时(柱子的指示器)
    option.tooltip.axisPointer = {} // 指示器设置
    option.tooltip.axisPointer.type = 'line' // 线条
    option.tooltip.axisPointer.z = 0 // 层级
    option.tooltip.axisPointer.lineStyle = {} // 指示器线条样式
    option.tooltip.axisPointer.lineStyle.color = '#2d3443'
    option.tooltip.axisPointer.lineStyle.width = 20

#### 区域缩放 option.dataZoom = {}
    option.dataZoom.show = true // 显示区域缩放

    // 筛选10条数据
    option.dataZoom.startValue = 0 // 开始位置
    option.dataZoom.endValue = 9 // 结束位置
    
#### 事件
    echartInstance.on('mouseover', () => {}) // mouseover 代表鼠标进入柱子时触发 