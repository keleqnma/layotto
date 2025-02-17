
## How to generate a Java PROTO file

### 1. 下载对应[proto](https://github.com/protocolbuffers/protobuf/releases/tag/v3.6.1) 文件到本地

my protoc version: 
```shell
$ protoc --version
libprotoc 3.17.3
```

### 2. 修改对应`proto`文件生成类名包名等信息
(需先修改文件内部service名)
appcallback.proto: 
```protobuf
option java_outer_classname = "AppCallbackProto";
option java_package = "spec.proto.runtime.v1";
```
runtime.proto
```protobuf
option java_outer_classname = "RuntimeProto";
option java_package = "spec.proto.runtime.v1";
```

### 3. 编译其对应`JAVA`文件
```shell
cd ${your PROJECT path}/spec/proto/runtime/v1
protoc -I=. --java_out=./  runtime.proto
```

PS: 建议用maven插件`protoc-gen-grpc-java`生成protobuf和grpc的java代码
