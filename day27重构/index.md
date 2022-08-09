## 重构及插件
1. vscode自己的：cmd+.
2. Abracadabra,, 妈咪妈咪哄
  rename symbol
  extract variable提取变量
  inline variable
  替换字符串为模板字符串
3. hocusPocus
  创建函数 `Leader + f`
  创建变量 `Leader + v`
```json
 {
      "before": [
        "<Leader>",
        "f",
        "f",
      ],
      "commands": [
        "hocusPocus.createFunction"
      ]
    },
    {
      "before": [
        "<Leader>",
        "v",
        "v",
      ],
      "commands": [
        "hocusPocus.createVariable"
      ]
    },
```
4. javascript booster 
  1. extend selection扩大选区（vim里面有af af也可以)
  2. shrink selection