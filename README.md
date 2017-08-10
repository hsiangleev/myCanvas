# 简易贪吃蛇实现思路：<br>
1. 沙箱模式封装图片加载函数，对外暴露loadImg(imgUrl,Fn)函数，
其中imgUrl为图片地址（对象），Fn为回调函数。<br>
2. 创建整个游戏函数，封装为DrawSnake，单例模式对外暴露DrawSnake（）<br>
  2.1 原型中创建随机生成食物函数food，思路为把20（整个游戏以20为一个单位）的倍数放入数组，随机取出其中一个。
  2.2 初始化蛇身
  2.3 蛇头移动（headMove（））<br>
    >>a. 每次移动之前获取当前的蛇头坐标<br>
    >>b. 重新获取蛇身节点<br>
    >>c. 若屏幕宽度小于768，则认为是手机端，显示控制按钮，否则为键盘控制<br>
    >>d. 初始化四个方向布尔值，按钮或键盘改变的是布尔值真假，每次只有一个为真<br>
    >>e. 若蛇头碰撞到四周，则over为true；若蛇头碰到蛇身，则over为true。<br>
  2.4 蛇身移动<br>
    >>a. bodyMoveDelete（），未吃到食物，则删除蛇尾，并把蛇尾添加到蛇头<br>
    >>b. bodyMoveClone（），吃到食物，则复制蛇头节点为新节点，修改坐标为原蛇头坐标，添加到蛇头，并重新生成食物<br>
  2.5 bodyArr（）<br>
    >>a. 所有蛇身坐标存入数组，用以判断蛇头是否撞到蛇身，即蛇头坐标等于数组其中的一个<br>
    >>b. 用蛇身的长度来确定得分<br>
3. 设置游戏难度<br>
   通过点击难度按钮修改定时器执行时间
