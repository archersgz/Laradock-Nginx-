# **Laradock + Thinkphp5.1 + Vue.js**
_________________________________________________________________
## 首先明确目标，搞这玩意儿的目的一是与主机隔离，二是为了不用mock而使用前后端分离环境 ## 
## 思路 ##
1. 首先需要一个完整的Docker LNMP环境，首选Laradock，简单粗暴安全稳定，LNMP+NODE全部配好，大是大了点，不碍事就行．
2. 把数据流的顺序捋清，主机端口<=>容器端口<=>Nginx监听，这里因为是测试环境，我们还需要用到npm，所以还要来一下反向代理
3. 最后在vue项目中vue.config.js配置接口
__________________________________________________________________
## 步骤 ##
1. 目录结构设计：/project/backend(Thinkphp5.1), /project/frontend(Vue.js)
2. 自定义思路中的接口，Laradock/docker-compose.yml搜Nginx进行端口映射
3. 将conf放Laradock/Nginx/sites
4. docker-compose down -> docker-compose build nginx
5. 建vue项目，取名frontend，将vue.config.js - devServer - port设置为反向代理的端口
6. 博客园后台关键词Laradock + vue，忘了去过一眼(这条给自己看的)
# **完事了铁子们，搂起来！**
