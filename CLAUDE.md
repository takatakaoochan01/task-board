# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 技術スタック

- React 19 + Vite 8（`@vitejs/plugin-react`）
- Lint: oxlint（`npm run lint`）
- 状態管理はReact標準の `useState` / `useEffect` のみ。外部の状態管理ライブラリは使用しない
- 永続化はブラウザの `localStorage` を使用（バックエンド・DBなし）

### コマンド

- `npm run dev` — 開発サーバー起動
- `npm run build` — 本番ビルド（`dist/` に出力）
- `npm run preview` — ビルド結果のプレビュー
- `npm run lint` — oxlintによるlint実行

## コンポーネントの命名規約

- コンポーネントファイルは `PascalCase.jsx`（例: `TaskBoard.jsx`）、1ファイル1コンポーネント
- CSSはコンポーネント単位ではなく `App.css` に集約し、クラス名は `kebab-case`（例: `.task-item`, `.delete-button`）
- 状態が完了/未完了のように見た目に影響する場合はBEM風に修飾クラスを付与する（例: `.task-item.completed`）

## デプロイ先

https://takatakaoochan01.github.io/task-board/

GitHub Actions（[.github/workflows/deploy.yml](.github/workflows/deploy.yml)）により、`main` ブランチへのpushで自動ビルド・デプロイされる。公開/非公開はGitHubリポジトリの Settings > Pages で管理する。

## Git運用ルール

- コードに変更を加えたら、その都度コミットしてGitHubにプッシュすること。変更を溜め込まず、こまめにコミット・プッシュする。
- コミットメッセージは変更内容が分かるように簡潔に書く。
- プッシュ前に `git status` / `git diff` で差分を確認し、意図しない変更が含まれていないかチェックする。
