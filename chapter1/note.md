# 服务器端
1. 创建socket
```c
#include<sys/socket.h>
int socket(int domain, int type, int protocol);
/*
接口参数：
    domain：
    type：类型
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
int accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen);
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


# 客户端
1. 创建socket
2. 连接
3. 发送消息

# Linux的文件操作
Linux会给每个文件分配一个文件描述符，如标准输入为0，标准输出为1，标准错误为2等，
常见的文件操作有打开文件、关闭文件、写入文件、读取文件等。

1. 打开文件
```c
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
int open(const char *path, int flag);
/*
接口参数：
    path：文件明的字符串地址
    flag：文件打开模式信息
返回值：
    成功返回文件描述符，失败返回-1
*/
```
其中，第二个参数flag有如下选项：

|打开模式| 含义|
|:---:|:---:|
|O_CREAT| 必要时创建文件|
|O_TRUNC|删除现有所有数据|
|O_APPEND|维持现有数据，保存到其后面，追加模式|
|O_RDONLY|只读打开|
|O_WRONLY|只写打开|
|O_RDWR|可读可写|


2. 关闭文件
```c
#include <unistd.h>
int close(int fd);
/*
接口参数：
    fd：文件描述符
返回值：
    成功返回0，失败返回-1
*/
```
3. 写入文件
```c
#include<unistd.h>
ssize_t write(int fd, const void *buf, size_t nbytes);
```
4. 读取文件