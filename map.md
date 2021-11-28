# 地图 和 涟漪图 (map, scatter)

#### 绘图步骤
    // 1.初始化实例对象
    const echartInstance = echarts.init(dom, 'chalk') // dom 为网页元素, 'chalk' 为使用的主题(不传则用默认主题)

    // 2.准备地图矢量数据(这里获取的是本地数据)
    const { data } = await axios.get('http://localhost:8999/static/map/china.json')

    // 3.注册并初始化地图
    echarts.registerMap('china', data) // 'china' 是为该地图取的名字, data 是该地图绑定的数据

    // 4.准备 option
    const option = {}

    // 5.绘制图形
    echartInstance.setOption(option)

#### 地图配置 option.geo = {}
    option.geo.type = 'map' // 表示要绘制地图
    option.geo.map = 'china' // 要绘制哪一个地图(即第3步中注册的地图 china )

    option.geo.top = '5%' // 位置
    option.geo.bottom = '5%'

    option.geo.itemStyle = {} // 地图块样式
    option.geo.itemStyle.areaColor = '#2e72bf' // 区块颜色
    option.geo.itemStyle.borderColor = '#333' // 边界颜色

#### 系列 option.series = [{}, {}, {}....]
    option.series[0].type = 'effectScatter' // effectScatter 表示涟漪图, scatter 表示散点图
    option.series[0].rippleEffect = {} // 涟漪效果
    option.series[0].rippleEffect.scale = 5 // 范围大小
    option.series[0].rippleEffect.brushType = 'stroke' // 空心涟漪效果

    option.series[0].name = '黄金用户' // 散点类型名(与图例 legend 对应)
    option.series[0].data = [{name: '武汉', value: {0: 114.31, 1: 30.52}},{},{}......] // 散点的数据(每个点有两个数据 name 和 value)

    option.series[0].coordinateSystem = 'geo' // 开启地图联动 (即散点在地图上绘制)
    
#### 地图事件
    echartInstance.on('click', (e) => {}) // click 代表鼠标点击省份时触发, e 为该区域详情
