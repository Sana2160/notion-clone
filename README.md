# Notion Clone (開発中)

## 📌 概要

このアプリは、React と TypeScript を用いて開発中の Notion クローンアプリです。ページの追加・編集・切り替えといった基本的なノート機能を備え、直感的なUIで複数ページの管理ができることを目指しています。

データの保存には Supabase を使用しており、リアルタイムでの読み書きやユーザーごとのページ管理を想定した構成になっています。

## 🎯 目的

- Notion風のUI/UXの再現
- Supabase によるバックエンド設計と認証の習得
- 型安全な大規模Reactアプリケーションの構築練習

## 🚧 現在の実装状況

- [x] ログインページ UI（※将来的にSupabase Authと連携予定）
- [x] サイドバー／ページ一覧 UI
- [x] ページごとのテキスト表示・選択
- [x] Supabase 経由でのページデータ読み書き
- [ ] ページ作成／削除
- [ ] 認証によるユーザー別のデータ管理
- [ ] リッチテキストエディタ機能（検討中）

## 🔧 使用技術

- **React**
- **TypeScript**
- **Supabase**
  - Database（PostgreSQL）
  - Auth（今後導入予定）
- **React Router**
- **Tailwind CSS**（スタイリング）
- **ESLint / Prettier**

## 💡 工夫した点

- Supabase の `useEffect + async` でデータをフェッチし、ページ読み込みを軽量に保つ
- React Router を使ったページ別ルーティングと動的URL管理
- Context API を使ってアプリ全体の状態を一元管理（今後 Zustand などの導入も検討）

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      ...tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      ...tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      ...tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```
