# 🔥 2025年7月22日 - Day22
## ✅ 已完成任务
1. 业务需求以及可行性分析![架构图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250721_Day21_LNMP%E6%9E%B6%E6%9E%84%E6%8B%86%E5%88%86/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-24%20221946.png)
2. 完成数据库迁移后测试远程连接数据库![图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250721_Day21_LNMP%E6%9E%B6%E6%9E%84%E6%8B%86%E5%88%86/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-25%20111445.png)
3. 增加一台web02服务器
4. 准备一台NFS服务器
5. 测试数据库是否同步共享到NFS![架构图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250721_Day21_LNMP%E6%9E%B6%E6%9E%84%E6%8B%86%E5%88%86/sreenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-25%20221212.png)
## 🐞 遇到的坑
- **问题1**：浏览器控制台提示：WordPress Gutenberg 编辑器的「画廊区块（core/gallery）」结构与系统预期不一致，导致图片上传或编辑失败。是 WordPress 前端渲染层的问题，和 Linux/Nginx 服务端配置（如权限、PHP 环境）是不同维度的故障，但两者可能因 “文件配置或者是路径不一致导致区块数据损坏” 或 “主题 / 插件依赖服务端环境” 间接关联。
- **解决**：经过测试和排错，才发现了web01和web02的php版本下载不一致，导致cp同样的code代码无法使wordpress正常上传图片，只好重装web02，让两台服务器实现真正意义的完全一致。
- **问题2**：wordpress网页无法写入问题
- **解决**：时间路径没有，在上传文件时会自动创建，原文件在拷贝过来的时候权限会是root，导致无法往里面写，需要修改权限

## 📌 明日计划
* nginx方向代理


