---
title: "Golang 기초 프로그래밍 - 안녕, 고랭[작성 중]"
date: 2020-08-29T16:28:51+09:00
categories:
- cs
- basic-programming-language
tags:
- golang
- basic
- 기초
keywords:
- tech
thumbnailImagePosition: left
thumbnailImage: //gurumee92.github.io/images/cs/basic-programming-language/logo.png
---

<!--more-->
![로고](/images/cs/basic-programming-language/logo.png)


## 프로그래밍이란 무엇인가?

## 왜 Golang?

## Golang 설치

## 안녕, 고랭

먼저 적당한 위치에, `hello.go`라는 파일을 만들고 다음을 작성한다.

hello.go
```go
package main

import "fmt"

func main() {
    fmt.Println("안녕, 고랭")
}
```

이제 `go` 도구를 이용하여 `hello.go`를 컴퓨터가, 이해하여 실행할 수 있는 바이너리 파일을 만들어보자. 터미널에 다음을 입력한다.

```bash
# hello.go 빌드
$ go build hello.go

# 빌드해서 만들어진 바이너리 파일 실행
$ ./hello
안녕, 고랭
```

위의 방법의 경우, 빌드, 실행의 과정을 하나 하나 터미널에 입력해야 한다. `go` 도구는 이 과정을 한 번에 할 수 있다. 터미널에 다음을 입력하자.

```bash
# 이전 빌드 결과물 hello 파일 삭제
$ rm hello

# hello.go 실행
$ go run hello.go
안녕, 고랭
```

이 때, 빌드 결과물은 존재하지 않는다. `go run`은 **컴파일 -> 빌드 -> 실행 파일 실행 -> 실행 파일 삭제**의 과정을 거치기 때문이다.

## 참고

* 책 "윤성우의 열혈 C 프로그래밍" - 오렌지 미디어
* 책 "Go In Action" - 제이펍