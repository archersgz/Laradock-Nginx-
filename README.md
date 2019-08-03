# __玩前端需要环境，不想用mock来模拟，怎么办呢？搞个前后端分离的环境吧！__
# Laradock + Thinkphp5.1 + Vue.js
_________________________________________________________________
## 思路整理 ##
1. 首先需要一个完整的Docker LNMP环境，首选Laradock，简单粗暴安全稳定，LNMP+NODE全部配好，大是大了点，不碍事就行．
2. 把数据流的顺序捋清，主机端口<=>容器端口<=>Nginx监听，这里因为是测试环境，我们还需要用到npm，所以还要来一下反向代理
3. 最后在vue项目中配置接口
__________________________________________________________________
## 步骤整理 ##
1. 目录结构设计为/project/backend(Thinkphp5.1), /project/frontend(Vue.js)
2. 定义好思路中的接口，找到Laradock/docker-compose.yml中的Nginx一栏，做接口映射
3. 将两个conf文件塞到Laradock/Nginx/sites下
4. docker-compose down -> docker-compose build nginx
5. 建vue项目，取名frontend，将vue.config.js - devServer - port设置为反向代理的端口
# **这就完事了铁子们，搂起来！**
