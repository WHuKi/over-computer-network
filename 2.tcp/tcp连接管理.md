### tcp的连接

![img](https://mianbaoban-assets.oss-cn-shenzhen.aliyuncs.com/2021/3/uqEjMv.png)

* 第一次握手 
  * 客户端发送一个syn标志位表示请求连接，并且发送一个客户端初始序列号isn(c) ,此时客户端的状态改为 syn_sent
* 第二次握手
  * 服务端收到后会回复 syn=1，ACK=1表示已经收到，seq=y以及ack=isn(c)+1表示下次发来的内容是这个，此时服务端的状态变为syn_recvd
* 第三次握手
  * 客户端收到服务端发来的内容后会回复 ACK=1, seq =x+1表示客户端的数据 ack=y+1 表示服务端的数据



### tcp的关闭

* 第一次挥手
  * 客户端发送FIN=1报文，seq=x，客户端进入fin_wait_1状态
* 第二次挥手
  * 服务端收到后 发送ACK=1, seq=y,ack=x+1数据 服务端进入CLOSE_WAIT阶段，客户端收到后进入 fin_wait_2阶段
* 第三次挥手
  * 想客户端发送FIN=1包，seq=w,ack=x+1