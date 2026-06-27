# CLAUDE.md — 「Claude Codeでショート動画」勉強会 教材プロジェクト

> このファイルはプロジェクトの文脈です。**編集を始める前に必ず読み、`slide/slides.md` と `docs/index.html` の現状を確認してから**作業すること。最後の「▼ 今回の依頼」に従って続きを修正する。

---

## 0. これは何か

- **動画制作会社の動画クリエイター（非エンジニア）向け、約3時間の対面ハンズオン勉強会**の教材一式。
- 目的は「エンジニアにする」ことではなく、**Claude Code に頼んでショート動画を“動く形”で1本書き出す**体験をしてもらうこと。
- 主催・進行は Seiya。

### 当日のゴール（参加者の成果物）
**自分の手で、縦型（9:16）のショート動画 `short.mp4` を実際に1本書き出すところまで。** 作り方の“3つの型”を手を動かして体験する。投稿（YouTube連携）は希望者のみ。

---

## 1. 教え方の方針（ここをブラさない）

- 用語は「前もって全部」でも「一切なし」でもなく、**“使う直前に1個ずつ”**。1語ごとに一言の言い換え＋たとえを添える。
- スライドではこれを **「用語ピル＋言い換え」**（`.term` / `.gloss`）で統一表現。新しい用語もこの形で。
- トーン：「**全部わからなくてOK。1本できれば勝ち**」。エラーは失敗ではなく“会話のきっかけ”。
- **非エンジニア向けなので「コマンドを打つ」より「自然文で頼む→Claudeが実行」を軸にする。** スライドにPythonのコマンドを並べない（間違いの元 & 趣旨と違う）。コピペするのは“頼み方（プロンプト）”。
- 著作権・利用規約は必ず「人間が最終チェック」と添える（素材・切り抜きの両方）。

---

## 2. 教える内容（3つの型 ＋ 概念 ＋ ブラウザ自動化）

**概念パート（最低限の地図）**
- LLM / Claude / Claude Code、Context window、Agentic loop、MCP、Skills、Agent/サブエージェント、得意・苦手。

**準備**
- APIキー（合言葉）の説明、`.env`、IrodoriTTS の起動。用途別キー：①GEMINI_API_KEY、②Pexels/Pixabay（任意）、③OPENAI_API_KEY、投稿はYouTube OAuth（任意）。

**ハンズオン①：静止画ショート** — `youtube-shorts` Skill（Gemini nanobanana で画像→ IrodoriTTS → ffmpeg合成）。アニメ調・偉人伝・雑学向け。
**ハンズオン②：素材ショート** — `stock-video-shorts` Skill（Pexels/Pixabay/Envato → Remotion → IrodoriTTS）。型は concept-explainer / remotion-toplist。解説・TOP5・ニュース向け。**このリポジトリの推奨既定**。
**ハンズオン③：切り抜きショート** — 別リポジトリ `claude-code-clip-video` の `youtube-clipper` Skill（yt-dlp → Whisper文字起こし → ★Claude本人が名場面選定 → 顔寄せ＋カラオケ字幕で9:16書き出し）。派生 `clipper-explainer`/`clipper-qa`。対談・講義・Q&A向け。
**おまけ：ブラウザ自動化** — Agent browser / Claude in Chrome / Playwright MCP。ネタ集め・素材さがし・投稿の下書き。下書きまで＝人が最終確認。

### 素材リポジトリ（教材の元ネタ・参照のみ）
- `/Users/apple/dev/claude-code/claude-code-gen-shorts`（①②。Skill: `youtube-shorts`, `stock-video-shorts`）
- `https://github.com/PeterTakahashi/claude-code-clip-video`（③。Skill: `youtube-clipper` 他）
- スタイル参照元：`/Users/apple/dev/claude-code/claude-code-tutorial-for-non-engineer`

---

## 3. 当日の流れ（3時間・目安）

