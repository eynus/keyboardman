## 删除函数
1. % 匹配括号 (),[]
      1. 应用： v,% (先进入visual,匹配括号==>实现快速选中代码段)
2. vim-indent-object
      1. 对python(基于缩进而不是基于大括号的很有用)
      2. <operator>ii 函数体内部
      3. <operator>ai 函数体全部
      4. <operator>aI 函数体全部(包括3实现不了的选中末尾的括号)
      （要在函数体内有效）

      #vaI 不舒服=> 改配置
      ```json
        // 删除函数
          {
            "before": [
              "a",
              "i"
            ],
            "after": [
              "a",
              "I"
            ]
          },
      ```

方式
1. dap 基于段落 text-object（空格隔开）
2. daI 由于改了配置，dai即可
3. V$%d 
  V:基于行
  $ 来到行尾
  % 基于{}进行筛选
  d 删除
  [四次按键的优化-映射]："空格df"
  ```json
      "vim.normalModeKeyBindings": [
      // 删除函数
      {
        "before": [
          "<Leader>",
          "d",
          "f"
        ],
        "after": [
          "V",
          "$",
          "%",
          "d"
        ]
      },
      ]
  ```
  #如果函数的参数多换行了，V$%只会选到function(...){,还需键入$%(按两次)
  #之前空格df失败是因为函数{后面紧跟了注释！

```js
function hasPrmission(roles, route) {
  if (route.meta && route.meta.roles) {

    return roles.some(role => route.meta.roles.includes(role))
  } else {
    return true
  }
}
```
