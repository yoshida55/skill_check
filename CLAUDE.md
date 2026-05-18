# 📋 プロジェクト概要：Mでんき住設 コーディングスキルチェック

## 🎯 課題の目的
RESTARTさんからの擬似プロジェクト課題。
実案件（Mでんき住設）のXDデザインをもとに、Webサイト全8ページをコーディングする。

---

## 📁 フォルダ構成

```
00_restartさん課題/
├ CLAUDE.md（このファイル）
├ sankou/
│  ├ URL等.md         ← 課題の指示文・XDリンク・Backlogリンク
│  ├ 仕様.md          ← 質問の下書き（古いバージョン）
│  ├ 質問.md          ← RESTARTさんへ送る質問（現在編集中）
│  └ 不安要素.md      ← チーム内の懸念事項メモ
```

---

## 📄 対象ページ（全8ページ）

| ページ名 | ファイル名 | 備考 |
|---|---|---|
| TOP | front-page.html | テンプレート提供あり |
| 会社概要 | company.html | XDアートボード名より |
| スタッフ紹介 | （XDで英語名確認） | |
| 事業内容（個人向け） | 〃 | |
| 事業内容（法人向け） | 〃 | |
| お知らせ | 〃 | |
| お問い合わせ | 〃 | |
| プライバシーポリシー | 〃 | |

※ PCデザインのアートボードに英語名が入っているので、そこからファイル名を確認する。

---

## 🗂 提供素材（リポジトリ内 template フォルダ）

```
template/
├ front-page.html（構造参考用）
├ style.css（WordPress化想定で直下に配置）
├ css/
│  └ reset.css
└ img/（使用素材一式）
```

---

## 🔗 参照リンク

- **Backlog**: https://re-start01.backlog.com/dashboard
- **PCデザイン（XD）**: https://xd.adobe.com/view/321d1719-c044-473a-b3a6-29689023338e-674e/
- **SPデザイン（XD）**: https://xd.adobe.com/view/4504c8dc-7ec6-4288-a671-b5fb70951026-1057/
- **Gitリポジトリ**: Backlog内 `skillcheck1_00●●`（番号は要確認）

---

## ⚙ 開発ルール（確定分）

- HTML・CSS・JSでまず実装（WordPressは将来対応）
- ヘッダー・フッターは各ページに同じ内容を記述（共通パーツ想定）
- 各ページごとにHTMLファイルを作成
- CSSはRESTARTのテキストの記述ルールに従う
- Gitは適切な粒度でコミット・履歴をわかりやすく保つ

---

## ❓ 未確定事項（質問.mdで確認中）

- Backlogリポジトリ番号（skillcheck1_0●●）
- RESTARTのテキスト（記述ルール）の入手方法
- ブレイクポイント・PCの最大幅/最小幅
- CSSクラス名の命名規則
- JSの実装範囲・ライブラリ（jQuery/Swiper等）使用可否
- JSファイルの共通化ルール
- チームの人数・ページ分担の割り当て方
- 質問・連絡手段（Backlogのコメント機能でOK？）
- 2週間の起点日（リポジトリ準備完了日から？）
- コミットのタイミング・メッセージ形式

---

## 👥 体制・進め方（確定次第更新）

- 担当人数：未確定（RESTARTさんに確認中）
- 分担単位：ヘッダー / フッター / 各ページ（1ページ＝1担当）
- ダブルチェック：製造担当者以外が行う

---

## 📊 Backlog 作業手順

1. 製造開始 → 親課題・作業中の課題を「処理中」に変更
2. 製造・セルフチェック完了
3. ダブルチェック（別担当者が実施）
4. 修正 → 「修正」種別の子課題として追加・製造担当者が対応

---

## 🌿 Git運用方針（2リモート・mainブランチ1本）

### リモート構成
| リモート名 | URL | 用途 |
|---|---|---|
| `restart` | RESTARTさんのGitHubリポジトリ（TortoiseGitでクローン後、自動登録） | RESTART提出用・チーム共有 |
| `origin` | git@github.com:yoshida55/skill_check.git | 自分用（会社↔自宅の同期） |

### ブランチ構成
- **mainブランチ1本のみ**で運用する

### .gitignore（必須設定）
```
sankou/
CLAUDE.md
.claude/
```
→ これにより `git add .` しても上記ファイルはどちらのリモートにも送られない

### 初期設定手順（最初の1回だけ）
1. RESTARTさんのGitURLをコピー
2. TortoiseGitでクローン（`restart` リモートが自動登録される）
3. TortoiseGit → 設定 → リモート → `origin` として自分のGitHubを追加
4. `.gitignore` に `sankou/` `CLAUDE.md` `.claude/` を記載

### 毎日のプッシュ（TortoiseGit）
```
右クリック → Push → リモート欄で送り先を選ぶ
  restart → RESTARTのリポジトリへ（提出・チーム共有）
  origin  → 自分のGitHubへ（会社↔自宅の同期）
```

### 毎朝のプル（順番厳守）
```
① git pull restart main  → チーム全員の最新を取り込む
② git pull origin main   → 自宅での作業を取り込む
```
⚠ 必ず restart → origin の順番で行うこと（逆にすると衝突しやすくなる）

### ⚠ 注意
- `sankou/` `CLAUDE.md` `.claude/` は `.gitignore` で自動除外されるためRESTARTには届かない
- `sankou/` や `CLAUDE.md` を更新した場合は手動でコピーして持ち運ぶ
- RESTARTさんのリポジトリURL確定後に `restart` リモートを正式登録する

---

## 🎯 評価ポイント

- デザインの再現力
- HTML/CSSの設計力
- Gitの使い方（履歴・運用）
- Backlogでの進捗管理
- チーム開発を意識した進め方
- 問題解決力
