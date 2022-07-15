ssss## 插件vim-easymotion
1. vim-easymotion（默认集成到vscode=vim,只要配置开启使用就可）

  "vim.easymotion": true,

2. leader代表反斜杠           改键：<Space>      "vim.leader": "<Space>",               

3. 因为改建，下面的<leader>替代为[空格] 
[上面这几个就够用了！][w e b ge j k]
[光标向下]
单词首部：<leader><leader> w          跳转点(罗列出跳转点，此时只需键入你的目标点实现跳转) 
单词尾部：<leader><leader> e
行首部：<leader><leader> j

[向上↑]：
单词首部：<leader><leader> b
单词尾部：<leader><leader> ge
行首部：<leader><leader> k
比较多：匹配单词开始和结尾，#后，...<leader><leader> h

[上下都有]
<leader><leader><leader>j
```js
      function patchElement =(
            n1:VNode,
            n2:VNode,
            parentComponent:ComponentInternalInstance |  null,
      )
```

## 插件vim-sneak（相比全局搜索节约一次按钮enter)
基于两个字符
v/nomral + f + 2char
operation + z  + 2char

 向下搜索：按键s+[目标字母]   如：scom ;(继续搜索) ,(上一个搜索)
 向上搜索：按键S 

本来s按键平常常用，sneak把s替换了怎么办呢？
1. sneak是全局的，包含了行内搜索f
2. 与原生的f搜索功能类似，所以可以用sneak代替f功能（行内搜索）
3. 改建： 
      1. 把s(sneak)的功能=> f
      2. 重置s原生的功能

```json
 "vim.easymotion": true,
  "vim.leader": "<Space>",
  "vim.sneak": true,
  // 解决sneak递归 非递归配置
  "vim.normalModeKeyBindingsNonRecursive": [
    {
      "before": [
        "f"
      ],
      "after": [
        "s" //sneak
      ]
    },
    
      "before": [
        "F"
      ],
      "after": [
        "S"
      ]
    },
    {
      "before": [
        "s" //删除当前字符并进入insert 和cl组合键一样，所以s替换成cl
      ],
      "after": [
        "c",
        "l"
      ]
    },
    {
      "before": [
        "S"
      ],
      "after": [
        "^",
        "C"
      ]
    },
    // {
    //   "before": [
    //     ""
    //   ],
    //   "commands": []
    // },
  ],
  // 可视化模式也要统一，f和s统一
  "vim.visualModeKeyBindingsNonRecursive": [
    {
      "before": [
        "f"
      ],
      "after": [
        "s"
      ]
    },
  ],
  //此模式下用z，为了统一，用f
  "vim.operatorPendingModeKeyBindingsNonRecursive": [
    {
      "before": [
        "f"
      ],
      "after": [
        "z"
      ]
    },
    {
      "before": [
        "F"
      ],
      "after": [
        "Z"
      ]
    },
  ],

```
dfne
dFne



