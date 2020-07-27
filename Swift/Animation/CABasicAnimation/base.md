### 1、类的继承关系图

<img src='https://raw.githubusercontent.com/XueWuQianKun/LearnNotes/master/Swift/Animation/images/class_relation.png'>



### 2、动画的各个属性及作用

>##### 属性
>
>fromValue`: 动画的开始值(**Any**类型, 根据动画不同可以是`CGPoint`、NSNumber等)
>
>`toValue`: 动画的结束值, 和fromValue类似
>
>`beginTime`: 动画的开始时间
>
>`duration` : 动画的持续时间
>
>`repeatCount` : 动画的重复次数
>
>`fillMode`: 动画的运行场景
>
>`isRemovedOnCompletion`: 完成后是否删除动画
>
>`autoreverses`: 执行的动画按照原动画返回执行
>
>`path`：关键帧动画中的执行路径
>
>`values`: 关键帧动画中的关键点数组
>
>`animations`: 组动画中的动画数组
>
>`delegate` : 动画代理, 封装了动画的执行和结束方法
>
>##### `timingFunction`: 控制动画的显示节奏, 系统提供五种值选择，分别是：
>1.`kCAMediaTimingFunctionDefault`( 默认，中间快)
>2.`kCAMediaTimingFunctionLinear` (线性动画)
>3.kCAMediaTimingFunctionEaseIn (先慢后快 慢进快出）
>4.`kCAMediaTimingFunctionEaseOut` (先块后慢快进慢出）
>5.`kCAMediaTimingFunctionEaseInEaseOut` (先慢后快再慢)
>
>##### type： 过渡动画的动画类型，系统提供了多种过渡动画, 分别是:
>1: `fade` (淡出 默认)
>2: `moveIn` (覆盖原图)
>3: `push` (推出)
>4: `fade` (淡出 默认)
>5: `reveal` (底部显示出来)
>6: `cube` (立方旋转)
>7: `suck` (吸走)
>8: `oglFlip` (水平翻转 沿y轴)
>9: `ripple` (滴水效果)
>10: `curl` (卷曲翻页 向上翻页)
>11: `unCurl` (卷曲翻页返回 向下翻页)
>12: `caOpen` (相机开启)
>13: `caClose` (相机关闭)
>
>##### subtype : 过渡动画的动画方向, 系统提供了四种,分别是:
>1.`fromLeft`( 从左侧)
>2.`fromRight` (从右侧)
>3.`fromTop` (有上面）
>4.`fromBottom` (从下面）