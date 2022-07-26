## 删除函数
1. % 匹配括号 (),[]
      1. 应用： v,% (先进入visual,匹配括号==>实现快速选中代码段)
2. vim-indent-object
      1. 对python(基于缩进而不是基于大括号的很有用)
      2. <operator>ii
            测试py文件: vii选中函数内部体
                        vai选中函数全部
                        dai删除函数
            测试js
            * 有点小的缺陷
                        vii选中函数内部体
                        vai选中函数全部，但是末尾少了一个} => 使用vaI
   

      3. <operator>ai 函数体全部
      4. <operator>aI 函数体全部(包括3实现不了的选中末尾的括号)
      （要在函数体内有效）

      #vaI 不舒服=> 改配置
      ```json
        // 删除函数
          {
            "before": [
              "a",
              "i"
            ],
            "after": [
              "a",
              "I"
            ]
          },
      ```

方式
1. dap 
  1. 基于段落 text-object（空格隔开）
  2. [缺陷]：有空格会断开
2. daI 
  1. 基于vim-indent-object
  2. 由于改了配置，dai即可
3. V$%d 
  V:基于行
  $ 来到行尾
  % 基于{}进行筛选
  d 删除
  [四次按键的优化-映射]："空格df"
  ```json
      "vim.normalModeKeyBindings": [
      // 删除函数
      {
        "before": [
          "<Leader>",
          "d",
          "f"
        ],
        "after": [
          "V",
          "$",
          "%",
          "d"
        ]
      },
      ]
  ```
  #如果函数的参数多换行了，V$%只会选到function(...){,还需键入$%(按两次)
  #之前空格df失败是因为函数{后面紧跟了注释！
  
4. 总结 在函数内部：dai 在函数名那一行：空格df
```js
function hasPrmission(roles, route) {
  if (route.meta && route.meta.roles) {

    return roles.some(role => route.meta.roles.includes(role))
  } else {
    return true
  }
}
```
```js
 getData() {
      const that = this;
      // 汇总数据（左）
      GetRealHzData({ isTemp: 1 }).then((res) => {
        that.centerTpf1 = parseFloat(res["碳排放"]).toFixed(0);
        const defaultConfig = {
          grid: {
            left: "3%",
            right: "3%",
            bottom: "3%",
          },
          series: [
            {
              name: "业务指标",
              type: "gauge",
              center: ["50%", "65%"],
              radius: "150%",
              startAngle: 190,
              endAngle: -10,
              min: 0,
              max: 100,
              // 去掉多余的分段
              splitNumber: 1,
              itemStyle: {
                color: "#00ffa2",
                // shadowColor: 'rgba(0,138,255,0.45)',
                // shadowBlur: 10,
                // shadowOffsetX: 2,
                // shadowOffsetY: 2
              },
             
              data: [
                {
                  value: (that.warn1 / that.total1).toFixed(2),
                  name: "健康率",
                },
              ],
            },
          ],
        };
        that.chartOpt3 = that.$eChartFn.testGauge(defaultConfig);
      });
```
