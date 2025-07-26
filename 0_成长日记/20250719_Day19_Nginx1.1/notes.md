# 🔥 2025年7月19日 - Day19
##  已完成任务
1. nginx区块关系
* ![具体关系](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20002718.png)
2. nginx中模块的常用配置
* ![具体关系](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-27%20003432.png)

## 各模块的使用
1. 指定路径方式
   * root路径指定(存储位置:/package/dlownload)
     `location /download {
root /package;
autoindex on;
}` 
   * alias指定路径(存储位置:/package)
     `location /download {
alias /package;
autoindex on;
}`
2. 用户名密码登录验证模块
   * ![使用](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20102925.png)
3. IP地址限制
   * ![具体使用](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20135252.png)
4. nginx状态模块
   * ![具体使用](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20135440.png)
5. 连接限制和请求限制
   * ![具体使用](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250719_Day19_Nginx1.1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20153647.png)
## 🐞 遇到的坑
* 第一个模块指定路径时，浏览器搜索的时候一定要在IP后面把路径加上，不然默认访问/code
* 配置密码文件时总是把auth写成auto，还不好找错
* IP限制时，先拒绝再允许，被拒绝的一样无法访问，相当于黑名单

## 📌 明日计划
* 学完nginx后就可以开始部署一些业务了
