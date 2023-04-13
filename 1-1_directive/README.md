# 1-1_directive

## データバインディングのディレクティブ

### ディレクティブとは

|ディレクティブ|役割|
|----|----|
|v-bind|データバインディング|
|v-on|イベント処理|
|v-model|双方向データバインディング|
|v-html|HTML文字列表示|
|v-pre|静的コンテンツ表示|
|v-once|データバインディングを初回のみに制限|
|v-clock|マスタッシュ構文の非表示|
|v-if|条件分岐|
|v-show|表示／非表示の制御|
|v-for|ループ処理|

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
    1) Run `Extensions: Show Built-in Extensions` from VSCode's command palette
    2) Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

### NOTES:

* 本サンプル内ではスタイルシート（CSS）の拡張メタ言語を使用しています。そのため Vue のデフォルトのプロジェクト作成の他に以下のパッケージをインストールしています。

    * sass-loader
    * sass
    * fibers

* Vueプロジェクトで外部にそのまま公開されるのは public フォルダの中に置かれたファイルであるため、本サンプル内で使用される assets 内のファイルは public フォルダ内に予め用意しています。