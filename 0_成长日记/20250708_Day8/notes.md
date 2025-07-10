# 🔥 2025年7月8日 - Day8 
## ✅ 已完成任务
1. 详细学习了浏览器输入域名连接到服务端的各种情况 ![过程图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250708_Day8/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-10%20115749.png)
2. 学习了TCP三次握手的详细过程以及各种控制字段的含义 ![过程图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250708_Day8/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-10%20161238.png)
3. TCP四次挥手的过程 ![过程图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250708_Day8/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-10%20165301.png)
4. TCP11种状态集的意义及转换 ![转换图](https://github.com/YJUNO6/cloud-devops-learning/blob/main/0_%E6%88%90%E9%95%BF%E6%97%A5%E8%AE%B0/20250708_Day8/screenshot/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-07-10%20173153.png)

## 🐞 注意
* 三次握手可以有效防止服务器资源被浪费，因为连不上的直接抛弃，只有三次连接成功的才进行传输。如果一次握手，会由于网络或其它原因造成等待，如果客户端早已经接收到数据并且关闭了，则会一直白白等待
* 浏览器连接成功后如果长时间未进行操作，底层服务器会主动断开，后面再操作需要重新进行三次握手
* TIME_WAIT的作用是防止上一个步骤出意外（网络断开）导致服务端一直处于LAST_ACK状态等待，浪费资源，从而设置以备重发ACK确认信息

## 📌 明日计划
* TCPDUMP抓包以及网络常用命令
