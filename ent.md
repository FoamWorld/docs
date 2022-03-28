# 实体信息
## 通用属性
|属性名|类型|描述|
|:-:|:-:|:-:|
|x|Float|x坐标|
|y|Float|y坐标|

## 通用接口
|函数名|参数类型（第一个参数为Entity类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|move!|Float,Float||移动（计算碰撞箱）||

* 允许在函数第二参数栏（`;`后）增加参数，但必须提供默认值
* `w`开头函数名保证不会被占用

## 列表
* **生物**
	+ 玩家