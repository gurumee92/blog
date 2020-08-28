---
title: "Hugo + Github으로 개인 블로그 만들기"
date: 2020-08-28T18:02:37+09:00
categories:
- etc
tags:
- hugo
- github pages
- devlog
- 개인 블로그
keywords:
- tech
---


## 개요 

개인적으로, 원래 블로그 플랫폼으로 `Tistory`를 이용했었다. 언젠가 사람들이 `Github` 페이지로 개발 블로그를 만드는 것을 보고 멋있다고 생각한 것 같다. 올해 어떤 계기로 티스토리 블로그를 닫았는데, 새로운 마음으로 `Github` 페이지룰 이용하여, 개발 블로그를 만들 생각이다.

보통 `Github` 페이지로 개발 블로그를 만들 때 사용하는 것은 `Jekyll`, `Hexo`, `Hugo` 이 3가지 중 하나를 사용한다. 이들은 `Static Site Generator`로써 직역하면 정적 페이지 생성기이다. 웹 페이지는 크게 `정적 페이지`와 `동적 페이지`로 나눌 수 있다. `동적 페이지`란, 클라이언트 액션에 반응해서 웹 서버, DB 등 여러 컴포넌트들이 상호 작용하여 HTML 페이지를 동적으로 만들어주는 페이지를 말한다. 뭐 개발자라면, `Java` 진영에서는 `Spring MVC`로 만든 웹 서비스라고 생각하면 편하다. 반면, `정적 페이지`는 HTML/CSS/JS를 미리 올려서 서버가 바뀌지 않는 HTML 페이지를 보여주는 것을 말한다. 

블로그를 방문하는 유저 입장에서는 모든 컨텐츠들이 언제나 `Read Only`이다. 즉 상호 작용하는 건이 별로 없다는 뜻이다. 그래서 정적 페이지 생성기를 이용해, 개발 블로그를 만들 것이다. 그 중 `Hugo`를 사용한다. `Jekyll`이 참고할 수 있는 문서량이 제일 많지만, 페이지를 많이 올릴수록 빌드 속도가 매우 저하된다는 소문이 있다. 반면 `Hugo`는 굉장히 빠르다고 한다. 그리고 `Golang`을 이용해서 만들었다는게 참 친근하게 다가왔다. 이제 잡소리는 그만하고 바로 시작하자.


## Hugo 설치

준비물은 다음과 같다.

* Mac - Windows 사용자들은 Hugo 설치 방법을 따로 찾길 바란다. 그리고 `HomeBrew`가 설치 되어 있어야 한다. 설치가 되지 않았다면, [이 곳](https://brew.sh/index_ko)을 참조하자.
* Github ID - 회원가입이 안되어 있다면, [이 곳](https://github.com/)으로 가서 회원가입하자.
* Golang - Hugo는 Golang으로 만들어져 있다. Golang을 설치해야 한다. [이 곳](https://golang.org/)을 참고하자.

터미널에 다음을 입력한다.

```bash
# hugo 설치
$ brew install hugo
```

설치가 완료되면, 다음을 터미널에 입력해보자. 

```bash
# hugo 버전 확인
$ hugo version
# 다음이 출력되면 정상적으로 설치된 것이다.
Hugo Static Site Generator v0.74.3/extended darwin/amd64 BuildDate: unknown
```


## Github 레포지토리 2개 파기

깃헙 레포지토리를 2개 파야 한다. 둘 다 아무렇게 지어도 상관은 없지만, 잘 모르겠다면, 다음처럼 만들어두자.

* `blog`
* `<USERNAME>.github.io`

다음과 같이 말이다.

![깃 헙 레포지토리](/img/create-blog-with-hugo/01.png)


## Hugo로 프로젝트 만들기

먼저, 프로젝트를 만들어야 한다. 적당한 위치에서 다음을 입력한다.

```bash
# 현재 위치 확인
$ pwd
# 현재 경로
/Users/gurumee/Workspaces

# hugo 프로젝트 생성
$ hugo new site blog
# 생성 완료되면 출력 문구
Congratulations! Your new Hugo site is created in /Users/gurumee/Workspaces/blog.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

만들어진 프로젝트 구조는 다음과 같다.

```
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```