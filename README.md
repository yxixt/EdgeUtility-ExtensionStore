# EdgeUtility Extension Store

公開用の拡張配布リポジトリです。拡張のソースコードは置かず、審査済みの署名済み `.edgeext` と署名済みfeedだけを配布します。

## 現在の状態

このリポジトリは配布場所として準備中です。まだ署名済みfeed・拡張パッケージは公開していません。署名のないプレースホルダーfeedはEdgeUtilityで検証に失敗するため、登録しません。

## 配布ルール

- パッケージとfeedはEdgeUtility本体に登録された発行者公開鍵と一致する署名で検証できること
- feedのPublisher、拡張manifest、SHA-256、runtime、要求capabilityを相互に一致させること
- パッケージはGitHub Releasesのアセットとして保管し、feedからHTTPSで参照すること
- 秘密鍵、PFX/P12、トークン、個人情報、拡張ソースコードはこの公開リポジトリに置かないこと
- 公開前に、パッケージをクリーン環境で検証し、拡張ID・バージョン・権限・ライセンスをレビューすること

## feed URL

署名済み `extension-feed.json` を追加した後に公開するRaw URLは以下の形式です。

`https://raw.githubusercontent.com/yxixt/EdgeUtility-ExtensionStore/main/extension-feed.json`

現行アプリは公開feed URLを自動読込せず、Extension Managerの「ローカル」からユーザーがfeedファイルを選ぶ方式です。URLの自動接続を追加する場合は本体側の実装変更が必要です。

feed署名鍵の利用手順が確定するまでは、拡張パッケージやfeedを公開しません。鍵はGitHubやこのリポジトリへアップロードしません。
