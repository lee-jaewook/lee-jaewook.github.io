---
layout: article
title: Github(깃허브) 프로필 꾸미기(4) - Contribution Chart
tags: github
article_header:
  type: overlay
  theme: dark
  background_color: 'rgba(0, 255, 0, .5)'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(75, 106, 120, 0.7), rgba(75, 106, 120, 1.0))'
    src: assets/images/posts/github/4/1.svg
published : true
---
깃허브 프로필에 컨트리뷰션 차트 추가하는 법

<!--more-->
# 컨트리뷰션 차트(Contribution chart) 추가

```yml
# <github user name>/.github/workflows/cobrinha.yml
name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: your_git_username
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

우선 `/.github/workflows` 폴더를 생성하시고, 폴더 안에 `cobrinha.yml`파일을 생성하셔서 위와 같이 코드를 작성해주시면 됩니다. 다른건 수정할게 없고, `github_user_name`에 자신의 사용자명을 기입하시면 됩니다

```markdown
<!-- github_user_name/README.md -->
## 🌱 Git Contribution Chart
 ![Snake animation](https://github.com/github_user_name/github_user_name/blob/output/github-contribution-grid-snake.svg)<br>
```

위의 코드에서 `github_user_name`을 자신의 깃허브 사용자명으로 바꾸시고 `README.md`파일에 추가해주시면 됩니다.

그 다음은 [Github(깃허브) 프로필 꾸미기(1)](https://lee-jaewook.github.io/2021/07/10/git_profile_1.html)에서 설명드렸던 것처럼 깃허브 레파지토리에서 `Action`을 실행해 주시면 됩니다.

![](/assets/images/posts/github/4/2.png)

![](/assets/images/posts/github/4/3.png)




