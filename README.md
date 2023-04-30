<div align="center">
  <br>

  <h1>GitHub BLOG_JEKYLL</h1>

</div>

<h4 align="center">
  Git BLOG by using<a href="https://jekyllrb.com/" target="_blank"><code>Jekyll</code></a>
</h4>

. <h3 align = "center"> <https://minchan02.github.io> </h3>
  
<br>

해당 Repository는 Jekyll을 사용해서 제작한 깃 블로그 입니다. 국민대학교 유레카 프로젝트 강의 내용을 기반으로 제작되었습니다. 

<p align="center">
  Windows10환경에서 windowsPowerShell 터미널을 이용해서 프로젝트를 진행했습니다.
</p>




## Connect Git

깃허브에서 `<username>.github.io` 이름의 repostiory를 생성한다.

지정한 디렉토리에 git 저장소를 지정한다:

```
$ git init
```

git add, commit 후에 원격저장소를 연결한다:

```
$ git remote add origin https://github.com/minchan481/minchan481.github.io
```

## Generae PAT
github -> Setting -> Developer settings -> Personal access tokens -> Generate new token


이후엔 git status, git add, git commit, git push 등의 명령어를 이용해 깃허브 원격 저장소에 코드 업로드

## Install Jekyll

Windows 환경에서 Jekyll을 설치하기 위해서 windows powershell 터미널을 이용했다.
먼저 해당 링크를 통해 Ruby를 설치한다 : `https://rubyinstaller.org/downloads/`

지킬을 설치한다 : 

```
$ gem install jekyll bundler
```
! 윈도우 환경에서 설치가 되었지만 bundler에 오류가 있었다. 
그래서 일단 다음 과정을 계속 진행했다.


해당 디렉토리에 Jekyll을 설치한다 :

```
$ jekyll new . --force
```

jekyll을 실행한다 :

```
$ bundle exec jekyll serve
```

하지만 jekyll 실행 과정에서 다음과 같은 오류가 나왔다 : `Jekyll 4.2.0 Please append --trace to the serve command`

그래서 구글링을 통해 해결해 주었다. [오류 해결](https://velog.io/@minji-o-j/jekyll-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0) ↓↓↓

## `❌ Jekyll 4.2.0 Please append --trace to the serve command`

`--trace` 명령을 추가해 주었다.

```
$ bundle exec jekyll serve --trace
```

## `❌ cannot load such file -- webrick`

`bundle add webric` 명령 실행 후 다음과 같은 오류가 나왔다.

## `❌ Could not find gem 'webric x64-mingw32'`

webrick을 설치해준다 : 

```
$ gem install webrick
```

후에 다시 명령을 실행한다 : 

```
$ bundle exec jekyll serve --trace
```

정상적으로 동작하는 것을 확인 할 수 있다.

## Change Theme
기본 테마의 블로그에서 다른 테마로 바꾸어주었다.
jeffreytse의 yat 테마를 사용하였다.
[https://github.com/jeffreytse/jekyll-theme-yat](https://github.com/jeffreytse/jekyll-theme-yat).

해당 repository의 내용을 git clone해서 로컬 저장소로 가져온다.
그 다음 깃허브 페이지에 접속하면 테마가 바뀐것을 확인 할 수 있다.

## Add Comments - Disqus
Disqus를 활용해서 댓글 기능을 추가한다.

Disqus 홈페이지에 접속하여 가입한다. [Disqus](https://disqus.com/)
Disqus에 홈페이지를 추가한다.

1. Jekyll Playform을 선택한다.

2. 깃허브 Web Page를 추가시킨다.

3. _config.yml에 Disqus 코드를 반영한다.

```
comment:
  provider:         "disqus"
  disqus:
    shortname:        "minchan481"

```

4. universal code를 반영한다.

_layouts/post.html

``` html
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    // let PAGE_URL = "{{site.url}}{{page.url}}"
    // let PAGE_IDENTIFIER = "{{page.url}}"
    var disqus_config = function () {
    this.page.url = "https://minchan481.github.io/";  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = "minchan481"; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://minchan481.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
```

5. post에 댓글을 허용한다.

`comments : true` 를 지정한다.
