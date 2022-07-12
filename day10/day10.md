## 数字:重复执行操作
语法： 数字 + operation

以前删除3个单词： dw dw dw
d3w / 3dw:一口气删除3个单词  

比如之前学的 5j 5l



2fte
1. 好处 保持连贯的撤销历史记录
2. 坏处 需要有思考的时间（按几合适）所以不是太推荐 除非特定场合：
this is a book
删除两个单词 改成(方块位于a上：c2w)
this is an apple

## 点：重复上一次的修改1.做了更新(增删改)2.离开插入模式之前的全部按键操作都记录

this is a book，this is a bookh is a book
[insert下删除两个字符并回到normal,此时点操作代表insert下删除两字符，按下会重复]
[insert下增加abc并回到normal,此时点操作代表insert下增加abc，按下会重复]
[insert下删除光标前字符并增加abc并回到normal,此时点操作代表insert下删除光标前字符并增加abc增加abc，按下会重复]

[normal模式下按键x表示删除一个字符，此时点操作表示删除字符]
  ook，thicw a  is a book

[删除单词的方式]
1. 光标单词首部 bde (b先移动到首部，be删除)
2. 光标单词尾部dbx (光标单词尾部，db 此时还剩下最后一个字符，用x删除)
3. 光标单词上diw 
衡量：这三种能不能用点操作重复
分析：
1. .只记录[be]  b是移动并不会改变，不会被.操作记录 因此不能达到重复删除单词;;
2. .只记录[x]   .只记录上一次修改，这里有两次修改，所以只记录了x;
3. 完胜！不管光标位于单词哪里都可以记录删除单词操作。 ;

## 核心：一键移动，一键操作
1. 加分号 (三行尾部同时加分号)
      ①原来方式  Vjj A
      ②现在方式  A ; (回到normal) j(下一行). j.  j. 
2. 查找手动替换(有的地方替换有的不替换) 
      比如查找替换vnode成aaa
      ①先搜索  /vnode
      ②n(下一个) 查找到需要替换的 [cw]删除vnode,改成aaa切会normal
      ③n 查找到想替换的 . 


function sdsdsds0000(){
      console.log(vnode,'0000')
      const 0000 ='123'
  return vnode 
}
function sdsdsds0000(){
      console.log(vnode,'0000')
      const 0000 ='123'
  return vnode 
}
2(2). 删除连续多个单词
      [diw] .... (任意多个)   (删多了撤回) u

## 能够重复用点的 就不要用次数