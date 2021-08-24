# TCP-IP-Network-Programing
TCP/IP网络编程 [韩]尹圣雨 全书的代码

# 服务器端
1. 创建socket
```c
#include<sys/socket.h>
int socket(int domain, int type, int protocol);
/*
接口参数：
    domain：
    type：
    protcol：
返回值：
    成功时返回文件描述符，失败时返回-1
*/
```

2. 绑定IP和端口

```c
#include<sys/socket.h>
int bind(int sockfd, struct sockaddr *myaddr, socklen_t addrlen);
/*
接口参数：
    sockfd：文件描述符
    myaddr：本机地址
    addrlen：
返回值：
    成功时返回0，失败时返回-1
*/
```

3. 监听

```c
#include<sys/socket.h>
int listen(int sockfd, int backlog);
/*
接口参数：
    sockfd：文件描述符
    backlog：
返回值：
    成功时返回0，失败时返回-1
*/
```

4. 接收请求

```c
#include<sys/socket.h>
int accept(int sockfd, struct sockaddr *addr, socklen_t addrlen);
/*
接口参数：
    sockfd：文件描述符
    addr：发送方的地址
    addrlen：
返回值：
    成功时返回文件描述符，失败时返回-1
*/
```

5. 发送消息

一个服务端的示例：
```c

```

# 客户端
1. 创建socket
2. 连接
3. 发送消息
