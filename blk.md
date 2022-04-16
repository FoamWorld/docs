# 方块信息
## 通用接口
|函数名|参数类型（第一个参数为Block类型，不再重复）|返回值类型|描述|备注|
|:-:|:-:|:-:|:-:|:-:|
|id||String:类型名|（作为物品时）唯一辨识符||
|stack||UInt8:4|（作为物品时）最大堆叠数|≤16|
|c_use||Bool:false|能否使用|c:can|
|use|Int,Int||开始使用|参数是方块坐标|
|e_use|||结束使用|e:end|
|updg|||更新GUI||
|i_show|*Canvas*||（作为物品时）显示|i:item|
|b_show|*Canvas*,Int,Int||（作为方块时）显示|b:block|
|colbox|Int,Int|CollisionBox2|碰撞箱||
|hard||UInt:加载于`硬度dict`|硬度||
|light||UInt8:0|亮度|<16|
|hole||Bool|显示图像使是否包含背景||
|e_put|Int,Int||玩家放置后执行|默认不会调用exist|
|exist|Int,Int||诞生时执行||
|e_exist|Int,Int||湮灭时执行||
|li_show|Int,Int,UInt8:方块亮度||影响周围亮度||
|upd|Int,Int||状态更新||
|transparent||Bool|是否透明||

* 允许在函数第二参数栏（`;`后）增加参数，但必须提供默认值
* `w`开头函数名保证不会被占用

## 指定的field
|名称|类型|描述|
|:-:|:-:|:-:|
|background_color||背景色|
|color||颜色|
|dire|UInt8|朝向，通常是面朝放置者位置，通常范围`0x0~0x3`|
|ib|IB|物品管理|
|mat|Material|材料|
|t|UInt8|表示一类方块中一个的编号|
|text||文字|

## 列表
* **气体**
	+ 空气 占位
	+ 虚无
* **液体**
	+ 水
	+ 岩浆
* **固体**
	+ 星岩
	+ 玻璃
	+ 沙子
	+ 半砖 对材料类型的一层包裹
	+ 冰
	+ 地毯
	+ 高炉壁
	+ 高炉控制器
	+ 告示牌
	+ 合成台
	+ 结构方块
	+ 刻制台
	+ 块 对材料类型的一层包裹
	+ 模具台
	+ 木板
	+ 树苗
	+ 叶子
	+ 箱子
	+ 原木
	+ 组装台
	+ [Befunge](blk/Befunge.md)
	* **岩石**
		+ 石头 基本地形元素
		+ 花岗岩
		+ 安山岩
		+ 玄武岩
		+ 闪长岩
		+ 黑曜岩
		+ 萤石
	* **花**
		+ 番红花
