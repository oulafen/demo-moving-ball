# 使用canvas实现运动的小球
示例地址：[链接](http://oulafen.github.io/demo-moving-ball/)

## 运动原理
桢重绘
```
setInterval(function () {
    render(context);
    update();
}, 50)
```

## 运动定义
- 水平速度
- 垂直速度
- 重力加速度
```
var ball = {
    x: windowWidth * 0.6, 
    y: windowHeight * 0.2,
    r: 20, 
    g: 2, 
    vx: -5, 
    vy: 0, 
    color: '#005588'
    }
```
## 轨迹变化
根据速度改变绘制位置
```
ball.x += ball.vx;
ball.y += ball.vy;
ball.vy += ball.g; 
```

## 碰撞检测
例：
```
 // 底部检测
if (ball.y > (boxHeight - ball.r)) {
    ball.y = boxHeight - ball.r;
    ball.vy = -ball.vy * 0.7;  //0.7为摩擦系数
}
```