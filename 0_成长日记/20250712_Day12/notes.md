# 🔥 2025年7月12日 - Day12 
## ✅ 已完成任务
### rsync应用场景
1. 推送式（上传）
2. 拉模式（下载）
3. 多server备份 ![模式图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20152556.png)
4. 异地备份 ![模式图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20153350.png)

### rsync应用
1. 本地模式(了解)
* local：rsync [OPTION..] SRC… [DEST]
* ![示例](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20155906.png)
* 注意：拷贝目录时和cp不一样，cp是 源目录/ 拷贝整个目录 /*是拷贝目录下的文件，rsync则是直接 源目录 就是拷贝整个目录，源目录/ 是拷贝目录下的文件
  
2. 远程模式(熟练)
* 拉取
* ![命令](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20161902.png)
* 推送
* ![命令](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20174352.png)
* 注意：可以不加root，会默认与当前登录的用户相同用户名的对端用户；也可以使用域名传送。
  
3. 守护进程模式
   3.1 安装服务
   3.2 配置服务
   3.3 根据配置文件创建必要数据
   * 创建rsync虚拟用户
   * 创建密码文件
   * 修改密码权限为600
   * 创建backup目录
   * 修改目录权限为rsync用户
   3.4 启动服务并设置开机自启
   3.5 客户端测试推送至服务器
   * ![命令](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20222956.png)
   * ![命令](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250712_Day12/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-15%20234309.png)

## 📌 明日计划
* 进一步丰富和巩固对rsync的学习
