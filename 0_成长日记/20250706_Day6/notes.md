# 2025年7月8日 - Day6 
## ✅ 已完成任务
1. 了解了逻辑地址和物理地址这些基本知识还有交换机和pc端的连接关系![交换机和PC端连接图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250706_Day6/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-08%20143236.png)
2. 了解了用户端是如何通过局域网-->路由器-->运营商-->目标地址![用户到公网的路径图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250706_Day6/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-08%20153446.png)
3. 学习了如何配置路由使数据包能通过多个路由层层转换最终到达目的ip![数据包在路由间传输图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250706_Day6/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-08%210829.png)
4. 运营商之间通过接入骨干网，从而使能够实现互联
5. 使用cisco配置路由IP地址，使两台pc之间实现联通![实验结果图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250706_Day6/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-09%111513.png)

## 🐞 注意
* 交换机和交换机之间无法通信，网段不同，即使联通也无法发送数据包，会被丢弃（去往不同的地址需要走网关，也即是路由器（路由表里面有IP地址和接口的对应关系））功能叫路由转换
*  访问一些公网往往要通过多个路由如：运营商的多个点
*  使用Cisco配置路由IP地址，记得配置网关

## 📌 明日计划
* 继续学习网络管理的DNS和TCP部分
