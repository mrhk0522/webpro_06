
# Webプログラミング  レポートシステム設計

## 1．仮面ライダーシステム

### システム概要
仮面ライダーの情報を管理するWebアプリケーション．
仮面ライダーの名前，登場作品，変身者，モチーフなどを登録し，一覧表示や詳細表示を行う．

### ページ遷移図

```mermaid
stateDiagram-v2
    [*] --> riders

    riders: /riders
    rider_detail: /riders/:id
    rider_add: /riders/new
    rider_edit: /riders/:id/edit
    rider_delete: 削除確認

    riders --> rider_detail: ライダーを選択
    riders --> rider_add: 新規追加
    rider_add --> riders: 登録完了
    rider_add --> riders: 戻る

    rider_detail --> riders: 一覧に戻る
    rider_detail --> rider_edit: 編集
    rider_edit --> rider_detail: 更新完了
    rider_detail --> rider_delete: 削除
    rider_delete --> riders: 削除完了
    rider_delete --> rider_detail: キャンセル
```

### スキーマ

| 項目名 | データ型 | 内容 |
|---|---|---|
| id | Number | ライダーID |
| name | String | ライダー名 |
| series | String | 登場作品 |
| user | String | 変身者 |
| motif | String | モチーフ |
| description | String | ライダーの説明 |

### 実装予定の機能
- 仮面ライダーの一覧表示
- 仮面ライダーの詳細表示
- 新しい仮面ライダーの追加
- 登録済みライダーの情報変更
- 登録済みライダーの削除

---

## 2．ジョジョスタンドシステム

### システム概要
ジョジョの奇妙な冒険に登場するスタンドの情報を管理するWebアプリケーション．
スタンド名，本体名，登場部，能力などを登録し，一覧表示や詳細表示を行う．

### ページ遷移図

```mermaid
stateDiagram-v2
    [*] --> stands

    stands: /stands
    stand_detail: /stands/:id
    stand_add: /stands/new
    stand_edit: /stands/:id/edit
    stand_delete: 削除確認

    stands --> stand_detail: スタンドを選択
    stands --> stand_add: 新規追加
    stand_add --> stands: 登録完了
    stand_add --> stands: 戻る

    stand_detail --> stands: 一覧に戻る
    stand_detail --> stand_edit: 編集
    stand_edit --> stand_detail: 更新完了
    stand_detail --> stand_delete: 削除
    stand_delete --> stands: 削除完了
    stand_delete --> stand_detail: キャンセル
```

### スキーマ

| 項目名 | データ型 | 内容 |
|---|---|---|
| id | Number | スタンドID |
| name | String | スタンド名 |
| user | String | スタンド本体名 |
| part | Number | 登場する部 |
| ability | String | スタンド能力 |
| range | String | 射程距離 |

### 実装予定の機能
- スタンドの一覧表示
- スタンドの詳細表示
- 新しいスタンドの追加
- 登録済みスタンドの情報変更
- 登録済みスタンドの削除

---

