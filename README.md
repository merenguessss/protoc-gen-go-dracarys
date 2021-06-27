# protoc-gen-go-dracarys

一个`protobuf`编译器插件，设计用于`Dracarys`框架的代码生成。

## 先决条件

1. protobuf编译器

    请自行安装`protoc`编译器。

    [安装地址](https://github.com/protocolbuffers/protobuf#protocol-compiler-installation)

2. Golang Protobuf代码生成器
    
    获取golang protobuf代码生成器：
    ```
    go get -u github.com/golang/protobuf/protoc-gen-go
    ```

## 安装

- 方式一

    ```
    go get -u github.com/merenguessss/protoc-gen-go-dracarys
    ```

- 方式二
    ```
    git clone git@github.com:merenguessss/protoc-gen-go-dracarys.git
    git install
    ```

## 快速开始

1. 编写`protobuf`文件
    
    例：

    ```protobuf
    syntax = "proto3";

    package helloworld;
    option go_package="/helloworld";

    service Greeter {
        rpc SayHello (HelloRequest) returns (HelloReply) {}
    }

    message HelloRequest {
        string msg = 1;
    }

    message HelloReply {
        string msg = 1;
    }
    ```

2. 执行命令生成 `pb.go` 文件

    ```
    protoc --go-dracarys_out=. helloworld.proto
    ```
    一个`Dracarys`框架所需的代码就生成了。😝