| 時間 | 内容 |
|---|---|
| 0:00–0:15 | 自己紹介・今日の流れ・完成形デモ |
| 0:15–0:45 | 最低限の地図（概念） |
| 0:45–1:00 | 準備（APIキー・IrodoriTTS起動） |
| 1:00–1:45 | ハンズオン①：静止画ショート（全員でしっかり） |
| 1:45–2:15 | ハンズオン②：素材ショート |
| 2:15–2:45 | ハンズオン③：切り抜きショート |
| 2:45–3:00 | ブラウザ自動化・まとめ・質問 |

**正直な注意：3時間に全部“完璧に”は入らない。①を全員で完走 →②③は要点デモ＋各自トライ。①最優先。**

---

## 4. 成果物（ファイル）

```
.
├── CLAUDE.md                  # このファイル
├── README.md
├── slide/
│   ├── slides.md              # Marpスライド本体（日本語）
│   ├── slides.html            # レンダリング済み（marpで再生成可）
│   └── img/                   # 概念イラスト（llm/mcp/skills/agentic_loop）
└── docs/
    ├── index.html             # 記事版ワークブック（自習・復習用）
    └── img/                   # 記事内で使う画像（llm/mcp）
```

---

## 5. デザインシステム（編集時は厳守）

`slide/slides.md` 先頭の `<style>`、および `docs/index.html` の `<style>` に定義済み。**新しい要素もこの語彙だけで組む（崩さない）。**

- 色：`--ink #1F2933` / `--paper #FAF9F6` / `--accent`（クレイ＝Claude色）`#D97757` / `--accent2`（ティール＝行動）`#2A9D8F` / `--muted #6B7280` / `--line #E7E3DC` / `--soft #F0EDE7`
- スライド種別：`section.title`（表紙）/ `section.section`（章扉・濃紺）。章扉と表紙は `<!-- _paginate: false -->`。
- 部品：`.eyebrow` / `.term`+`.gloss`（用語の基本形）/ `.do`（ティール囲み＝やること）/ `.warn`（クレイ囲み＝注意）/ `.cols`+`.col` / `.diagram`+`.box`+`.arrow` / `.small`。
- 記事側の追加部品：`.prompt`（コピペ用プロンプト枠）/ `.check`（確認チェック）/ `.step`（STEPピル）/ `.cards`+`.card` / `.toc`。
- 用語を出す基本形：`<span class="term">用語</span><span class="gloss">一言の言い換え</span>`

### Marp 書き出し / プレビュー
```
npx --yes @marp-team/marp-cli@latest slide/slides.md -o slide/slides.html --no-stdin   # HTML
npx --yes @marp-team/marp-cli@latest slide/slides.md -o slide/slides.pdf  --no-stdin   # PDF（要Chrome/Chromium）
npx --yes @marp-team/marp-cli@latest slide/slides.md -o slide/slides.pptx --no-stdin   # PowerPoint
```
※ 非対話環境でstdin待ちになる場合は `--no-stdin` を付ける。macOSに `timeout` は無い。

---

## 6. 既知の注意点（honest flags）

- 3時間に全部は**タイト**。①が主役、②③は要点デモ＋各自トライ前提。
- ①は `GEMINI_API_KEY` 必須。③は `OPENAI_API_KEY`（Whisper）必須。投稿は YouTube OAuth（任意）。
- ③の切り抜きは**他人の動画には許諾が必要**。自分の動画 or 契約済み素材で。出力はまず非公開。
- 製品/ツールの**具体手順・APIキー取得手順は最新ドキュメントで都度確認**（記憶でハードコードしない）。
- TTS は IrodoriTTS を主役に説明（リポジトリには Aivis 等の別エンジン記述もある）。ポート番号など細部はスライドに載せず、必要ならClaudeに起動を頼む案内に留める。

---

## ▼ 今回の依頼（ここに毎回書く）

<!-- 例：「slide/slides.md のハンズオン②を concept-explainer 中心に書き直して。デザインは維持」 -->

（ここに今やってほしいことを書いてください）
