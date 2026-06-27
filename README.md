# Claude Codeでショート動画をつくる — 勉強会教材

動画制作会社のクリエイター（非エンジニア）向け、約3時間のハンズオン勉強会の教材一式です。
Claude Code に頼んで、ショート動画（縦型 9:16）を**3つの型**で1本ずつ作る体験をします。

| 型 | 素材のもと | 呼ぶSkill | 向いてる内容 |
|---|---|---|---|
| ① 静止画ショート | AIイラスト（Gemini nanobanana） | `youtube-shorts` | アニメ調・偉人伝・雑学 |
| ② 素材ショート | ストック動画（Pexels/Pixabay/Envato） | `stock-video-shorts` | 解説・TOP5・ニュース |
| ③ 切り抜きショート | 長い元動画 | `youtube-clipper` | 対談・講義・Q&A |

加えて、Claude Code の基礎概念（LLM / Context window / Agentic loop / MCP / Skills / Agent）と、ブラウザ自動化（Agent browser）も扱います。

## 中身

- **`slide/slides.md`** … 当日のスライド本体（Marp / 日本語）。`slide/slides.html` がレンダリング済み。
- **`docs/index.html`** … 記事版ワークブック。**この記事だけ見ても自分のペースで進められます**（遅刻・復習用）。コピペ用プロンプト集と用語ミニ辞典つき。

## 使い方

スライドをブラウザで開く：

```
open slide/slides.html      # macOS
```

スライドを編集後に再生成（PDF / PPTX も可）：

```
npx --yes @marp-team/marp-cli@latest slide/slides.md -o slide/slides.html --no-stdin
npx --yes @marp-team/marp-cli@latest slide/slides.md -o slide/slides.pdf  --no-stdin
```

記事版を開く：

```
open docs/index.html
```

## 元ネタ（参照リポジトリ）

- ①② … [`claude-code-gen-shorts`](https://github.com/PeterTakahashi/claude-code-gen-shorts)（Remotion + Gemini nanobanana / Pixabay・Envato + IrodoriTTS）
- ③ … [`claude-code-clip-video`](https://github.com/PeterTakahashi/claude-code-clip-video)（yt-dlp + Whisper + Remotion/ffmpeg）

> スタンス：**全部わからなくてOK。1本できれば勝ち。**
