## 删除函数
1. % 匹配括号 (),[]
      1. 应用： v,% (先进入visual,匹配括号==>实现快速选中代码段)
2. vim-indent-object
      1. 对python(基于缩进而不是基于大括号的很有用)
      2. <operator>ii
            测试py文件: vii选中函数内部体
                        vai选中函数全部
                        dai删除函数
            测试js
            * 有点小的缺陷
                        vii选中函数内部体
                        vai选中函数全部，但是末尾少了一个} => 使用vaI
      2. <operator>ai 
      2. <operator>aI
      3. 

方式
1. dap
2. dal
3. V$%d 
      1. 

```js
function hasPermission(roles, route) {//按%
  if (route.meta && route.meta.roles) {
    return roles.some(role => route.meta.roles.includes(role))
  } else {
    return true
  }
}
```
