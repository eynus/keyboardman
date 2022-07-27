## vscode快捷键——操作文件
1. 切到`files explorer`区域 
    1. vim--- shift+ctrl+h(局限：必须vim命令生效区，打开终端载终端就切不过去)
               shift+方向键
              
    2. vscode --- ctrl+;
     [配置切换到资源管理器的全局命令]————
                  ctrl+shift+p:key..shotcut、键入`shift explorer`,发现`shift+cmd+e`发现也可以切，但是难记————换个快捷键 ，copy 到keybings.json并修改key为`ctrl+;`
2. 切到`editor`区域
  1. vim --- shift+方向键(同理：终端就不生效了)
  2. vscode --- `cmd+e`   配置成  `ctrl+'`
    键入`command 1`(windows是`ctrl 1`),右键copy 
```json
  // 切换到侧边资源管理器，并修改key
  {
    // "key": "ctrl+shift+e",
    "key": "ctrl+;",
    "command": "workbench.view.explorer",
    "when": "viewContainer.workbench.view.explorer.enabled"
  },
  {
    "key": "ctrl+'",
    "command": "workbench.action.focusFirstEditorGroup",
  }
```
3. 移动光标 jk操作上下
4. 折叠展开 h就行（h代表左边，此处表示上一级，快速多次按h
5. 创建文件
    1. *在`files explorer`: `a` (前提光标在资源管理目录)
        [配置]:
        [资源目录处新增文件]：keyboard里面搜newFile/找到file:new file，copy
    2. *在editor: vim———————— `leader+n+f`
      editor内部使用vim命令实现在[当前文件目录新建文件]：settings配置
        操作： `空格+n+f`
          ```json
          "vim.normalModeKeyBindingsNonRecursive": [
            {
              "before": [
                "<Leader>",
                "n",
                "d",
              ],
              "commands": [
                "explorer.newFolder"
              ]
            },
            {
              "before": [
                "<Leader>",
                "n",
                "f",
              ],
              "commands": [
                "explorer.newFile"
              ]
            },]
          ```
    3. vscode:  `cmd+n` 需要自己保存（我无效?)
    4. 使用插件file utils(要自己安装) ctrl+shift+p_搜索utils 可以创建文件
6. 创建文件夹
    1. *在`files explorer`: `A` (前提光标在资源管理目录)
7. 重命名
8. 删除
<!-- keybindings.json -->
```json
 // 切换到侧边资源管理器，并修改key
  {
    // "key": "ctrl+shift+e",
    "key": "ctrl+;",
    "command": "workbench.view.explorer",
    "when": "viewContainer.workbench.view.explorer.enabled"
  },
  {
    "key": "ctrl+'",
    "command": "workbench.action.focusFirstEditorGroup",
  },
  // 创建文件
  {
    "key": "a",
    "command": "explorer.newFile",
    // 在资源管理处且不是input命名状态
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "shift+a",
    "command": "explorer.newFolder",
    "when": "filesExplorerFocus && !inputFocus"
  },
  // 重命名
  {
    "key": "f2",
    "command": "renameFile",
    "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
  } // 切换到侧边资源管理器，并修改key
  {
    // "key": "ctrl+shift+e",
    "key": "ctrl+;",
    "command": "workbench.view.explorer",
    "when": "viewContainer.workbench.view.explorer.enabled"
  },
  {
    "key": "ctrl+'",
    "command": "workbench.action.focusFirstEditorGroup",
  },
  // 创建文件
  {
    "key": "a",
    "command": "explorer.newFile",
    // 在资源管理处且不是input命名状态
    "when": "filesExplorerFocus && !inputFocus"
  },
  {
    "key": "shift+a",
    "command": "explorer.newFolder",
    "when": "filesExplorerFocus && !inputFocus"
  },
  // 重命名
  {
    "key": "r",
    "command": "renameFile",
    "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
  },
  // 删除
  {
    "key": "d",
    "command": "deleteFile",
    "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceReadonly && !inputFocus"
  }
```