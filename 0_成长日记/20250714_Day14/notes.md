# 🔥 2025年7月14日 - Day14
## NFS网络文件系统 
* ![NFS原理](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250714_Day14/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-17%20165955.png)
### 搭建环境步骤
1. 服务安装
2. 把需要的参数以及数据存放位置写进配置文件 ![配置参数](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250714_Day14/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-17%20175310.png)
3. 按配置文件创建数据并修改属主属组
4. 启动用户
5. 到/var/lib/nfs/etab中检查服务

### 挂载两台客户端
1. 安装nfs-utils服务，但不需要启动
2. 查看服务端共享的目录 `showmount -e 服务端ip`
3. 挂载 `mount -t nfs 172.16.1.31:/data /mnt`
4. 写入开机自动挂载 `tail -l /etc/fstab`

### 实现两台客户端文件在服务端共享
1. ![结果](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250714_Day14/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-17%20214017.png)
2. ![结果](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250714_Day14/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-17%20214039.png)

### 拓展（指定匿名用户）
1. 创建匿名用户
[root@nfs ~]$groupadd -g666 www
[root@nfs ~]$useradd -u666 -g666 -s /sbin/nologin -M www
2. 修改配置文件指定匿名用户
[root@nfs ~]$cat /etc/exports
/data/ 172.16.1.0/24(rw,sync,all_squash,anonuid=666,anongid=666)
* 重启生效
[root@nfs ~]$systemctl restart nfs
3. 更改用户和用户组为配置文件中的
[root@nfs ~]$chown -R www.www /data
4. 客户端测试
无法写入，必须将/data/目录属主属组修改为www用户

## 🐞 遇到的坑
- **问题**：如何解决单点故障问题
- **解决**：
- ![理论实现图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250714_Day14/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-17%20225525.png)

## 📌 明日计划
* 回顾前面内容
* 学习ssh免密钥的具体内容
