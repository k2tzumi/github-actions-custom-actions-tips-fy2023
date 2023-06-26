---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
fonts:
  # basically the text
  sans: 'Noto Sans JP'
  # use with `font-serif` css class from windicss
  serif: 'Noto Serif JP'
  # for code blocks, inline code, etc.
  mono: 'Noto Sans Mono'
---

# FY2023で導入してよかったGitHub Actionsのカスタムアクション＆Tips集

[PHPカンファレンス福岡2023 フリースタイルトーク](https://phpcon.fukuoka.jp/2023/)  
June 24, 2023.  
v0.0.5

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/k2tzumi/github-actions-custom-actions-tips-fy2023/blob/main/slides.md" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
layout: two-cols-header
---

# 自己紹介

katzumiと申します  

以下のアカウントで活動しています  
<fxemoji-partypopper /> [祝初採択！](https://fortee.jp/phpconfukuoka-2023/proposal/9af6e2bc-b64a-4287-baef-ee17ddd21560)  
このあとスグ！VAddyホール <lucide-clock-2 /> で僕と握手！  
今日は[コレ](https://fortee.jp/phpconfukuoka-2023/proposal/dee83699-f82c-4de9-96cb-eb189373507d)の供養です <twemoji-headstone />


::left::

<img src="https://pbs.twimg.com/profile_images/799890486773170176/KN4gKfS2_400x400.jpg" class="rounded-full w-40 mt-16 mr-12　float-left"/>  
<img src="/twitter_qr.png" class="mt-16 ml-8 w-25"/>

 <logos-twitter /> [katzchum](https://twitter.com/katzchum) 

::right::

<img src="https://avatars.githubusercontent.com/u/1182787?v=4" class="rounded-full w-40 mt-16 mr-12"/>

<logos-github-octocat /> [k2tzumi](https://github.com/k2tzumi)  
<simple-icons-zenn /> [katzumi](https://zenn.dev/katzumi)  



<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---
layout: default
---

# おじさん歴

1. Travisおじさん <logos-travis-ci />
1. CircleCIおじさん <logos-circleci />
2. Jenkinsおじさん <devicon-jenkins />
3. Github Actionsおじさん <logos-github-actions />

まあ最近はGithub Actionsが多いですよね？

---
layout: center
---

# 良かったカスタムアクション集

---

# Octocov

https://github.com/marketplace/actions/run-octocov

コードメトリクスツールです。PHPでも使える！  
一つのアクションを実行するだけで差分が出るのが良い！  
→ カバレッジを下げないことを意識づけできるようになりました

<img src="https://raw.githubusercontent.com/k1LoW/octocov-action/main/docs/comment_with_diff.png" class="h-50 rounded shadow" alt="Comment with diff" />

以前自前で "[GitHub Actionsでカバレッジを可視化する](https://zenn.dev/katzumi/articles/995df5abebc91e312167)" ことを行なっていましたが、差分までは出せなかったのがサクッと表示できるようになりました。

---
layout: two-cols-header
---

# Tagpr

https://github.com/marketplace/actions/automate-pull-request-generation-and-tagging-for-releases-using-tagpr

マージされたら自動でタグを打ってくれています。  
リリースフローをすごくいい感じにしてくれて開発者体験がすごくいいです。  
"[BaaSなプロジェクトにtagprを導入してみた](https://zenn.dev/katzumi/articles/introducing-tagpr-to-backend-as-a-service)"という記事にしました

::left::

<Tweet id="1576165379747246082" scale="0.7" />

::right::

<img src="http://songmu.github.io/images/ghzo/22-0830-0036-a8c809bd2e307295.png" class="h-50 rounded shadow" alt="pull request" />

<!-- 実はこのスライドの作成環境もGithub Actionsで管理されており、スライド自体がバージョンをナンバリングして管理できるようなっています -->

---

# runn

https://github.com/marketplace/actions/run-runn

APIシナリオテストツールのCI組み込みがより簡単に！（宣伝）  
そもそもAPIシナリオテストってどうよ？という方は是非この後VAddyに来てください！（２回目）  
"[APIシナリオテストの新ツールrunn](https://zenn.dev/katzumi/articles/api-scenario-testing-with-runn)" という紹介記事を書いているのでどぞー

<Tweet id="1561490586858770432" scale="0.7" />

---
layout: center
---

# Tips

---

# 連続pushした時に止めるアレ = concurrency

名前が分かりづらいので見落としている人が多いかも。。  
定期的に記事 [^1] にいいねが付きます。

```yaml {all|11-}
name: test
on:
  pull_request:
    types: [opened, reopened, synchronize]
    paths:
      - 'foo/**'
  push:
    branches:
      - develop

concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true
```

[^1]: [zenn.dev](https://zenn.dev/katzumi/articles/using-concurrency-at-github-actions)

---

# GitHub APIをプログラマブルに呼び出す

https://github.com/marketplace/actions/github-script

javascriptで書ける！シェルで文字列加工や条件分岐は怠いですよねw

```yaml
  - name: Upload Release Asset
    uses: actions/github-script@v6
    with:
      github-token: ${{ secrets.GITHUB_TOKEN }}
      script: |
        const fs = require('fs');
        const path = require('path');
        const release = await github.rest.repos.getReleaseByTag({
          owner: context.repo.owner,
          repo: context.repo.repo,
          tag: context.payload.inputs.tag
        });
        const filePath = path.join(path.resolve(process.env.GITHUB_WORKSPACE), 'slides-export.pdf');
        const fileContent = fs.readFileSync(filePath);
        await github.rest.repos.uploadReleaseAsset({
          url: release.data.upload_url,
          headers: {
            'content-type': 'application/octet-stream',
            'content-length': fileContent.length,
          },
          name: 'slides-export.pdf',
          data: fileContent,
        });
```

---
layout: end
---

ご清聴ありがとうございます