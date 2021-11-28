# 饼图(pie)

#### 系列 option.series = {}
    option.series[0].type = 'pie' // pie 表示饼图

    option.series[0].radius = 20 // 大小
    option.series[0].center = ['50%', '60%'] 位置(图形正中央偏下)
    
    option.series[0].data = [
        { value: 335, name: 'Direct' },
        { value: 310, name: 'Email' },
        { value: 274, name: 'Union Ads' },
        { value: 235, name: 'Video Ads' },
        { value: 400, name: 'Search Engine' }
    ]

    option.series[0].label = {} // 文字配置
    option.series[0].label.show = false // 是否显示文字
    option.series[0].labelLine = {} // 饼图 连接线
    option.series[0].labelLine.show = false // 是否显示文字

    option.series[0].emphasis.label.show = false // emphasis 表示高亮时, 显示状态


