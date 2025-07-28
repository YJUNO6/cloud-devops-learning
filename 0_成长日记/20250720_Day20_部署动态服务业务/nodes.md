# 🔥 2025年7月20日 - Day20
## ✅ 已完成任务
1. LNMP架构解析![框架](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250720_Day20_%E9%83%A8%E7%BD%B2%E5%8A%A8%E6%80%81%E6%9C%8D%E5%8A%A1%E4%B8%9A%E5%8A%A1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-23%20162515.png)
2. 安装php
3. 分别联通nginx和php、nginx和MySQL的联通
4. 成功部署业务wordpress![成功部署](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250720_Day20_%E9%83%A8%E7%BD%B2%E5%8A%A8%E6%80%81%E6%9C%8D%E5%8A%A1%E4%B8%9A%E5%8A%A1/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-24%20153401.png)
5. 搭建电商平台phpshe
   
## 🐞 遇到的坑
- **问题1**：CentOS7停止维护，无法安装php7
- **解决**：利用Remi仓库安装
- **问题2**： 安装phpshe登陆时遇到验证码失败问题
- **解决**： 先查看日志，发现权限错误，然后修改对应路径的权限问题`	root@web01 she]$ll -d /var/lib/php/session
	drwxrwx--- 2 root apache 6 Jun  5  2024 /var/lib/php/session
	[root@web01 she]$chown www.www /var/lib/php/session
`

## 📌 明日计划
* LNMP架构拆分

