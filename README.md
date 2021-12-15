<div align="center">
  <br>

  <h1>GitHub BLOG_JEKYLL</h1>

</div>

<h4 align="center">
  Git BLOG by using<a href="https://jekyllrb.com/" target="_blank"><code>Jekyll</code></a>
</h4>
<!--
<p align="center">
  <a href="https://jeffreytse.github.io/jekyll-theme-yat">
    <img src="https://github.com/jeffreytse/jekyll-theme-yat/workflows/Github%20Pages/badge.svg"
      alt="Github Pages" />
  </a>
</p>
-->

<br>

해당 Repository는 Jekyll을 사용해서 제작한 깃 블로그 입니다. 국민대학교 유레카 프로젝트 강의 내용을 기반으로 제작되었습니다. 

<p align="center">
  Windows10환경에서 windowsPowerShell 터미널을 이용해서 프로젝트를 진행했습니다.
</p>

## Connecting Git

깃허브에서 `<username>.github.io` 이름의 repostiory를 생성한다.

지정한 디렉토리에 git 저장소를 지정한다:

```
$ git init
```

git add, commit 후에 원격저장소를 연결한다:

```
$ git remote add origin https://github.com/minchan481/minchan481.github.io
```

## PAT 생성하기
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

그래서 구글링을 통해 해결해 주었다. [오류 해결](https://velog.io/@minji-o-j/jekyll-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0).
↓↓↓

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

## Installation

There are three ways to install:

- As a [gem-based theme](https://jekyllrb.com/docs/themes/#understanding-gem-based-themes).
- As a [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/) (GitHub Pages compatible).
- Forking/directly copying all of the theme files into your project.

### Gem-based Theme Method

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "jekyll-theme-yat"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: jekyll-theme-yat
```

And then execute:

```bash
$ bundle
```

Or install it yourself as:

```bash
$ gem install jekyll-theme-yat
```

### Remote Theme Method with GitHub Pages

Remote themes are similar to Gem-based themes, but do not require `Gemfile` changes or whitelisting making them ideal for sites hosted with GitHub Pages.

To install:

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "github-pages", group: :jekyll_plugins
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
# theme: owner/name --> Don't forget to remove/comment the gem-based theme option
remote_theme: "jeffreytse/jekyll-theme-yat"
```

And then execute:

```bash
$ bundle
```

### GitHub Pages without limitation

GitHub Pages runs in `safe` mode and only allows [a set of whitelisted plugins/themes](https://pages.github.com/versions/). **In other words, the third-party gems will not work normally**.

To use the third-party gem in GitHub Pages without limitation:

Here is a GitHub Action named [jekyll-deploy-action](https://github.com/jeffreytse/jekyll-deploy-action) for Jekyll site deployment conveniently. 👍

## Usage

Add or update your available layouts, includes, sass and/or assets.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_data`, `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `jekyll-theme-yat.gemspec` accordingly.

## Contributing

Issues and Pull Requests are greatly appreciated. If you've never contributed to an open source project before I'm more than happy to walk you through how to create a pull request.

You can start by [opening an issue](https://github.com/jeffreytse/jekyll-theme-yat/issues/new) describing the problem that you're looking to resolve and we'll go from there.

## License

This theme is licensed under the [MIT license](https://opensource.org/licenses/mit-license.php) © JeffreyTse.

<!-- External links -->

[jekyll]: https://jekyllrb.com/
[yat-git-repo]: https://github.com/jeffreytse/jekyll-theme-yat/
[yat-live-demo]: https://jeffreytse.github.io/jekyll-theme-yat/
[jekyll-spaceship]: https://github.com/jeffreytse/jekyll-spaceship
[jekyll-seo-tag]: https://github.com/jekyll/jekyll-seo-tag
[jekyll-sitemap]: https://github.com/jekyll/jekyll-sitemap
[jekyll-feed]: https://github.com/jekyll/jekyll-feed
[highlight-js]: https://github.com/highlightjs/highlight.js
