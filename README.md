# __玩前端需要环境，不想用mock来模拟，怎么办呢？搞个前后端分离的环境吧！__
# Laradock + Thinkphp5.1 + Vue.js
_________________________________________________________________
## 思路整理 ##
1. 首先需要一个完整的Docker LNMP环境，Docker Hub中大多数是个人发布的，维护不及时，那就找来Laradock吧，大是大了点，不过反正是我们自己玩的，又不用来生产，对吧？
2. 把数据流的顺序捋清，主机端口<=>容器端口<=>Nginx监听，这里因为是测试环境，我们需要用到npm，故还需要用Nginx对前端的环境端口进行反向代理
__________________________________________________________________
## 步骤整理 ##
1. 目录结构设计为/project/backend(Thinkphp5.1), /project/frontend(Vue.js)
2. 定义好思路中的接口，找到Laradock/docker-compose.yml中的Nginx一栏，做接口映射
3. 将两个conf文件塞到Laradock/Nginx/sites下
4. docker-compose down -> docker-compose build nginx
