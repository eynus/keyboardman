## VSpaceCode (whichkey)
功能：
键入`空格;` 弹出vspacecode窗口 开箱即用，集成了所有命令并分类
 【f:文件的命令 g:git命令 w:窗口 等等】
1. 安装 去网址下载插件：`marketplace.visualstudio.com/items?itemName=VSpaceCode.vspacecode`
2. 该配置，初始化
  1. settings`github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/settings.jsonc`
  ```json
  //键入空格;时打开vspacecode
 
    {
      "before": [
        "<Leader>",
        ";"
      ],
      "commands": [
        "vspacevode.space"
      ]
    },
  ```
  2. keybindings(settings配置只对编辑区有效，若想左边资源管理区也生效则需配置此项)
  `github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/keybindings.jsonc`
  ```json
    //资源管理区使用空格打开vspacecode
  {
    "key": "space",
    "command": "vspacecode.space",
    "when": "sideBarFocus && !inputFocus && !whichkeyActive"
  },
  {
    "key": "space",
    "command": "vspacecode.space",
    "when": "activeEditorGroupEmpty && focusedView === '' && !whichkeyActive && !inputFocus "
  },
  ```
3. 在原有的基础上做修改
  1. 修改增加
  ```json
  {
    "whichkey.bindingOverrides":[
      {
        "keys":"g.s",
        "name":"Go to line",
        "type":"command",
        "command":"workbench.action.gotoLine"
      }
    ]
  }
  ```
  2. 删除
  ```json
  {
    "whichkey.bindingOverrides":[
      {
        "keys":"g.s",
        "position":-1,
      }
    ]
  }
  ```
  3. 重写
  ```json
  {
    "whichkey.bindingOverrides":[
      {
        "keys":"g",
        "name":"Go...",
        "type":"bindings",
        "bindings":[
          {
            "key":"g",
            "name":"go to",
            "type":"command",
            "command":"workbench.action.gotoLine"
          }
        ]
      }
    ]
  }
  ```
4. 自定义自己的
扩展：
不喜欢弹窗可以自己配置vim