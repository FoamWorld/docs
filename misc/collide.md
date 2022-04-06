# 碰撞信息
## 类型系统
* **CollisionBox2**
	+ EmptyCollisionBox 空碰撞箱
	+ `BCollisionBox{T}(lx,ly,rx,ry)` 横平竖直的矩形碰撞箱
	+ `SegCollisionBox{T}(lx,ly,rx,ry)` 线段碰撞箱，保证lx≤rx
	+ `CirCollisionBox{T}(x,y,r)` 圆碰撞箱

## 相关函数
|函数名|参数列表|返回值列表|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|collide|CollisionBox2,CollisionBox2|Bool|检验碰撞||
|collide|CollisionBox2,Dimension|检验碰撞||
|collide_move|CirCollisionBox,Dimension,Number,Number,UInt8:8|移动并计算碰撞箱|使用二分法，最后一个参数表示二分次数|
