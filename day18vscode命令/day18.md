## vim调用vscode命令
1. commands字段
  {
      "before": [
        "<Leader>",
        "f",//format document的简写
        "d"
      ],
      "commands": [
        //vscode命令 如何找：见①
        "editor.action.formatDocument"
      ]
    },
    {
      "before": [
        "<Leader>",
        "r",
        "n"
      ],
      "commands": [
        "editor.action.rename"
      ]
    },
    {
      "before": [
        "<Leader>",
        "["
      ],
      "commands": [//配置成对象形式，不然会报错
        {
          "command": "editor.fold",
        },
        {
          //有个问题，折叠后按下y又展开了，解决：折叠完成后，改变光标位置到尾部
          //使用：空格+【 即可收起并光标到尾部
          "command": "vim.remap",
          "args": {
            "after": [
              "$",
              "%"
            ]
          }
        }
      ]
    },
2. 功能点
  1. 格式化文档
      shift+alt+f
      <Leader>+f+d(setting设置的)
  2. 重命名
    f2
    <Leader>+r+n
  3. 折叠代码
    alt+cmd+[ / ] `[`收起,`]`展开
      <Leader>+[




①：`ctrl+shift+p` 键入`keyboard` 选择`open.. shotcut`,新页面搜索`format document`找到对应，右键copy command id,粘贴到`settings.json`的`vim.normalModeKeyBindingsNonRecursive`的commands的字符串中