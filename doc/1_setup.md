
# セットアップ

- Node.jsをインストール
- プロジェクトを作成する予定の場所まで移動

```sh
$ npm create vue@latest
✔ Project name: … <your-project-name>
✔ Add TypeScript? … No
✔ Add JSX Support? … No
✔ Add Vue Router for Single Page Application development? … No
✔ Add Pinia for state management? … No
✔ Add Vitest for Unit testing? … No
✔ Add an End-to-End Testing Solution? … No
✔ Add ESLint for code quality? … Yes
✔ Add Prettier for code formatting? … No
✔ Add Vue DevTools 7 extension for debugging? (experimental) … No

Scaffolding project in ./<your-project-name>...
Done.
```

```sh
# 作成したプロジェクトへ移動
$ cd <your-project-name>
# 依存関係をインストール
$ npm install
# 開発サーバー起動
$ npm run dev
```

アプリをプロダクション環境に出す準備ができたら、以下を実行
```sh
$ npm run build
```


