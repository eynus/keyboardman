## snippets
1. 插件
  1. JavaScript（es6） code snippets
  2. vue3 snippets
  3. vue vscode snippets
2. 常用
  1. imp `import fs from 'fs'`
  2. imd `import {rename} from 'fs'` 
  3. fn 
  4. log
  5. vue
  6. anfn
  7. iife
  8. rp
3. 技巧
  1. tab键可以切换位置
  2. 如果不小心提示消失的时候用 `cmd+i` `ctrl+space`(和输入法冲突)
4. 自己实现一个snippets `csp`>`user snippets`
  1. 文档
    1. `https://code.visualstudio.com/docs/editor/userdefinedsnippets`
    2. `https://snippets-generator.app/`
  2. 知识点
    1. tab位置 $1,$2...
    2. 默认值
    3. 多选
    4. 变量 `TM_FILENAME`
  3. 比如anfn 我想要一个没有括号的
  ```json
  	"function without huohao": {
		"prefix": "anfn2",
		"body": [
			"($1) => ${2:$1}", //$2默认值是$1
		],
		"description": "Log all type"
	}
  ``` 