# APIテストツール（HTML版）

このツールは、HTMLとJavaScriptで構築された軽量なAPIテストツールです。Postmanなどの代替として、シンプルなUIでAPIの送信・確認が行えます。

## 特長

- **GUIによるAPIリスト表示とパラメータ入力**
- **パラメータのバリデーション（正規表現・最小長・最大長）**
- **送信ボタンの状態管理（未入力時グレー／入力完了時緑）**
- **リクエスト形式の切り替え（JSON / フォーム）**
- **レスポンスとリクエストプレビューの表示**

## 使用方法

1. `index.html` をブラウザで開きます。
2. ホスト名・アクセストークンを入力します（必要に応じて）。
3. 左からAPIを選択すると、詳細とパラメータ入力欄が表示されます。
4. 必須項目を入力すると、送信ボタンが有効化されます。
5. 「送信」ボタンを押すと、リクエストとレスポンスの結果が右側に表示されます。

## カスタマイズ

API一覧 (`apiListData`) は JavaScript 内で定義されています。必要に応じて内容を編集してください。

```js
const apiListData = [
  {
    name: "ユーザー詳細取得",
    method: "GET",
    path: "/api/users/detail",
    parameters: [
      { name: "userId", required: true, pattern: "^[a-z0-9]{4,10}$", ... }
    ]
  },
  ...
];
```

## 対応形式

- リクエスト形式：JSON または application/x-www-form-urlencoded
- パラメータ型：文字列、セレクトボックス、チェックボックス

## ライセンス

MIT License（詳細は LICENSE を参照）

このツールの初期実装・記述整理には ChatGPT および Claude.ai を活用し、最終的には人間による調整を行っています。

This project includes content assisted by AI tools (ChatGPT, Claude.ai),
with final edits and structure confirmed by a human.
