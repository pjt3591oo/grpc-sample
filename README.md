# Install GRPC(Package)

```bash
go get google.golang.org/grpc
```

# sample 코드 실행

해당 샘플코드를 실행하기 위해서는 다운받은 후 **`$GOPATH/src`** 디렉터리에 넣어준 후 아래 명령어를 실행

```bash
$ git clone https://github.com/pjt3591oo/grpc-sample.git
$ mv grpc-sample $GOPATH/src
$ cd $GOPATH/src/grpc-sample/grpc
```

* GRPC server 실행

```bash
$ go run server.go
```

* GRPC client 실행

```bash
$ go run client.go
```

# Install protoc-gen-go(Binary)

```bash
$ go get -u -v github.com/golang/protobuf/protoc-gen-go

$ export PATH=$PATH:$GOPATH/bin
```

# Create Interface 

```bash
$ /Users/bagjeongtae/Desktop/protoc-3.6.1-osx-x86_64/bin/protoc -I $GOPATH/src/sample/grpc --go_out=plugins=grpc:$GOPATH/src/sample/grpc $GOPATH/src/sample/grpc/helloworld/helloworld.proto
```

> 참고: protoc-gen-go가 정상적으로 설치되야 **`helloworld.proto`** 파일을 이용하여 인터페이스 파일생성이 정상적으로 가능. 또한, 앞에서 **`$GOPATH/bin`** 을 PATH에 추가하는 이유는 어느 경로에서나 protoc-gen-go을 사용하기 위함임. **`$GOPATH/bin`** 에는 go 기반의 바이너리 파일이 있음.

protobuf를 통해 데이터를 주고받는 인터페이스 정의