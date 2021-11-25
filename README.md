# echarts八大图表类型记忆图

### 组件封装模版
见 template.vue 文件

### 1.柱形图(bar)

##### 1.设置标题
option.title = {
    text: '商家销售统计',
    left: 20,
    top: 20
}
##### 2.设置图形的上下左右间距
option.grid = {
    top: '20%',
    left: '3%',
    right: '6%',
    bottom: '3%',
    <!-- 距离要包含坐标轴文字 -->
    containLabel: true
}

##### 3.设置柱状图鼠标提示信息
option.tooltip = {
    <!-- 触发方式 -->
    trigger: 'axis',
    <!-- 指示器配置 -->
    axisPointer: {
        <!-- 线条 -->
        type: 'line',
        <!-- 层级 -->
        z: 0,
        <!-- 线条样式 -->
        lineStyle: {
            color: '#2d3443'
        }
    }
}

echartInstance.setOption(option)

### 2.折线图(line)
### 3.地图(map)

连接展示如下
[地址名](https://blog.gitee.com)
