## 页面内操作
1. 进入文本框选择模式(聚焦input) `gi`

2. 复制当前标签页(url链接) `yy`

3. 在当前标签页打开复制的地址`p`

4. 新建标签页打开赋值的地址 `P`

5. 关闭当前标签`x` | chrome自带`cmd+w`

6. 刷新  `r` |  chrome自带`cmd+r`

7. 选择文字
  1. `yv`  (对应小坐标点) 键入坐标点后即进入可视化模式，可以hjkl自由选择 例如$到行尾，0到行头
  2. `V` 基于行选择
  (以上，选中后ctrl+c即可复制内容)
  (ctrl+[或esc退出)
  (此处推荐按两次`esc`:第一次退出visual,第二次退出选中字符串)
  3. 改映射
  `github.com/gdh1995/vimium-c/wiki/Use-in-another-keyboard-layout`per-mode mapkey
  (行尾更习惯于L)
    1. 打开扩展程序找到插件vimium-c,点击选项
    2. 自定义快捷键输入
    ```json
    mapkey <L:v> <$>
    mapkey <H:v> <0>
    ```
  测试：`yv` `L` 直接选中到行尾

