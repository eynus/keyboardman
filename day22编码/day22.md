## 编码
1. 【智能提示类】
1. show code actions(小灯泡提示框) `command+.` 在弹框里集成显示可用的插件 (检测拼写错误、重构等等)
2. trigger parameter hints `shift+command+space`
  1. 用途：显示参数提示。见test.js 使用键入`getName()`键入`()`时会有提示`getName(name:any,age:any):void`,取消后再次显示
2. trigger suggestion `command+i`
  1. 用途：触发建议。见test.js 键入`co`,会有建议弹框，esc后取消弹框后键入`command+i`再次显示 (测试发现我的不显示)

 【功能场景】（原来就在用的）
2. 移动行`opt+up/down`   opt在win下是alt
2. 增加行 `command+enter`
2. 删除前面的单词 (需在keybinds配置 deleteWordPartLeft,deleteWWordPartRight)
  `opt+delete`基于驼峰命名删除  `opt+ctrl+delete`基于单个单词删除
  ```json
   {
    "key": "ctrl+delete",
    "command": "deleteWordLeft",
    "when": "textInputFocus && !editorReadonly"
  },
  {
    "key": "ctrl+end",
    "command": "deleteWordRight",
    "when": "textInputFocus && !editorReadonly"
  },
  {
    "key": "ctrl+shift+delete",
    "command": "deleteWordPartLeft"
  },
  {
    "key": "ctrl+shift+end",
    "command": "deleteWordPartRight"
  } {
  "key": "ctrl+delete",
  "command": "deleteWordLeft",
  "when": "textInputFocus && !editorReadonly"
  }
  ```
2. 跳转到错误处 `f8` 基于workspace
  上一个错误的跳转`shift+f8`
2. 选择所有出现的当前单词 `command+f2` 
    选择所有的目标单词。`gb`略麻烦，这个按一次就全部选择
