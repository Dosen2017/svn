# svn创建新仓库的步骤
### golang中某些包不能下载的解决办法：http://hishenyi.com/archives/1420 <br/>
    GOPROXY=https://goproxy.io    or   export GOPROXY=https://mirrors.aliyun.com/goproxy/
### protobuf地址
    https://developers.google.com/protocol-buffers/docs/gotutorial
### 框架安装
&ensp;&ensp;&ensp;&ensp;go get -u google.golang.org/grpc <br/>
### 工具安装
&ensp;&ensp;&ensp;&ensp;https://github.com/protocolbuffers/protobuf/releases  <br/>
### 插件安装
&ensp;&ensp;&ensp;&ensp;go get -u github.com/golang/protobuf/{proto,protoc-gen-go}  <br/>
### 生成文件（不带grpc）
&ensp;&ensp;&ensp;&ensp;protoc --go_out=../services Prod.proto  <br/>
### 生成文件（带grpc）
&ensp;&ensp;&ensp;&ensp;protoc --go_out=plugins=grpc:../services Prod.proto  <br/>
### 生成文件（带gateway）
&ensp;&ensp;&ensp;&ensp;protoc --grpc-gateway_out=logtostderr=true:../services Prod.proto <br/>


