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

2020년, 🐭하얀쥐띠 경자년, 새해가 밝았습니다. 새해 목표를 다지면서 가장 처음으로 진행하는 프로젝트는 새로운 깃허브 페이지 개선 프로젝트입니다. 개선하는 그 과정에 대해서 포스팅 하겠습니다.

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

▾ photos 작성법

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/12.png)

URL 요청으로 이미지를 가져오시면 더욱 효율적으로 포스팅을 할수있습니다.

## 추가하기

이제 기본적인 환경 셋팅은 완료하였습니다.

좀더 나만의 홈페이지로 개선하기 위해서 몇가지 기능을 추가해보도록 하겠습니다.

### Disqus 추가

[DISQUS](https://disqus.com/)란, 손쉽게 댓글을 관리해주는 서비스입니다.

해당 링크를 클릭하여 접속 후, `GET STARTED`를 클릭해줍니다.

▾ Disqus 홈페이지

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/16.png)

클릭 시, 회원가입과 로그인 화면이 나타나는데

저는 Google 소셜 로그인으로 접속하였습니다.

로그인이 완료되었으면 이제 두가지 선택 버튼이 나타납니다.

`I want to comment on sites`, `I want to install Disqus on my site` 라는 문구 버튼 중에서

`I want to install Disqus on my site`를 클릭해줍니다.

▾ 선택 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/17.png)

Create a new site 페이지에서 `Website Name`에 자신의 github page 주소를 기입해줍니다.

그후 아래 선택은 원하시는걸로 선택하시고 `Create Site` 버튼을 클릭합니다.

▾ Create a new site 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/18.png)

그 다음 원하시는 서비스를 선택하는 화면이 나타납니다.

스크롤을 내리다 보면 `Basic` 박스가 보입니다. 

기본 서비스를 선택하여 줍니다.

▾ Basic 선택 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/19.png)

이제 여러가지 버튼이 보입니다.

다양한 템플릿에 지원하는 페이지로 보이며 우리는 맨 하단으로 이동하여

`I don't see my platform listed, install manually with Universal Code` 버튼을 클릭하여줍니다.

▾ Install 선택 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/20.png)

그 후에는 자바스크립트로 만들어진 코드를 자신의 홈페이지에 붙이라는 페이지가 나타납니다.

저희가 필요한 정보는 `Shortname` 이라는 정보만 필요합니다.

과감하게 좌측 상단 홈페이지 주소를 클릭하고 `Edit` 버튼을 클릭하여 줍니다.

▾ Edit 선택 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/21.png)

좌측 SITE 카테고리에서 `General` 클릭하면 `Shortname`라는 정보가 있습니다.

자신의 Shortname 복사하고 홈페이지 소스로 돌아갑니다.

▾ General 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/22.png)

자신의 테마 폴더 안에 `_config.yml`에서 disqus_shortname에 아까 복사했던 Shortname을 붙여넣기합니다.

▾ Shortname 설정

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/23.png)

이제 마지막으로 자신이 원하는 포스팅에 Disqus를 활성화 시키기고 싶을 경우 포스팅 정보란을 수정합니다.

comments라는 정보를 true로 설정합니다.

▾ post 정보

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/24.png)

그리고 마지막으로 홈페이지를 실행시켜 확인해봅니다.

```bash
$ hexo server

INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

▾ 결과 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/25.png)

### Google AdSense 추가

[Google AdSendse](https://www.google.com/adsense)란, 트래픽 수익을 얻을 수 있는 광고 마케팅 중 하나로 `구글(google)`에서 시작되었습니다.

즉, 자신의 페이지에 광고를 삽입하여 해당 사이트로 접속시 광고 트래픽에 따른 수익을 얻을수 있는 서비스입니다.

해당 링크를 통해 접속 후 자신의 구글 계정을 로그인 해줍니다.

웹 사이트, 이메일 주소를 기입 후 `저장하고 계속하기` 버튼을 클릭합니다.

▾ Google AdSense | 가입 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/26.png)

그리고 home 화면이 나타납니다.

home 화면에서 알려주는 순서대로 코드를 복사해줍니다.

▾ Google AdSense | 가입 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/27.png)

이제 복사한 코드를 자신의 홈페이지에 삽입하겠습니다.

자신의 테마 폴더안에 `_config.yml`에서 새로운 정보를 셋팅해줍니다.

에드센스 코드에서 data-ad-client 코드를 입력해줍니다.

▾ themes/hipaper/_config.yml 코드

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/28.png)

이제 adsense 스크립트 적용 파일을 만들어 보도록 하겠습니다.

자신의 테마 폴더안에 `layout/_partial` 안에 `google-adsense.ejs` 파일을 생성합니다.

그 후, 다음과 같이 코드를 작성합니다.

▾ google-adsense.ejs 코드

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/29.png)

이제 해당 파일을 불러오도록 하겠습니다.

자신의 테마 폴더안에 `layout/_partial/head.ejs`로 이동하여 해당 코드를 삽입하여 줍니다.

▾ head.ejs 코드

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/30.png)

여기까지 완료 하였으면 홈페이지를 실행시켜 봅니다.

그 후 F12 개발자 모드로 들어가서 Sources 탭에서 자신의 코드가 정상적으로 삽입되었는지 확인합니다.

```bash
$ hexo server
```

▾ 홈페이지 Sources 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/31.png)

정상적으로 자신의 코드가 삽입되었으면, 이제 배포를 해줍니다.

```bash
$ hexo clean
$ hexo deploy
```

마지막으로 Google AdSense 홈페이지에서 `코드를 사이트에 붙여넣었습니다.` 체크 박스를 체크하고

완료 버튼을 눌러줍니다.

그러면 모달창이 나타나며 코드 확인 완료가 끝났습니다.

몇일 후에 확인해보도록 하겠습니다.

▾ 코드 확인 완료 화면

![](https://raw.githubusercontent.com/ljlm0402/ljlm0402.github.io/site-images/new-gh-page/32.png)
