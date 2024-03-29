# multi-threaded-web-server
一个简单的多线程web服务器，使用“生产者-消费者模型”。首先会创建若干个消费者线程，之后生产者线程负责接收网络http请求，将文件描述符放在一个固定大小的缓冲区中，消费者线程则不断地从缓冲区中读出文件描述符，并处理对应的http请求。

## 使用

```shell
> make
> ./wserver -d files -p 8080
```

可以在命令行中设定服务器的根目录和端口，也可以在`config.h`中进行更多配置，包括消费者线程数量、buffer大小、IP等。

## 效果

![pic](files/pic.png)

## 并发测试

使用Apache的`ab`工具进行并发测试：

![bingfa](files/bingfa.png)