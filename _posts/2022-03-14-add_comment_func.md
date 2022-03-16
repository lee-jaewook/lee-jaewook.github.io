---
layout: article
title: Utterances로 깃허브 페이지(Github Page) 댓글 기능 추가하는 법
aside:
  toc: true
tags: Blog
published : true
---
![](/assets/../../assets/images/posts/blog/03_14/1.png){: .align-center}

깃허브 페이지에 댓글 기능을 추가하는 방법 중에 가장 대중화된(?) 방법은 [Disqus](https://disqus.com/)를 사용하는 것 입니다. Disqus도 무료로 사용할 수 있지만... 광고가 붙게되고 ~~못생겨서~~
대안을 찾게 됐습니다. 대안을 찾을 때 고려했던 사항은  

1. 광고가 없어야 한다. 🚫
2. 가볍고 예뻐야 한다. 💅

입니다. 그 결과 발견💡한 것이 [Utterances](https://utteranc.es/) 입니다.  
<!--more-->  

![](/assets/../../assets/images/posts/blog/03_14/2.png){: .align-center}

`Utterances`를 사용하게 되면 위의 사진처럼 댓글을 Github의 issue로 관리할 수 있습니다. 댓글을 달기 위해서는 Github의 계정이 필요한 것이 단점이지만, 제 블로그에 들어오셔서 댓글을 남기실 분들은 Github 계정이
있을테니 괜찮겠죠??  

지금부터는 차례차례 `Utterances`를 제 블로그에 적용해보겠습니다.

# 1. 댓글을 관리할 레파지토리 생성
![](/assets/../../assets/images/posts/blog/03_14/4.png){: .align-center}

Utterance를 적용하기에 앞서 댓글(깃허브 이슈)를 관리할 public repository가 필요합니다. 이름은 정해져있는게 아니고 임의로 지정하셔도 무관합니다. 다만, 꼭 `public`으로 생성하셔야 합니다.

![](/assets/../../assets/images/posts/blog/03_14/5.png){: .align-center}

그 다음 생성한 레파지토리 안에 `utterances.json` 파일을 생성하셔서 아래의 코드를 작성하시면 사전 작업 완료입니다.

```json
{
    "origins": ["https://lee-jaewook.github.io"] // [*] 안에는 댓글 기능을 추가할 사이트를 입력
}
```

# 2. 설치
![](/assets/../../assets/images/posts/blog/03_14/3.png){: .align-center}

먼저 깃허브 앱의 [Utterances 설치 페이지](https://github.com/apps/utterances)에서 `install` 버튼을 눌러줍니다.

![](/assets/../../assets/images/posts/blog/03_14/6.png){: .align-center}

그 다음 `Only select repositories`를 선택, `select repositoris`를 클릭하셔서 [챕터 1](#1-댓글을-관리할-레파지토리-생성)에서 만들었던 repository를 선택하시면 됩니다.

# 3. 설정
![](/assets/../../assets/images/posts/blog/03_14/7.png){: .align-center}

설치를 완료하시면 위에 보이시는 설정 페이지로 자동으로 이동됩니다. 이 페이지에서 `rpositroy 설정`, `포스트와 이슈 맵핑`, `이슈 라벨`, `테마 설정`을 하실 수 있습니다.

![](/assets/../../assets/images/posts/blog/03_14/8.png){: .align-center}

`rpositroy 설정`은 `username/repository_name`을 기입하시고 `포스트와 이슈 맵핑`은 pathname으로 이슈를 매핑하는게 나중에 블로그 내용이 바뀌어도 이슈가 맵핑될 수 있을 것 같아 선택하였습니다.

![](/assets/../../assets/images/posts/blog/03_14/9.png){: .align-center}

설정을 완료하신 다음 `Enable Utterances` 스크립트를 복사합니다.

# 4. 깃허브 페이지 파일에 코드 추가

마지막으로 `Enable Utterances` 스크립트를 넣을 파일을 찾아야 합니다. 보통 `_layouts/article.html`에 넣으시면 되는데, 제가 사용하고 있는 [TeXt 테마](https://github.com/kitian616/jekyll-TeXt-theme)에서는  

```yml
## => Comments
##############################
comments:
  provider: "custom" # false (default), "disqus", "gitalk", "valine", "custom"
```

`_config.yml`의 commets provider를 `custom`으로 수정한 뒤 `_inclue/comments-providers/cumtom.html`에 아래와 같이 코드를 추가하면 됩니다.  

```html
<!-- start custom comments snippet -->
<script src="https://utteranc.es/client.js"
        repo="lee-jaewook/blog-comments"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
<!-- end custom comments snippet -->
```

수정된 파일을 모두 깃허브에 push하시면 아래와 같이 댓글 기능이 추가된 것을 확인할 수 있습니다.(로컬로는 안보입니다!)

![](/assets/../../assets/images/posts/blog/03_14/10.png){: .align-center}


