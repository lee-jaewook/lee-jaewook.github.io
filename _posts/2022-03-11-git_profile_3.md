---
layout: article
title: Github(깃허브) 프로필 꾸미기(3) - Technique Icons & Badge
tags: github
article_header:
  type: overlay
  theme: dark
  background_color: 'rgba(0, 255, 0, .5)'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(75, 106, 120, 0.7), rgba(75, 106, 120, 1.0))'
    src: assets/images/posts/github/2/1.png
published : true
---
깃허브 프로필에 기술 아이콘 및 소셜 뱃지 생성하는 법

<!--more-->
# 1. 기술 아이콘(Technique Icons) 생성
```markdown
<!-- github_user_name/README.md -->
<div style="display: inline_block">
  <img align="center" alt="Python" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg">
</div>
```

기술 아이콘을 추가하는 방법은 README.md 파일에 위의 코드를 추가하시면 됩니다. 예시 코드에는 파이썬만 추가하였지만 [devicon.dev](https://devicon.dev/)에 접속하셔서 원하는 기술 아이콘의 `<img>` 요소를 얻을 수 있습니다.

![](/assets/images/posts/github/3/2.png)

![](/assets/images/posts/github/3/1.png)

# 2. 소셜 뱃지(Social Badge) 생성
[150-badges-for-github](https://devicon.dev/)에 들어가셔서 원하는 뱃지의 url을 복사해 `<a>`태그로 추가하시면 됩니다. 예시 코드는 아래와 같습니다.

```markdown
<!-- github_user_name/README.md -->
<div style="display: inline_block"><br>
  <a href="https://github.com/lee-jaewook" target="_blank"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/lee-jaewook/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
</div>
```
![](/assets/images/posts/github/3/3.png)
