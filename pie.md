# 饼图(pie)

#### 系列 option.series = {}
    option.series[0].type = 'pie' // pie 表示饼图

    option.series[0].radius = 20 // 大小

    option.series[0].radius = [60, 80] // 内圆 60 外圆80 (环状图使用)

    option.series[0].center = ['50%', '60%'] 位置(图形正中央偏下)
    option.series[0].hoverAnimation = false // 鼠标放入时动画不启用
    
    // 普通饼图
    option.series[0].data = [
        { value: 335, name: 'Direct' },
        { value: 310, name: 'Email' },
        { value: 274, name: 'Union Ads' },
        { value: 235, name: 'Video Ads' },
        { value: 400, name: 'Search Engine' }
    ]
    // 环形图(这里做了5个环形图，循环得出其中一个环形图的数据如下)
    option.series[0].data = [
        { 
            value: item.sales,
            name: item.name,  // 只显示一个名字(环状图使用)
            itemStyle: {
                color: 'red'
            }
        },
        { 
            value: item.stock, 
            itemStyle: {
                color: '#333843'
            }
        }
    ]

    option.series[0].label = {} // 文字配置

    option.series[0].label.position = 'center' // 显示在中间(环状图使用)

    option.series[0].label.show = false // 是否显示文字
    option.series[0].labelLine = {} // 饼图 连接线
    option.series[0].labelLine.show = false // 是否显示文字

    option.series[0].emphasis.label.show = false // emphasis 套住的属性表示: 高亮时, 才显示该状态


