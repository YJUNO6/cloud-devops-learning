#  2025年7月18日 - Day18
## 分析nginx的优势
1. 选择nginx的原因![问题分析](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250718_Day_18_Nginx/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-20%20213048.png)
2. nginx和apache的对比![对比分析](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250718_Day_18_Nginx/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-20%20215139.png)
3. nginx应用场景![应用场景](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250718_Day_18_Nginx/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-20%20215906.png)

## 部署nginx
### 安装配置步骤：
1. 配置nginx仓库(配置后yum会自动先找自己的仓库)
	* root@web01 ~]$cat /etc/yum.repos.d//nginx.repo
	* [nginx-stable]
	* name=nginx stable repo
	* baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
	* gpgcheck=1
	* enabled=1
	* gpgkey=https://nginx.org/keys/nginx_signing.key
  * 仓库地址需要到官网找
2. 安装nginx服务
	* [root@web01 ~]$yum -y install nginx
3. 配置服务
	* nginx的主配置文件：/etc/nginx/nginx.conf
	* [root@web01 ~]$cd /etc/nginx
	* [root@web01 nginx]$ll /etc/nginx/nginx.conf
	* rw-r--r-- 1 root root 648 May 30  2024 /etc/nginx/nginx.conf
	* [root@web01 nginx]$cat /etc/nginx/nginx.conf
	* (查看配置文件，就三个分别是核心模块事件模块（和用户连接的各种事件）和http模块，简单易读且版本是1.26.1)   
4. 启动并加入开机自动运行
	* [root@web01 nginx]$systemctl start nginx
	* [root@web01 nginx]$systemctl enable nginx
5. 检查端口是否开启
	* [root@web01 nginx]$netstat -tnulp
	* Active Internet connections (only servers)
	* Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
	* tcp        0      0 0.0.0.0:111             0.0.0.0:*               LISTEN      926/rpcbind         
	* tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      1750/nginx: master 
	* Ps axu|grep nginx #查看子进程
6. 修改default.conf文件并按修改路径创建相应的目录和添加内容
	* root@web01 conf.d]$cat default.conf
	* server{
	* 	listen 80;
	* 	server_name www.yuno.com;
	
	* 	location  /{
	* 		root /code/;
	* 		index index.html index.htm;
	* 	}
	* }
	* [root@web01 conf.d]$mkdir /code
	* [root@web01 conf.d]$echo yyj > /code/index.html

### 配置多个业务
1. 使用多个IP地址配置多业务
	* [root@web01 conf.d]$ip add add 10.0.0.8/24 dev eth0 ##在网卡0配置多个IP##
	* [root@web01 conf.d]$ip add ##查看添加的网卡##
* 配置两个.conf文件存放服务数据(nginx.conf里面配置会找到下面文件执行)
	* [root@web01 conf.d]$cat png1.conf
	* server {
	* listen 10.0.0.8:80;
	* server_name _;
	* location / {
	* root /data;
	* index index.html index.htm;
	* }
	* }
	* [root@web01 conf.d]$cat png.conf
	* server {
	* listen 10.0.0.7:80;
	* server_name _;
	* location / {
	* root /code/;
	* index index.html index.htm;
	* }
	* }
2. 基于端口的方法配置多业务
   把png.confIP端口配置更换端口listen 81;，然后去浏览器访问10.0.0.7:80,10.0.0.7:81或者是10.0.0.8的不同端口也可以
3. 使用多个域名配置多个业务
   server_name www.yuno.com  记得要到主机下的hosts文件添加IP域名才能正常访问，不然访问的是别人的域名

## 🐞 注意
* 如果配置了官网仓库，但yum还是去epel安装软件，则yum clean all清除一下缓存或者到/etc/yum.repos.d/epel.repo下面关闭epel,enabled=0
* 上传文件时浏览器访问10.0.0.8只能查看到html下的这是因为默认到10.0.0.8/index.html查看，需要加上文件名字到ip下才能查看（除非index.html被上传文件覆盖）



## 📌 明日计划
* 继续学习nginx区块关系和各模块的使用
