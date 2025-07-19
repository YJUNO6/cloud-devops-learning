# 🔥 2025年7月15日 - Day15 
## ✅ 已完成任务
1. 远程连接
* `ssh root@10.0.0.42` 连接命令
* `cat /etc/hosts` 查询设置的IP域名，可以使用域名连接
2. 免密钥连接
* `ssh-keygen -l -f ~/.ssh/id_rsa.pub` 生成公钥保存到~/.ssh ，可以直接`ssh-keygen`
* `ssh-copy-id -i .ssh/id_rsa.pub 172.16.1.42` 复制公钥发送到对端，可简写`ssh-copy-id 172.16.1.42`
* 远程创建文件 ![图例](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/2025715_Day15_ssh/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-19%20132918.png)
3. 通过ssh远程创建脚本执行创建nfs ![脚本代码]()
3. scp复制数据至远端


## 🐞 遇到的坑
- **问题**：`sudo apt update` 报错 `Failed to fetch`
- **解决**：更换阿里云镜像源 [[操作截图]](screenshot/apt-error-fix.png)

## 📌 明日计划
1. 学习文件操作命令（cp/mv/rm）
2. 编写第一个备份脚本

