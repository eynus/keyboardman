# 替换命令 :substitute
1. 公式([]代表可写) :[range]s[ubstitute] / [pattern] / [string] / [flags]
   e.g   :s /目前字符串 /替换字符串 回车
   tips: 如果不回车，回到normal模式会返回未替换状态

2. rang 范围 
      ①$ 到尾部（从指定行到全文尾部）
            : 10,$ s/xxx/xxx2回车
      ②% 全文(最常见*)           (只会匹配行内第一个！)        
            : % s /xxxx /xxx2 回车
      ③number,number(基于line行)
            替换line10-12里面的xxx字符 : 10,12 s/xxx/xxx2回车
3. pattern
            把全局的h1,h2都替换 
                  : %(全局) s/h\dg/xxx2 回车  
                  : %(全局) s/h[1,2]g/xxx2 回车  [1,2]代表可选的1,2(正则)
3. flag（可多个）
      g  全局
            :%s/xxx1/xxx2/g  (行内第一个之后的也会被匹配！)

      c
            弹对话框，是否替换
            y:替换当前高亮但不退出，可多次按y一个个替换  n:不替换 a:全部替换 q:直接退出 l:当前替换第一个并退出
             :%s/xxx1/xxx2/gc
4. 可视化模式下 ————全部替换（就不需要指定范围）
      v模式下按: 底栏会出现符号 :'<,'>
      '<指回到v模式下选中区域开头
      '>指回到v模式下选中区域结尾
      以上即可确定范围，配合v模式 $,number,number就不常用了,且v模式高亮符合日常习惯
      使用：  v(可视化模式) 选中区域 :s/xxx1/xxx2

      如何看文档：键入vim进入模式，键入:help s_flags回车 (终端和vscode操作可能不同)

5. 多选操作 gb(找到附件的该单词，多光标操作) —————— add another word on the next word it finds which is the same as the word under the word
      1. 操作： 光标放目前位置 gb(选中当前) gb(选中下一个) 键入目标操作符例如c 实现删除修改
      2. 区分大小写

## 练习
aaaaaadaslkdjlas
ss

sdada sssp
adsadass sss saadsadasda999 999
