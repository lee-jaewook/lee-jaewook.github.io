---
layout: article
title: Github(깃허브) 프로필 꾸미기(1)
tags: github
article_header:
  type: overlay
  theme: dark
  background_color: 'rgba(0, 255, 0, .5)'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(75, 106, 120, 0.7), rgba(75, 106, 120, 1.0))'
    src: assets/images/posts/github/1/11.png
---
README.md 생성과 블로그 포스트 리스트(blog post list) 생성
<!--more-->
# 1. README.md 파일 생성
블로그 리스트와 Stats를 추가하기에 앞서 각자의 깃허브 사용자명으로 폴더를 생성한 뒤 , 해당 폴더 안에 README.md 파일을 추가해 아래와 같이 간단한 내용을 적어줍니다.
```markdown
<!-- <github user name>/README.md -->
# Hi there, I'm `your name`  👋 
```

이 파일을 깃허브 사용자명과 동일한 repository에 push해 주게되면 profile 상단에 표시되게 됩니다.

![](/assets/images/posts/github/1/4.png)

# 2. 블로그 포스트 리스트 생성
## 2.1 README.md 파일 수정
[blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow)를 사용해 깃허브 프로필에 블로그 리스트를 생성하기 위해서 `README.md` 파일에 아래와 같이 내용을 추가해줍니다.

```markdown
<!-- <github user name>/README.md -->
### 📕 Latest Blog Posts
<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
```

## 2.2 폴더 생성 및 파일 생성
`/.github/workflows`폴더를 생성한 뒤 해당 폴더 안에 `blog-post-workflow.yml` 파일을 생성해, `blog-post-workflow.yml` 파일에 아래와 같이 입력합니다.

```yml
# <github user name>/.github/workflows/blog-post-workflow.yml
name: Latest blog post workflow
on:
  schedule: # Run workflow automatically
    - cron: '0 * * * *' # Runs every hour, on the hour
  workflow_dispatch: # Run workflow manually (without waiting for the cron to be called), through the Github Actions Workflow page directly

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Pull in dev.to posts
        uses: gautamkrishnar/blog-post-workflow@master
        with: 
          feed_list: # "your blog feed url"
```

여기서 `feed_list`에 여러분 블로그의 RSS feed URL을 적어주시면 됩니다. 저처럼 jekyll로 만든 github page를 사용하고 계신 분은 `_cofig.yml`파일에 

```yml
plugins:
  - jekyll-feed
```

이렇게 `jekyll-feed`를 추가하신 뒤, `feed_list`에 `"<github page url>/feed"`를 기입하시면 됩니다.  
이제 수정된 모든 파일을 깃허브에 업로드합니다.

### 2.3 깃허브 workflows 설정

![](/assets/images/posts/github/1/5.png)

업로드를 했지만 위의 그림처럼 포스트의 리스트가 표시되지 않습니다🤦‍♂️.   
마지막으로 한가지 작업이 더 남아있습니다.  

![](/assets/images/posts/github/1/6.png)

![](/assets/images/posts/github/1/7.png)

프로필을 작성중인 `깃허브 사용자명`프로젝트에 들어가셔서 `Actions`을 누르시고 좌측의 `Workflows` 밑에 `Latest blog post workflow`를 클릭, `Run workflow`를 클릭하시면 됩니다.

![](/assets/images/posts/github/1/8.png)

잠시 기다린 뒤, 새로고침을 하면 아래와 같이 `workflow`가 실행되고 다시 프로필에 가보시면 리스트가 이제 보이게 됩니다  
👍👍👍

![](/assets/images/posts/github/1/9.png)

![](/assets/images/posts/github/1/10.png)