# 🔥 2025年7月13日 - Day13 
## ✅ 已完成任务
1. rsync的免交互方法
   * 方法一：将密码写入文件中
   * 方法二：使用rsync的内置变量，定义为全局变量
2. 参数使用
   * --delete 参数进行数据同步
   * --bwlimit 带宽限速 ![示例](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250713_Day13/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-16%20161502.png)
3. 使用rsync做一个业务实操
   * ![客户端需求](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250713_Day13/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-16%20171628.png)
   * 
   * ![服务端需求](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250713_Day13/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-16%20220604.png)
   * 结果展示 ![结果](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250713_Day13/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-16%20161502.png)
## 🐞 遇到的坑
- **问题**：`sudo apt update` 报错 `Failed to fetch`
- **解决**：更换阿里云镜像源 [[操作截图]](screenshot/apt-error-fix.png)

## 📌 明日计划
1. 学习文件操作命令（cp/mv/rm）
2. 编写第一个备份脚本
