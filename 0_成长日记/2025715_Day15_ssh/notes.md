# 🔥 2025年7月15日 - Day15 
## ✅ 已完成任务
1. 远程连接
  * `ssh root@10.0.0.42` 连接命令
  * `cat /etc/hosts` 查询设置的IP域名，可以使用域名连接
2. 免密钥连接
  * `ssh-keygen -l -f ~/.ssh/id_rsa.pub` 生成公钥保存到~/.ssh ，可以直接`ssh-keygen`
  * `ssh-copy-id -i .ssh/id_rsa.pub 172.16.1.42` 复制公钥发送到对端，可简写`ssh-copy-id 172.16.1.42`
  * 远程创建文件 ![图例](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/2025715_Day15_ssh/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-19%20132918.png)
3. 通过ssh远程创建脚本执行创建nfs ![脚本代码](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/2025715_Day15_ssh/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-18%20215317.png)
4. 把10.0.0.31当作跳板机去远程控制其他服务器 ![模型图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/2025715_Day15_ssh/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-18%20220122.png)
  * xshell生成公钥，放到Windows连接的Linux用户中的.ssh/authorized_keys里
  * `root@nfs ~]$vim /etc/ssh/sshd_config` 修改自动密码登录
  * Ifdown eth0 #关闭外网网卡，不用xshell登录backup使用31去登录。
  * 31端建立远程免密钥连接
  * ![结果](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/2025715_Day15_ssh/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-19%20155703.png)
5. scp复制数据至远端


## 🐞 遇到的坑
* 切记权限问题

## 📌 明日计划
* 学习HTTP协议

