---
marp: true
theme: default
paginate: true
size: 16:9
title: Claude Codeでショート動画をつくる3時間
author: Seiya
---

<style>
:root{
  --ink:#1F2933; --paper:#FAF9F6; --accent:#D97757; --accent2:#2A9D8F;
  --muted:#6B7280; --line:#E7E3DC; --soft:#F0EDE7;
}
section{
  background:var(--paper); color:var(--ink);
  font-family:-apple-system,"Hiragino Sans","Hiragino Kaku Gothic ProN","Noto Sans JP","Yu Gothic",sans-serif;
  font-size:26px; padding:54px 64px; line-height:1.55;
}
h1{ font-size:46px; border-bottom:4px solid var(--accent); padding-bottom:.18em; letter-spacing:.01em;}
h2{ font-size:33px; }
h3{ font-size:27px; color:var(--accent2); margin:.2em 0;}
strong{ color:var(--accent); }
a{ color:var(--accent2); }
code{ background:var(--soft); padding:.08em .35em; border-radius:6px; font-size:.88em;}
pre{ background:var(--ink); color:#F6F8FA; padding:.85em 1.1em; border-radius:12px; font-size:19px;}
pre code{ background:transparent; color:inherit;}
ul,ol{ margin-top:.2em;} li{ margin:.22em 0;}
blockquote{ border-left:5px solid var(--accent2); margin:0; padding:.25em 1em;
  background:#EFF6F4; border-radius:0 10px 10px 0;}
.eyebrow{ font-size:19px; letter-spacing:.18em; color:var(--accent); font-weight:800;}
.term{ display:inline-block; background:#fff; border:2px solid var(--accent); color:var(--accent);
  border-radius:999px; padding:.02em .7em; font-weight:800; font-size:.8em; margin-right:.2em;}
.gloss{ color:var(--muted);}
.small{ font-size:18px; color:var(--muted);}
.do{ background:#EAF6F3; border-left:6px solid var(--accent2); padding:.5em .9em; border-radius:0 12px 12px 0;}
.warn{ background:#FBEEE8; border-left:6px solid var(--accent); padding:.5em .9em; border-radius:0 12px 12px 0;}
.cols{ display:flex; gap:24px;}
.col{ flex:1; background:#fff; border:1px solid var(--line); border-radius:14px; padding:.7em .9em;}
.diagram{ display:flex; gap:10px; align-items:stretch; margin-top:.4em;}
.box{ flex:1; background:#fff; border:2px solid var(--line); border-radius:14px; padding:.6em .4em; text-align:center; font-size:.82em;}
.box b{ display:block; color:var(--accent); font-size:1.0em; margin-bottom:.15em;}
.arrow{ display:flex; align-items:center; color:var(--muted); font-size:26px;}
.split{ display:flex; gap:30px; align-items:center;}
.split>.t{ flex:1; min-width:0;}
.split>img{ flex:none; width:300px; border-radius:18px; box-shadow:0 8px 24px rgba(31,41,51,.13); background:#fff;}
.split.sm>img{ width:240px;}
.split.lg>img{ width:340px;}
.gallery{ display:flex; gap:18px; margin-top:.5em;}
.gallery a{ flex:1; min-width:0; text-decoration:none; color:var(--ink); display:block;}
.gallery img{ width:100%; border-radius:12px; box-shadow:0 6px 18px rgba(31,41,51,.18); display:block; border:1px solid var(--line);}
.gallery .cap{ display:block; font-size:17px; line-height:1.3; margin-top:.35em;}
.gallery .views{ display:block; font-size:15px; color:var(--accent); font-weight:800;}
a .term{ cursor:pointer;}
section.title{ background:linear-gradient(135deg,#1F2933,#2b3a47); color:var(--paper); justify-content:center;}
section.title h1{ color:#fff; border:none; font-size:58px;}
section.title h2{ color:#E9C3B4; font-weight:500;}
section.section{ background:var(--ink); color:var(--paper); justify-content:center;}
section.section h1{ color:#fff; border:none; font-size:52px;}
section.section .eyebrow{ color:var(--accent);}
section::after{ color:var(--muted); font-size:15px;}
</style>

<!-- _class: title -->
<!-- _paginate: false -->

<span class="eyebrow">CLAUDE CODE × ショート動画 / 3時間ハンズオン</span>

# Claude Codeでショート動画をつくる

## 台本も・素材も・音声も・編集も、AIに頼んで“動く動画”にする

by Seiya

<!-- 最初の10分：自己紹介＋今日の流れ＋完成形デモ。専門知識ゼロ前提で、気楽に。 -->

---

## 自己紹介（テンプレ・自由に書き換え）

- 名前 / ふだんやっている動画制作の仕事
- なぜこの会を開いたのか（ひとことで）
- 今日のスタンス：**「全部わからなくてOK。1本できれば勝ち」**

<div class="do">

今日は“エンジニアになる会”ではありません。**いつもの「素材集め・編集・書き出し」を、AIに頼んで時短する**会です。

</div>

---

## 今日のゴール

<div class="do" style="font-size:1.05em">

**自分の手で、ショート動画を実際に1本書き出すところまで。**<br>
作り方の“3つの型”を、手を動かして体験します。

</div>

<div class="diagram">
  <div class="box"><b>① 静止画ショート</b>AIイラスト＋ナレーション<br><span class="small">画像を並べて動画に</span></div>
  <div class="arrow">／</div>
  <div class="box"><b>② 素材ショート</b>ストック動画＋ナレーション<br><span class="small">既存の映像を組み合わせ</span></div>
  <div class="arrow">／</div>
  <div class="box"><b>③ 切り抜きショート</b>長い動画から名場面<br><span class="small">文字起こし＋字幕</span></div>
</div>

<div class="small">

むずかしい契約や公開設定はしません。まずは「自分のPCで動画ファイルができる」ところがゴール。

</div>

---

## 今日の流れ（3時間）

| 時間 | 内容 |
|---|---|
| 0:00–0:15 | 自己紹介・今日の流れ・**完成形デモ** |
| 0:15–0:45 | 最低限の地図（Claude Codeの言葉と仕組み） |
| 0:45–1:00 | みんなで準備（アプリ・APIキー・素材） |
| 1:00–1:45 | ハンズオン①：**静止画ショート**（AIイラスト＋ナレーション） |
| 1:45–2:15 | ハンズオン②：**素材ショート**（ストック動画＋ナレーション） |
| 2:15–2:45 | ハンズオン③：**切り抜きショート**（長い動画→名場面） |
| 2:45–3:00 | おまけ：**ブラウザ自動化**・まとめ・質問 |

<div class="warn small">

正直な注意：3時間に全部を“完璧に”は入りません。①を全員でしっかり → ②③は要点デモ＋各自トライ、という構成です。**①で「作れた！」を持ち帰るのが最優先。**

</div>

---

## まず完成形を見てもらいます（デモ）

<div class="do">

これから1〜2分。**「テーマを伝えるだけで、ナレーション付きのショートが書き出される」**ところを先に見せます。

</div>

- ゴールが見えていると、途中の作業で迷子になりません
- 「あれを自分で作るのか」という感覚を持って始めましょう
- 完成した縦型動画（9:16）を、その場で再生します

<!-- ここでSeiyaが実際に1本ライブ生成 → 再生まで見せる。 -->

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">PART 1</span>

# 最低限の地図
### 〜言葉は“使う直前に1個ずつ”〜

---

## そもそもClaude Codeって何？

<div class="split lg">
<div class="t">

<span class="term">LLM</span><span class="gloss">ネットの文章を大量に読んだ“物知りな助手”</span>

<span class="term">Claude</span><span class="gloss">その助手のひとり（Anthropic社製）</span>

<span class="term">Claude Code</span><span class="gloss">その助手に“手”を付けたもの</span>

> ふつうのAIチャットは「答えを言う」だけ。**Claude Codeは、あなたのPCを実際に操作して、ファイルを作ったり、動画を書き出したりできる。**

</div>
<img src="img/llm.png" alt="たくさんの本に囲まれた物知りな助手のイラスト">
</div>

---

## なぜ動画制作と相性がいい？

- **言葉で頼める**：コードや専門ソフトの操作を覚えなくていい
- **自分で手を動かす**：素材集め→音声生成→編集→書き出しまで通しでやる
- **失敗を自分で直す**：エラーが出たら原因を探して直し、もう一度試す
- **道具につながる**：<span class="term">MCP</span>で画像生成・素材サイト・ブラウザにも接続

<div class="do">

要するに「**作れる人の条件**」が、“ソフトを使いこなせる”から“**やりたいことを言葉にできる**”に変わった。

</div>

---

## Claude Codeの“頭の中”：4つの言葉

<div class="diagram">
  <div class="box"><b>Context window</b>いま覚えていられる量<span class="small">＝机の広さ</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>Agentic loop</b>考える→やる→直す<span class="small">＝自分で回す</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>MCP</b>外の道具に挿す<span class="small">＝コネクタ</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>Skills</b>作業手順書<span class="small">＝レシピ集</span></div>
</div>

<div class="small" style="margin-top:.6em">

この4つだけ押さえれば、今日やることは全部「この組み合わせ」で説明できます。1個ずつ見ていきましょう。

</div>

---

## Context window（コンテキスト・ウィンドウ）

<span class="term">Context window</span><span class="gloss">AIが“いま同時に覚えていられる”情報の広さ＝作業机の広さ</span>

- 会話やファイルを読むほど、机の上がどんどん埋まっていく
- 机がいっぱいになると、**古い話を忘れたり、ぼんやり**してくる
- だから長い作業は、**こまめに区切る／要点を伝え直す**のがコツ

<div class="do">

実用のコツ：話が長くなって反応が変だなと思ったら、**新しいセッションで「今やりたいこと」だけ伝え直す**。机を片付ける感覚。

</div>

---

## Agentic loop（自分で回す仕組み）

<span class="term">Agentic loop</span><span class="gloss">考える→やる→結果を見る→直す、を自分で繰り返す</span>

<div class="diagram">
  <div class="box"><b>考える</b><span class="small">何をすべきか</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>やる</b><span class="small">素材生成・書き出し</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>確認</b><span class="small">結果・エラー</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>直す</b><span class="small">必要なら修正</span></div>
</div>

<div class="split sm">
<div class="t">

- 人が一手ずつ指示しなくても、ある程度**自走**する
- 動画づくりは工程が多い → ここがいちばん効く
- だから「**止める・確認する**」操作が大事になる

</div>
<img src="img/agentic_loop.png" alt="考える→やる→確認→直すをぐるぐる繰り返すループのイラスト">
</div>

---

## MCP（コネクタ）とは

<div class="split sm">
<div class="t">

<span class="term">MCP</span><span class="gloss">AI用の“USB端子”。外部サービスに挿す仕組み</span>

- Claude Code単体は「自分のPCの中」が基本
- **MCPを挿す**と、外の世界につながる
- 今日は<a href="https://elements.envato.com/"><span class="term">Envato</span></a>（素材サイト）や**ブラウザ**をMCPで操作します

</div>
<img src="img/mcp.png" alt="USB端子で外部の道具につながるAIのイラスト">
</div>

<div class="do">

イメージ：**画像生成AI・素材サイト・ブラウザ**を、AIの“手の届く範囲”に挿し込む。挿すだけで、できることが一気に増える。

</div>

---

## Skills（スキル）とは

<div class="split sm">
<div class="t">

<span class="term">Skills</span><span class="gloss">よく使う“作業手順書”をまとめたパック</span>

- 「この手順で動画を作って」を、あらかじめ覚えさせておけるもの
- 画面で **`/`（スラッシュ）** を打つと呼び出せる
- 毎回ゼロから説明しなくてよくなる

</div>
<img src="img/skills.png" alt="手順書（レシピ集）を持つロボットのイラスト">
</div>

<div class="do">

今日のハンズオンは、**ショート動画用のSkillsを呼び出す**のが中心。<br>
「①静止画」「②素材」「③切り抜き」それぞれに専用のSkillを用意しています。

</div>

---

## Agent / サブエージェント（おまけの言葉）

<span class="term">Agent</span><span class="gloss">ひとつの仕事を任せられる“AIの担当者”</span>
<span class="term">サブエージェント</span><span class="gloss">本体が、別の担当者に一部を“丸投げ”する仕組み</span>

- 大きな作業を、**小さな担当に分けて並行**で進められる
- 例：「画像を10枚作る担当」「ナレーションを作る担当」を分ける
- 私たちは**結果を受け取るだけ**。中の細かいやり取りは見なくてOK

<div class="small">

※ 今日は「そういう仕組みがある」程度でOK。Skillsの中で自動的に使われることがあります。

</div>

---

## Claude Codeの得意・苦手

- **得意**：素材集め・音声生成・編集の自動化／決まった手順のくり返し／試作を**速く**
- **得意**：「ちょっと直して」を何度でも（差分を見て採用/却下）

<div class="warn">

**苦手**：あいまいな丸投げ、細かい“感性の最終調整”、最新すぎる情報、権利関係の自動判断。<br>
→ **具体的に頼む・できた素材は自分の目で確認する**のが大事。特に**著作権／利用規約**は人間が最終チェック。

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">PART 2</span>

# みんなで準備
### 〜道具とカギ（APIキー）をそろえる〜

---

## 今日の道具立て（全体像）

<div class="diagram">
  <div class="box"><b>Claude Code</b>作業の司令塔<span class="small">指示を出す相手</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>Remotion</b>コードで動画を組む<span class="small">編集ソフトの代わり</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>IrodoriTTS</b>ナレーション音声<span class="small">声を作る</span></div>
  <div class="arrow">＋</div>
  <div class="box"><b>素材</b>画像/動画<span class="small">AI生成 or ストック</span></div>
</div>

<div class="small" style="margin-top:.6em">

これらは**プロジェクトに最初から入っています**。みなさんは「動かすカギ（APIキー）」を入れるだけ。<br>
細かい仕組みは覚えなくてOK。「こういう部品が連携してるんだな」で十分。

</div>

---

## カギ（APIキー）とは

<span class="term">APIキー</span><span class="gloss">外部サービスを使うための“合言葉”。サービスごとに発行される文字列</span>

- 画像を作るAI、素材サイト、音声…**外の道具を使うには合言葉が要る**
- もらった合言葉を **`.env`（環境設定ファイル）** に貼り付けておく
- 一度入れれば、あとはClaudeが自動で使ってくれる

<div class="warn">

**合言葉＝あなたの財布**。人に見せない・SNSに貼らない・GitHubに上げない。<br>
（`.env` は最初から「アップロード除外」設定済み）

</div>

---

## 今日そろえるカギ（用途別）

<div class="cols">
<div class="col">

### 🎨 画像生成
<span class="term">GEMINI_API_KEY</span>
<a href="https://ai.google.dev/">Gemini 2.5 Flash Image</a>（通称 **nanobanana**）<br>
<span class="small">①静止画ショートで使用。取得：<a href="https://aistudio.google.com/apikey">aistudio.google.com/apikey</a></span>

</div>
<div class="col">

### 🎞️ 動画素材
<a href="https://www.pexels.com/"><span class="term">Pexels</span></a> / <a href="https://pixabay.com/"><span class="term">Pixabay</span></a>
無料のストック動画API<br>
<span class="small">②素材ショートで使用。<a href="https://elements.envato.com/">Envato</a>は有料で高品質</span>

</div>
<div class="col">

### 🗣️ 音声
<a href="https://huggingface.co/Aratako/Irodori-TTS-500M-v2"><span class="term">IrodoriTTS</span></a>
ローカルで動くナレーション生成<br>
<span class="small">無料・回数制限なし。キー不要、起動するだけ</span>

</div>
</div>

<div class="small" style="margin-top:.5em">

※ 切り抜き（③）では文字起こしに **OpenAIのキー** を使います。後ほど。投稿（YouTube連携）は今日は任意。

</div>

---

## IrodoriTTS（ナレーション音声）

<a href="https://huggingface.co/Aratako/Irodori-TTS-500M-v2"><span class="term">IrodoriTTS</span></a><span class="gloss">文章を“しゃべり声”に変える、手元で動く音声エンジン</span>

- **無料・回数制限なし**（自分のPCの中で動く）
- 声の雰囲気を **言葉で指定**できる<br><span class="small">例：「明るく聞き取りやすい男性の語り口で、好奇心と驚きを込めて」</span>
- **参照音声**を使うと、動画ごとに声がブレない（同じ声で統一）
- 読み間違いは、台本のひらがなを直せば直る<span class="small">（例：後の世→のちの世）</span>

<div class="do">

使う前に一度だけ「起動」しておけばOK。あとはClaudeが各セリフを自動で音声化します。

</div>

---

## 準備チェックリスト

| やること | 今日やる？ |
|---|---|
| Claude Code が動く（プロジェクトを開く） | ✅ 全員 |
| `.env` に **GEMINI_API_KEY** を貼る | ✅ ①で使う |
| Pexels/Pixabay のキー（任意・無料） | ◯ ②で使う |
| IrodoriTTS を起動 | ✅ ①②で使う |
| OpenAI キー | ◯ ③切り抜きで使う |
| YouTube連携（OAuth） | △ 投稿したい人だけ |

<div class="small">

詰まっても大丈夫。**カギが1つ入れば①は動きます。**まず①を全員で完走しましょう。

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">共通の地図</span>

# ショート動画が“できるまで”
### 〜どの作り方も、流れは同じ〜

---

## 4工程はどの型でも同じ

<div class="diagram">
  <div class="box"><b>①台本</b>何を話すか<span class="small">構成・ナレーション文</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>②素材</b>絵・映像<span class="small">AI生成 / ストック / 元動画</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>③音声</b>ナレーション<span class="small">IrodoriTTS</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>④合成</b>1本の動画に<span class="small">Remotion / ffmpeg</span></div>
</div>

<div class="do" style="margin-top:.6em">

3つの“型”の違いは、**②素材をどこから持ってくるか**だけ。<br>
①AIで描く ／ ②ストックから借りる ／ ③長い動画から切り出す。台本・音声・合成は共通。

</div>

---

## Remotion（リモーション）とは

<a href="https://www.remotion.dev/"><span class="term">Remotion</span></a><span class="gloss">“コードで動画を組み立てる”仕組み。編集ソフトの代わり</span>

- タイムラインを手で並べる代わりに、**設定（テキスト）から動画を生成**
- 同じ型で**量産**できる・**やり直しが一瞬**（数字を変えて作り直すだけ）
- 字幕・アイコン・ズーム・テロップが**自動でそろう**

<div class="do">

みなさんがRemotionのコードを書くことはありません。**Claudeが書いて動かします。**<br>
「编集ソフトを自動操作してくれる人がいる」くらいの感覚でOK。

</div>

---

## 今日つくる“3つの型”

<div class="cols">
<div class="col">

### ① 静止画ショート
AIイラスト＋ナレーション<br>
<span class="small">Gemini nanobanana で絵を生成</span><br>
<span class="pill">アニメ調・偉人伝・雑学</span>

</div>
<div class="col">

### ② 素材ショート
ストック動画＋ナレーション<br>
<span class="small">Pexels/Pixabay/Envato から映像</span><br>
<span class="pill">解説・TOP5・ニュース</span>

</div>
<div class="col">

### ③ 切り抜きショート
長い動画から名場面<br>
<span class="small">文字起こし→いいとこ抽出→字幕</span><br>
<span class="pill">対談・講義・Q&A</span>

</div>
</div>

<br>

> どれも「**Skillを呼ぶ → 構成を確認 → 生成 → 自分の目でチェック**」という同じリズム。

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">HANDS-ON 1</span>

# 静止画ショート
### AIイラスト＋ナレーションで1本

---

## ①の仕組み

<div class="diagram">
  <div class="box"><b>構成案</b>6コマの台本<span class="small">Claudeが提案</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>画像生成</b>nanobanana<span class="small">1コマ1枚・縦型</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>音声</b>IrodoriTTS<span class="small">コマごとに音声</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>合成</b>字幕＋BGM<span class="small">9:16 の short.mp4</span></div>
</div>

<div class="small" style="margin-top:.5em">

使うSkill：<span class="term">youtube-shorts</span>（アニメ調・静止画）。「アニメ調で作って」と言うと呼ばれます。<br>
画像1枚あたり数円。6枚で十数円ほど。

</div>

---

## ①の進め方（実演しながら）

1. Claudeに**テーマを伝える**（型は「アニメ調・静止画で」）
2. Claudeが**構成案（コマ＋ナレーション）**を出す → ここで直す
3. 「OK」と言うと、**画像→音声→合成**まで自動で進む
4. 出てきた **`short.mp4`（縦型）を自分の目で確認**
5. 直したいコマだけ「3番の絵をこう変えて」と頼む

<div class="do">

頼み方の例（コピペOK）：<br>
「<strong>アニメ調の静止画ショート</strong>を作りたい。テーマは『スティーブ・ジョブズが風呂に入らなかった話』。まず6コマの構成とナレーションを提案して。」

</div>

---

## ①のチェックと直し方

- **構成の段階で直すのが一番ラク**（絵を作る前に台本を固める）
- 絵が気に入らない → 「3番だけ作り直して。もっと夜の雰囲気で」
- 声が硬い → 「ナレーションをもっと明るい語り口に」
- 読み間違い → 台本のその語を**ひらがな**に直す

<div class="warn small">

注意：実在の人物・ブランドのAI画像は**“そっくり”を避け、雰囲気で**。投稿時は各プラットフォームのルールも確認。

</div>

---

## ①の実例（クリックで再生）

<div class="gallery">
  <a href="https://youtube.com/shorts/LZBgDaeRwcU">
    <img src="https://img.youtube.com/vi/LZBgDaeRwcU/hqdefault.jpg" alt="1990円フリースで社会現象を起こした男">
    <span class="cap">1990円フリースで社会現象を起こした男</span>
    <span class="views">▶ 8,832 回</span>
  </a>
  <a href="https://youtube.com/shorts/BfcNnLQDvv0">
    <img src="https://img.youtube.com/vi/BfcNnLQDvv0/hqdefault.jpg" alt="刑務所で1000冊読んだ男">
    <span class="cap">刑務所で1000冊読んだ男</span>
    <span class="views">▶ 5,198 回</span>
  </a>
  <a href="https://youtube.com/shorts/AdqXXJzcSN4">
    <img src="https://img.youtube.com/vi/AdqXXJzcSN4/hqdefault.jpg" alt="カモノハシは生物学の常識を全部破る動物">
    <span class="cap">カモノハシは、生物学の常識を全部破る動物</span>
    <span class="views">▶ 5,104 回</span>
  </a>
</div>

<div class="small" style="margin-top:.5em">

アニメ調の静止画＋ナレーション。出典：<a href="https://github.com/PeterTakahashi/claude-code-gen-shorts">claude-code-gen-shorts</a>

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">HANDS-ON 2</span>

# 素材ショート
### ストック動画＋ナレーションで1本

---

## ②の仕組み

<div class="diagram">
  <div class="box"><b>構成案</b>シーン/順位<span class="small">解説 or TOP5</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>素材取得</b>Pexels等<span class="small">英語キーワードで検索</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>音声</b>IrodoriTTS<span class="small">シーンごと</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>合成</b>Remotion<span class="small">字幕・アイコン・テロップ</span></div>
</div>

<div class="small" style="margin-top:.5em">

使うSkill：<span class="term">stock-video-shorts</span>（このリポジトリの**おすすめ既定**）。2つの型：<br>
<b>concept-explainer</b>（1テーマ解説）と <b>remotion-toplist</b>（TOP5ランキング）。

</div>

---

## ②の進め方（実演しながら）

1. Claudeに**テーマ＋型**を伝える（解説 or TOP5）
2. Claudeが**シーン構成・ナレーション・検索キーワード**を提案
3. 「OK」→ **ストック動画を自動取得→音声→Remotionで合成**
4. 出てきた **縦型 `short.mp4` を確認**
5. 「3位の映像が地味」→ 検索キーワードを変えて差し替え

<div class="do">

頼み方の例（コピペOK）：<br>
「<strong>ストック動画で TOP5 ショート</strong>を作って。テーマは『世界一大きい動物 TOP5』。まず構成案（各順位の名前・数値・ナレーション・映像の検索ワード）を出して。」

</div>

---

## ②の強み：著作権と量産

- 素材は**正規のストックサービス**から取得 → 商用利用の見通しが立てやすい
- コストが**ほぼ定額**（無料API or 月額）→ 本数を増やしても安い
- 同じ型で**横展開しやすい**（TOP5を別テーマで量産）

<div class="warn">

ただし**ライセンスは型ごと・素材ごと**に違う。<a href="https://www.pexels.com/">Pexels</a>/<a href="https://pixabay.com/">Pixabay</a>は寛容だが、**最終確認は人間**。<br>
特に**収益化・商用**で使うなら、各サービスの利用規約をその都度チェック。

</div>

---

## ②の実例（クリックで再生）

<div class="gallery">
  <a href="https://youtube.com/shorts/Xzgp2CSDewI">
    <img src="https://img.youtube.com/vi/Xzgp2CSDewI/hqdefault.jpg" alt="外国人が驚く日本の技術 TOP5">
    <span class="cap">外国人が驚く日本の技術 TOP5</span>
    <span class="views">▶ 6,657 回</span>
  </a>
  <a href="https://youtube.com/shorts/p8Scy0yxVX8">
    <img src="https://img.youtube.com/vi/p8Scy0yxVX8/hqdefault.jpg" alt="毒が強い動物 TOP5">
    <span class="cap">毒が強い動物 TOP5、1位はハコクラゲ</span>
    <span class="views">▶ 4,506 回</span>
  </a>
  <a href="https://youtube.com/shorts/Y6c2VfXo9P4">
    <img src="https://img.youtube.com/vi/Y6c2VfXo9P4/hqdefault.jpg" alt="世界一大きい動物 TOP5">
    <span class="cap">世界一大きい動物 TOP5（さっきの例）</span>
    <span class="views">▶ 3,469 回</span>
  </a>
</div>

<div class="small" style="margin-top:.5em">

ストック実写＋アイコン＋字幕アニメ。出典：<a href="https://github.com/PeterTakahashi/claude-code-gen-shorts">claude-code-gen-shorts</a>

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">HANDS-ON 3</span>

# 切り抜きショート
### 長い動画から“名場面”を縦型に

---

## ③の仕組み（ここが面白い）

<div class="diagram">
  <div class="box"><b>元動画</b>長尺をDL<span class="small">YouTube URL等</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>文字起こし</b><a href="https://github.com/openai/whisper">Whisper</a><span class="small">秒単位の字幕データ</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>★名場面選び</b>Claude本人<span class="small">40〜60秒を選ぶ</span></div>
  <div class="arrow">→</div>
  <div class="box"><b>合成</b>顔寄せ＋字幕<span class="small">9:16の short.mp4</span></div>
</div>

<div class="do" style="margin-top:.5em">

ポイント：**“バズりスコア”のような自動採点ではない。**<br>
Claudeが文字起こしを読んで、「最初の2秒でフックがある／話が完結している」という基準で**理由を説明しながら**選ぶ。

</div>

---

## ③の進め方（実演しながら）

1. **元動画のURL**をClaudeに渡す（対談・講義・Q&Aが向く）
2. Claudeが**文字起こし**して、**切り抜き候補（40〜60秒）**を提案<br><span class="small">「ここが効く理由」も一緒に説明してくれる</span>
3. 採用するものを選ぶ → **縦型・顔寄せ・字幕入り**で書き出し
4. **`short.mp4` を確認**してから公開判断

<div class="do">

頼み方の例（コピペOK）：<br>
「この動画 <code>https://youtu.be/…</code> から、**40〜60秒の切り抜きショート**を3本作りたい。文字起こしして、**フックの強い場面**を理由つきで提案して。」

</div>

---

## ③のうれしい自動処理

- **カラオケ字幕**：今しゃべっている言葉が黄色くハイライト
- **顔追従＋ズーム**：話者の顔を中央に寄せて縦型にトリミング
- **間（ま）のカット**：無音や「えーと・あの」を自動で詰められる
- **結論先出し**：オチを冒頭に持ってくる構成も指定できる

<div class="warn small">

権利の大前提：**他人の動画を切り抜くには許諾が必要**。自分の動画、または許可・契約のある素材で。<br>
出力は最初**非公開**で書き出し → 確認してから公開、が安全。

</div>

---

## ③の実例（クリックで再生）

<div class="gallery">
  <a href="https://youtube.com/shorts/V6Ji4VochMM">
    <img src="https://img.youtube.com/vi/V6Ji4VochMM/hqdefault.jpg" alt="ひろゆき AIでエンジニアは失業しない">
    <span class="cap">ひろゆき「AIでエンジニアは失業しません」</span>
    <span class="views">▶ 5,623 回</span>
  </a>
  <a href="https://youtube.com/shorts/2PeL7StRkhM">
    <img src="https://img.youtube.com/vi/2PeL7StRkhM/hqdefault.jpg" alt="ひろゆき 子供のゲーム課金">
    <span class="cap">ひろゆき「子供のゲーム課金、親はこうしろ」</span>
    <span class="views">▶ 4,452 回</span>
  </a>
  <a href="https://youtube.com/shorts/hsiryTT3U-s">
    <img src="https://img.youtube.com/vi/hsiryTT3U-s/hqdefault.jpg" alt="ひろゆき 少子化問題の正体">
    <span class="cap">ひろゆき「今の少子化問題の正体」</span>
    <span class="views">▶ 3,838 回</span>
  </a>
</div>

<div class="small" style="margin-top:.5em">

長い対談から名場面を縦型＋字幕に。出典：<a href="https://github.com/PeterTakahashi/claude-code-clip-video">claude-code-clip-video</a>

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">BONUS</span>

# ブラウザ自動化
### AIに“ブラウザを操作”してもらう

---

## ブラウザ自動化とは

<div class="split sm">
<div class="t">

<span class="term">Agent browser</span><span class="gloss">AIが人の代わりにブラウザを開いて操作する仕組み</span>

- 画面を見て**クリック・入力・スクロール・スクショ**ができる
- Claude Codeに**ブラウザの“手”を足す**イメージ（MCPの一種）
- 動画制作の前後の**面倒な手作業**を任せられる

</div>
<img src="img/mcp.png" alt="ブラウザを自動操作するAIのイラスト">
</div>

<div class="small">

代表例：Claude in Chrome（拡張）や Playwright MCP。「このサイトを開いて〜して」と頼むだけ。

</div>

---

## 動画制作での使い道

<div class="cols">
<div class="col">

### 🔎 ネタ・トレンド集め
急上昇やコメントを**一覧化**<br>
<span class="small">「このページの上位10件を表に」</span>

</div>
<div class="col">

### 🖼️ 素材さがし
素材サイトを横断して**候補を収集**<br>
<span class="small">「条件に合う動画を10本リスト」</span>

</div>
<div class="col">

### ⬆️ 投稿まわりの下ごしらえ
タイトル・説明文の**下書き入力**<br>
<span class="small">最終送信は人がチェック</span>

</div>
</div>

<br>

<div class="warn small">

マナー：**少量・学習目的**で。相手サイトの規約・回数制限に配慮（大量取得しない）。自動“送信・投稿”は事故のもと → **下書きまで＝人が最後に確認**が安全。

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

<span class="eyebrow">WRAP-UP</span>

# まとめ
### 持ち帰ってほしいこと

---

## 今日の3つの型・おさらい

| 型 | 素材のもと | 呼ぶSkill | 向いてる内容 |
|---|---|---|---|
| ① 静止画 | AIイラスト(nanobanana) | `youtube-shorts` | アニメ調・偉人伝・雑学 |
| ② 素材 | ストック動画(Pexels等) | `stock-video-shorts` | 解説・TOP5・ニュース |
| ③ 切り抜き | 長い元動画 | `youtube-clipper` | 対談・講義・Q&A |

<div class="do">

共通のリズムは一つ：**Skillを呼ぶ → 構成を確認 → 生成 → 自分の目でチェック → （必要なら）投稿。**

</div>

---

## いちばん大事な感覚

- **コマンドを覚える会ではない**。「やりたいことを言葉にする」会
- AIは**自走する**。だから「**止める・確認する**」がこちらの仕事
- **できた素材は必ず自分の目で**。特に**著作権・利用規約は人間が最終チェック**
- 完璧を狙わない。**まず1本出して、回しながら良くする**

<div class="do" style="font-size:1.05em">

「全部わからなくてOK。**1本できれば勝ち。**」

</div>

---

## 持ち帰り・次の一歩

- 今日作った1本を、**自分のチャンネルのテーマ**で作り直してみる
- うまくいった**頼み方（プロンプト）をメモ**して使い回す
- 詰まったら**復習用の記事（index.html）**を見返す<span class="small">（このスライドの記事版）</span>

<div class="do">

質問タイム 🙋<br>
「自分のチャンネルだとどの型が合う？」も、その場で一緒に考えましょう。

</div>

---

<!-- _class: title -->
<!-- _paginate: false -->

<span class="eyebrow">THANK YOU</span>

# 今日はおつかれさまでした

## あとは、手を動かした分だけ慣れていきます

<span class="small" style="color:#cdd6dd">復習はワークブック（docs/index.html）へ</span>
