## Fundamentals of using Protocol Buffer

The first step when working with protocol buffers is to define the structure for the data you want to serialize in a proto file:
this is an ordinary text file with a **.proto** extension.

Then, once you’ve specified your data structures, you use the protocol buffer compiler **protoc** to generate data access classes in your preferred language(s) from your proto definition

The protocol buffer compiler, **protoc**, is used to compile **.proto** files, which contain service and message definitions.

Instructions on [Protocol Buffer Compiler Installation](https://grpc.io/docs/protoc-installation/)

To run the compiler, specify the source directory (where your application's source code lives – the current directory is used if you don't provide a value),
the destination directory (where you want the generated code to go), and the path to your **.proto** file:

`protoc -I=$SRC_DIR --python_out=$DST_DIR file.proto`

This command generates **file_pb2.py** in your specified destination directory.

Because I wanted Python classes, I used the **--python_out** option (similar options are provided for other supported languages).

More information in the [official tutorial](https://developers.google.com/protocol-buffers/docs/pythontutorial).

### To run programs from this repo, use following commands:

`python3 write_to_addressbook.py my_protobuf_address_book`

`python3 read_from_addressbook.py my_protobuf_address_book`
