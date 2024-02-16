---
layout: post
title: Today I Learned
date: 2024-02-16 14:28:20 +0900
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: githubblog.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Learning, Blog]
---
## 🌟Github Blog 만들기
1. 내 계정이름을 딴 Repository를 만든다.
> <계정이름>.github.io 로 public repository를 만들었다.

![github.io]({{site.baseurl}}/assets/img/image.png)

2. 해당 `git clone`을 받고(VSCode 사용), 간단하게 `index.html` 파일을 만들고, github에 commit한다. (아무 내용이나 작성)
```bash
git add index.html
git commit -m "add index.html"
git push
```

3. Github에 commit하면 자동으로 **build and deployment**가 되면서 조금 기다리면 `Settings` > `Pages`에 가보면 내 사이트가 만들어져있다!

---

## 🎀 Jekyll 사용하여 웹사이트 호스팅하기

* **Jeckyll이란?** : Ruby 언어를 이용해 개발한 정적 웹사이트 생성기(Static Website Generator)

1. Ruby 설치하기. 
- https://rubyinstaller.org/downloads/ 에서 다운로드 가능하다. 
- 설치 후 Gitbash에서 다음 명령어를 순서대로 실행한다.
```bash
gem install bundler
gem install github-pages
gem install jekyll
```

- 설치가 완료되면 성공적으로 jekyll 명령어가 동작하는지 확인해본다. 

![jekyll check]({{site.baseurl}}/assets/img/post1.png)

2. 이제 VSCode로 돌아가 아까 만들었던 `index.html`을 삭제하고, `jekyll new .` 명령어를 실행한다. (.git은 삭제 X)

3. Jekyll이 잘 적용되었는지 확인해본다.
```bash
bundle install
bundle exec jekyll serve
```

![jekyll check]({{site.baseurl}}/assets/img/post2.png)

4. 테마 입히기
- 나는 이 테마를 사용했다.
https://jekyllthemes.io/theme/flexible-jekyll
- Github 파일을 zip으로 받고, github.io 폴더로 가지고온다. (원래 있던 이전 파일들은 .git을 빼고는 모두 삭제!)

5. 설정 수정 (`_config.yml` 파일)
- baseurl: "" 비워주기
- url: "https://<계정이름>.github.io 로 변경
- 나머지 필요한 부분들도 모두 바꿔준다. (ex. title, description, author...등)

6. 게시글 작성하기
- `_posts` 경로에 작성한다. 
- 예시 게시글들을 따라 작성하면 된다! 지금 내가 하고 있는 것이다. 
- 맨 위에는 설정들이 있다. (title, date, img, fig-caption, tags) 
- 설정에서 주의할 것은 date를 +0900으로 설정해주어야 한국표준시로 설정된다~ 그렇지 않으면 자꾸 ~ has a future date로 오류가 뜬다..

7. 똑같이 Jekyll 적용하고, 잘 적용되었는지 확인 후 git에 올려주면 된다!
```bash
bundle install
bundle exec jekyll serve
```