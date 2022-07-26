## 掌握窗口的管理（vim)
1. 新建窗口
  1. 左右 [Ctrl+w] + v
  2. 上下 [Ctrl+w] + s
2. 窗口切换
  1. Ctrl+w + hjkl
  3. Ctrl+w + w(适用于左右两个窗口互换，多了用1.方便)
3. 关闭窗口
  1. Ctrl+w + c (关闭窗口内的一个文件)(等同于vscode的command+w *推荐)
  2. 利用vscode快捷键 Command+k+w关闭整个窗口及其文件（扩展内的3.2）
4. 只保留当前窗口，关闭其他
  1. Ctrl+w + o

## 扩展(这一套是基于vscode快捷键搭建的)
1. 利用vscode的自定义快捷键
2. 新建窗口
  1. Command + \
  2. Command + ctrl + \
  (以上是:左右切分)
  (上下切分：)
  命令栏 ctrl+shift+p, 键入split editor up,点击设置icon，设置快捷键。(视频设置的ctrl+cmd+\,我设置的ctrl+alt+\ )
  1. 设置快捷键
3. 关闭窗口
  1. Command + w   【*推荐】
  2. Command +  k + w
4. 窗口切换
  1. shift+方向键
```json
// keybindings.json
  {
    "key": "ctrl+alt+oem_5",
    "command": "workbench.action.splitEditorUp"
  },
  {
    "key": "shift+left",//前提是用软件把ctrl+hjkl改成方向键
    "command": "vim.remap",
    //为了不影响insert模式下shift+方向键的选中效果
    "when": "vim.mode == 'Normal'",
    "args":{
        "after": ["<c-w>", "h"]
    }
},
{
    "key": "shift+right",
    "command": "vim.remap",
    "when": "vim.mode == 'Normal'",
    "args":{
        "after": ["<c-w>", "l"]
    }
},
{
    "key": "shift+up",
    "command": "vim.remap",
    "when": "vim.mode == 'Normal'",
    "args":{
        "after": ["<c-w>", "k"]
    }
},
{
    "key": "shift+down",
    "command": "vim.remap",
    "when": "vim.mode == 'Normal'",
    "args":{
        "after": ["<c-w>", "j"]
    }
}
  ```

  2. 没改键的话用shift+ctrl+hjkl
## 梳理
            vscode              vim
1. 左右切分 comman+\          ctrl+w+v
2. 上下切分 ctrl+alt+\ (自己命令栏设置的)          ctrl+w+v
3. 关闭窗口 command+w command+w+k (windows好像无效哇！c)              command+w+c
4. 窗口切换 shift+方向键(自命令栏搜索keyboard.json打开openkeyboardshotcuts设置的)，没改建就用shift+control+jkhl
