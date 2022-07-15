## 注释gc enter
<!-- ssdsd -->
<!-- sdsdklsjdl gc -->

## 处理包裹字符的符号

vim-surround 
1. change* existing surround to desired 改变当前字符已经存在的符号 ————————  c s <existing> <desired>
2. add* desired surround around text defined by      ———————— y s <motion>(范围) <desired> (期望值)

3. delete exsiting surround  ——————————— d s <exsiting>
4. 大写的S surround when in visual modes(surround full selection)  —————— S <desired> *用的不多,normal模式下不好指定范围时可以用

```js
import { add } from './add'
import { 'add' } from './add'
      function patchElement =(
            n1:VNode,
            n2:VNode,
            parentComponent:ComponentInternalInstance |  null,
      ){
      const a = "b${name}"
      const b ='bsdsd' 
}
 // 1. 双引号换成模板字符的反引号`  c s " ` (注意需要在目标行才有效)
 // 2. import add from './add'中的add添加花括号   iw 当前单词  => y s  iw { 
 // 3. 删除单引号 const b = 'bsdsds'  =>  d s '  (光标需要在目前位置)
 //  4. 第二点怎么用S实现呢？先用可视化模式圈起来v+(hl控制范围)，键入大写S ，键入' 
```


