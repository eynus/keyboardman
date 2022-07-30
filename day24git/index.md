### git
1. 显示source control面板 默认快捷键`control+shift+g g`  （配置）`leader + g+ g ` (normal下)
2. 查看当前状态 stage change `leader g s`  
3. 查看文件的改变diff `leader g d f`
4. `commit `  `leader g c`  
5. unstaged change `leader g u`
6. discard change `leader g cl`

## 扩展点
edamagit
   
```json
  {
      "before": [
        "<Leader>",
        "g",
        "d",
        "f"
      ],
      "commands": [
        "git.openChange"//查看文件 的改变diff `leader g d f`
      ]
    },
    {
      "before": [
        "<Leader>",
        "g",
        "g"
      ],
      "commands": [
        "workbench.view.scm"//显示source control面板
      ]
    },
    {
      "before": [
        "<Leader>",
        "g",
        "s"
      ],
      "commands": [
        "git.stage"//查看当前状态 stage change `leader g s`  
      ]
    },
    {
      "before": [
        "<Leader>",
        "g",
        "c"
      ],
      "commands": [
        "git.commit"
      ]
    },
```