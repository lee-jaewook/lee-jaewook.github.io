---
layout: article
title: Github(깃허브) 프로필 꾸미기(2) - Stats
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
깃허브 프로필에 Github Stats 생성하는 법

<!--more-->
# Github Stats 생성
```markdown
<!-- github_user_name/README.md -->
<div align="center">
  <a href="https://github.com/your_git_username">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=your_git_username&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=your_git_username&layout=compact&langs_count=7&theme=dracula"/>
</div>
```

Github Stats을 추가하는 방법은 간단합니다. README.md 파일에 위의 코드를 추가하고, `your_git_username`을 자신의 깃허브 사용자명으로 수정해주시면 됩니다.

![](/assets/images/posts/github/2/1.png)

(번외로 스타일을 바꾸고 싶으신 분은 [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)를 참고하시면 됩니다.)