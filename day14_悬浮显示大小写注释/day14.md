## 悬浮显示 gh   _________hover
e.g 光标停到红波浪报错处，键入gh
esc退出

## 大小写 
（operation+范围，gu算"范围"）
1. normal 
      1. gu 变小写
      2. gU
2. 可视化 
      1. u
      2. U
3. 大小写切换  ~(normal和visual都能用)

## 注释
1. gc 单行注释
      gc l 注释当前行
      gc j 注释两行
2. gC 多行注释
      gC iw 注释当前单词
      gC a{ 注释`{ xxxx }`
      
3. tip normal和可视化模式通用

## 练习
```js
// function interface
function /* INTERFACE */ (键入：gu iw / gU iw)
function iNTERFACE (键入：ve u) 选中当前光标到单词末尾，小写
```
日常开发中大写：先小写，再转换成大写.驼峰用shift

