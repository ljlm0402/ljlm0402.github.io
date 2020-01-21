---
title: 새해, 새로운 페이지
date: 2020-01-01 00:00:00
comments: true
categorys:
    - begin
tags:
    - begin
photos:
    - https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/logo.png
---

2020년, 🐭하얀쥐띠 경자년, 새해가 밝았습니다. 새해 목표를 다지면서 가장 처음으로 진행하는 프로젝트는 새로운 깃허브 페이지 개선 프로젝트입니다. 개선하는 그 과정에 대해서 포스팅하겠습니다.

<!-- more -->

## 시작하기

### Hexo란 ?

[Hexo](https://hexo.io/ko/index.html)란, 빠르고 간단하고 강력한 블로그 프레임워크라고 홈페이지에 게시되어 있습니다. 

이처럼 블로그 개발에 최적화 된 프레임워크를 사용해보도록 하겠습니다.

#### 설치

``` bash
$ npm install -g hexo-cli
```

패키지 설치후에 간단한게 예제를 만들어보겠습니다.

```bash
hexo init blog
```

`themes/landscape`를 기본 테마로 생성되었습니다.

▾ 기본 폴더 구조입니다.

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/1.png)

그 후 원하는 테마를 설정해야합니다.

#### 테마 적용

[Themes | Hexo](https://hexo.io/themes/)에 접속하셔서 원하는 테마를 선택합니다.

저는 [hipaper](https://itimetraveler.github.io/hexo-theme-hipaper/) 테마를 선택하였습니다.

기존의 [melody](https://molunerfinn.com/) 테마보다 직관적이며 포스팅에 좀더 강력한 테마를 선택하였습니다.

개인적으로 추천드리는 테마는 [landspcape](https://hexojs.github.io/hexo-theme-landscape/), [icarus](https://blog.zhangruipeng.me/hexo-theme-icarus/), [PPOffice](https://blog.zhangruipeng.me/hexo-theme-hueman/) 입니다. 

많은 분들이 사용하고 있으며 포스팅 글에 최적화 되어있는 테마입니다.

그럼 해당 테마 레포지토리로 이동하여 설치해줍니다.

앞서 말한대로 원하시는 테마로 진행하시면 됩니다. 저는 hipaper 테마로 진행하겠습니다.

```bash
$ git clone https://github.com/iTimeTraveler/hexo-theme-hipaper.git themes/hipaper
```

그리고 나서 기존 `hexo init blog`로 생성한 폴더안 `themes` 폴더에 넣어줍니다.

▾ 현재 폴더 구조입니다.

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/2.png)

그 후 기본 테마였던 `landscape` 폴더를 삭제해줍니다.

최상단에 위치한 `_config.yml` 파일로 들어가서 테마 설정 코드를 작성해줍니다.

▾ 변경한 코드

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/3.png)

기존 theme: `landscape`라고 설정되었던 코드를 자신의 테마에 맞게 변경해줍니다.

```bash
$ hexo server
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

`hexo server` 명령어로 실행하고 해당 페이지주소로 접속합니다.

▾ 홈페이지 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/4.png)

이 처럼 테마가 적용된것을 확인할수 있습니다.

## 배포하기

### 레포지토리 생성

이제 [GitHub Pages](https://pages.github.com/)를 사용하여 해당 홈페이지를 호스팅 해보겠습니다.

자신의 깃허브 계정으로 접속한후 레포지토리를 생성해줍니다.

▾ 레포지토리 생성

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/5.png)

생성시 주의할점은 `자신의계정.github.io`로 생성하셔야 합니다.

해당 이미지의 에러는 이미 만들어진 에러라는 뜻으로 가볍게 무시하시면됩니다.

그 후에 아까 만들어 놓은 프로젝트를 push 해줍니다.

```bash
$ git init
$ git add .
$ git commit -m "first commit"
$ git remote add origin [방금 생성한 레포주소]
$ git push -u origin master
```

▾ 레포지토리 확인

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/6.png)

정상적으로 push가 완료되었습니다. 그 후 호스팅 브랜치를 설정해줘야합니다.

▾ 셋팅 클릭

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/7.png)

우측 상단에 `Settings`를 클릭하고 스크롤를 내립니다.

▾ Github Pages 설정

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/8.png)

`Github Pages`라는 제목의 설정란을 확인하면 `Source`가 존재합니다.

> Your GitHub Pages site is currently being built from the master branch. 

간단하게 번역해보면 "너의 Github Pages site는 현재 마스터 브랜치에 구축되어있다."

이 내용을 토대로 브랜치를 나누어서 파일을 관리하도록 하겠습니다.

우선 기본적으로 정적 호스팅을 하기위해선 `master` 브랜치에 build 된 파일들이 있어야합니다.

저희가 우선적으로 했던 hexo server로 동작은 hexo라는 프레임워크에서 제공하는 기능으로 정적 페이지가 아닙니다.

여기서 `hexo generate`를 사용해 보겠습니다.

작업중인 프로젝트로 가서 명령어를 쳐줍니다.

```bash
$ hexo generate
```

그렇게되면 `public`이라는 폴더가 생성되었습니다. 

### 배포하기

하지만 해당 public 폴더를 매번 generate 하고 별도로 배포하는 건 굉장히 번거롭습니다.

그래서 `hexo deploy` 기능을 살펴보도록 하겠습니다.

자세한 내용은 [Deployment](https://hexo.io/docs/github-pages)에서 확인해 볼 수 있습니다.

간단하게 설명드리면 설정을 통해 명렁어를 입력시 해당 경로에 자동으로 `generate` 된 파일들이 배포된다는 뜻입니다.

그럼 설정을 해보도록 하겠습니다.

```bash
$ npm install hexo-deployer-git
```

`_config.yml` 파일에서 새로운 내용을 추가해줍니다.

▾ 새롭게 추가 된 내용

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/9.png)

```bash
$ hexo clean
$ hexo deploy
```

그 후 자신의 깃허브 페이지 주소로 접속하면 정상적으로 확인하실수 있습니다.

자세한 사항은 [GitHub Pages | Hexo](https://hexo.io/docs/github-pages#Private-repository) 확인하실 수 있습니다.

### 브랜치 분리하기

위에서 언급하였듯 `master` 브랜치에는 정적 페이지 소스를 가지고 있어야 합니다.

그렇다면, 현재 hexo 생성하는 소스는 별도로 가지고 있어야하는데 

이 또한 해당 레포지토리에 브랜치를 분리하여 관리하도록 하겠습니다.

우선 제가 현재 분리한 구조입니다.

```bash
$ git branch
    master          # 정적 페이지 소스
    site-images     # 사이트 이미지 
    site-source     # hexo 소스
```

`master` 브랜치에서는 일절 작업을 하지 않고 

`site-source` 브랜치에서 `deploy`를 통해서만 배포를 할 계획입니다.

```bash
$ git checkout -b site-source
$ git add .
$ git commit -m "site-source commit"
$ git push -u origin site-source
```

이제 브랜치 분리가 되었습니다.

### 이미지 파일 관리하기

이제 마지막으로 의문점이 하나 남아있습니다.

바로 `site-images` 브랜치를 생성했는지에 대한 의문입니다.

예제 홈페이지로 이동해보겠습니다.

▾ [hipaper 샘플 페이지 - HOME](https://itimetraveler.github.io/hexo-theme-hipaper/index.html)

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/10.png)

▾ [hipaper 샘플 페이지 - CATEGORIES](https://itimetraveler.github.io/hexo-theme-hipaper/categories/)

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/11.png)

우측 `RECENT POSTS`를 보시면 엑박 표시가 나타납니다.

이것은 해당 포스팅 이미지 경로가 상대로 경로로 지정되어 `hexo generate` 경로 설정이 잘못된 경우입니다.

아까 위에 언급했든 `master` 브랜치에서는 일절 작업을 하지 않는다고 했습니다.

그래서 가장 편리하게 경로를 설정해줄수 있는 방법은 별도의 공간에 두어서 url로 요청하는 방식입니다.

그 결과 별도의 `site-images` 브랜치를 생성해서 관리하였습니다.

▾ _posts photos 작성법

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/12.png)

URL 요청으로 이미지를 가져오시면 더욱 효율적으로 포스팅을 할수있습니다.

## 최종

▾ 브랜치 별로 결과물

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/13.png)

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/14.png)

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/15.png)
