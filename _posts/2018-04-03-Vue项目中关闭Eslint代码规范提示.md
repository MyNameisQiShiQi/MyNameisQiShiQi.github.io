## Vue关闭Eslint代码规范提示

今天使用vue-cli新建一个vue项目时，开启了Eslint来检测代码规范性，但是Eslint和webstorm自带的规范化格式有所冲突，mac下的webstorm快捷键option+command+L规范出来的代码格式在eslint检测下报错。

## 解决方案

![alt 解决方案](https://raw.githubusercontent.com/MyNameisQiShiQi/storeImg/master/2018-04-03-pic-1.jpg )


## 如何解决打包过程中的报错

1. 将config文件夹下index.js文件中 useEslint设为false。
2. build下webpack.dev.conf.js中的createLintingRule去掉相关操作就行。
3. 最简单的是在使用vue-cli生成项目时就禁用eslint。


## 以上记录