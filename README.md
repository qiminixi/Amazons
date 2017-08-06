# 亚马逊棋程序框架

这是一个亚马逊棋框架程序，当年在学校做亚马逊棋时，希望那些没有学习GUI编程的同学，也能够参与进来一起研究计算机博弈，所以从当时的系统中抽出了UI功能，留出电脑计算的接口。现在正式完善了这个框架，并且提供了网络对战功能，以方便调试程序。  

程序使用的是随机走子，**不包含着法计算**，也就没有评估函数和搜索算法了，这些还是自己研究出来比较好。^_^  

功能包括：  
* 基本操作，开始、暂停、走子、放箭、计时等
* 历史步骤查看，前进、后退
* 存档功能（包括开局到当前的所有着法）
* 对局过程中生成临时存档文件，便于查找崩溃信息
* 人机，人人对局、网络对局
* 配置存储
* 着子标识


## 规则简介

* 在10*10的棋盘上，每方有四个棋子；
* 每个棋子走法与国际象棋中的皇后相同，可以在八个方向上任意直线行走，但不能穿过障碍；
* 双方轮流下棋，一次下棋包括两个步骤，首先移动4个棋子中的一个，然后从这个棋子的位置释放一个障碍，障碍的施放规则与棋子移动相同。
* 当某方下完后，对方4个棋子都不能移动时，对方输。（因此可以有平局，比如红方走完后自己死了，这时候不能立马判断红方输，如果之后黑方走了一步后自己也死了，就是平局）
* 对局过程中不能吃棋子或障碍

![screenshot](https://github.com/qiminixi/Amazons/blob/master/Amazons/Release/screenshot.png)



## 开始游戏

（1）默认是电脑和玩家对局，可通过菜单【游戏】-【游戏设置】修改   <br>
（2）点击工具栏左边的【开始按钮】或者点击鼠标右键开始   


## 网络对战

（1）网络对战需要启动GameServer，在GameServer下目录下。运行程序后，设置好ip地址和端口，点击【启动按钮】启动服务器。<br>
（2）游戏设置中设置一方为网络玩家，之后通过菜单【游戏】-【网络】打开网络对话框，设置好服务器地址和端口，连接到服务器。在玩家列表中选择玩家，邀请对局即可。


## 厉害点的程序
在Rlease文件夹中也提供了一个具有一定棋力的游戏程序Amazons_intelligent.exe。只使用了极大极小搜索和简单评估函数。  


## 写自己的代码
如果只对AI感兴趣，则只需要实现CAmazonsAI中的方法就可以，如果想实现游戏控制流程操作，比如文件读写，前进、后退等，则重写CAmazonsGameController中的方法。  


