# sample of protocol buffers of Google

[protobuf官方文档](https://developers.google.com/protocol-buffers/docs/cpptutorial)

首先 定义 .proto 文件

# 可以使用protoc 编译.proto 生成 .pb.h .pb.cpp

```

protoc -I=$SRC_DIR --cpp_out=$DST_DIR $SRC_DIR/addressbook.proto

```

# run

 IDE环境：CLion