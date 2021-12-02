# 后端处理
#### 第一步：后端安装 ws 包 
    npm i ws -S

#### 第二步：创建对象
    const WebSocket = require('ws)
    const wss = WebSocket.Server({
        port: 9998
    })

#### 第三步：监听事件
    // 监听客户端连接事件
    wss.on('connection', client => {
        console.log('客户端连接成功了......')

        // 监听客户端 message 事件
        client.on('message', msg => {
            console.log('客户端向后端服务器发送了数据：' + msg)
        })
        
        // 后端往前端发送的数据
        client.send('hello socket from bachend......')
    })