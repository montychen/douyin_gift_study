# 通过python获取抖音直播弹幕、点赞、礼物等信息
目录**douyin-live**是从github上的项目[dy-live-collection](https://github.com/Nothing-lin/dy-live-collection)上克隆下来的。

目录**dy-live-collection**是从github上的项目[douyin-live](https://github.com/Sjj1024/douyin-live)克隆下来的。 DJ注销掉了一些目前用不到的代码，以及额外加了一些注释


# dy-live-collection 
### 软件版本

使用 python 3.11 、  protobuf 26.1  可以正常运行

### windows 安装 protobuf 编译器
    
从 [Protobuf GitHub](https://github.com/protocolbuffers/protobuf) 仓库的下载适用于 Windows 的预编译二进制文件。选择适合你的系统的版本，例如 protobuf-cpp-{version}-win64.zip

### macOS 安装 protobuf 编译器
```bash
brew install protobuf
```
### 安装python protobuf 包
```
pip install protobuf
```

`dy-live-collection/protobuf/dy.proto`文件是使用protobuf定义的douyin消息

### 用`protoc`编译`dy.proto` 生成 `dy_pb2.py`文件
```bash
cd dy-live-collection   # 先进入 dy-live-collection 目录
protoc --python_out=.  protobuf/dy.proto 
```

### 运行
```bash
pip install -r requirements.txt
python main.py
```


### 打包
```bash
## MacOS
pyinstaller main.py --add-data "static/*:static/" # 打包成文件夹

## Windows
pyinstaller main.py --add-data "static/*;static/" # 打包成文件夹
```