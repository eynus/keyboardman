## 掌握搜索
1. 全局搜索
  1. shift+command+f
  我改成了ctrl+shift+s
  2. command +方向键 从全局搜索区域切换到查询结果列表 回去？在列表第一行键入`cmd+↑`回到输入栏
  3. jkhl目录移动
  4. shift+command+j 打开`files to include`面板 (win不生效，因为之前改键ctrl+j .)
  5. command+方向键 切换`files to include``files to exclude`
  6. 右侧文件内容看完之后 返回左侧目录：(vim中的)`cmd+←` 、 `ctrl+shift+f`(全局搜索按键)
  7. 切回后再次进入会保留之前的光标浏览位置
  8. 其他快捷键不常用（自行搜索search查看）
2. 搜索一个`symbol`(workspace工作区内)(#标记)：可以是一个变量、函数  `command+t` 需要在`vim.handlekeys`设置
ctrl+p+#效果一样）

3. 搜索`symbol`(file内) `shift+cmd+o`(@标记)  键入`@:` 冒号代表排序，理解为目录大纲帮我们快速了解文件职责
4. 全局搜索`ctrl+shift+p`,可以搜索vscode自带命令和插件(e.g file utils)的命令 
5. 搜索文件`cmd+p`，排序是通过最近打开的顺序；
    不同符号切换不同的命令：
      `>`:搜索命令，
      `@`:当前文件定义，
      `#`:全局搜索。
    另一个使用场景：两个文件快速切换`ctrl+tab`快速切换到上一次打开的文件(有用)