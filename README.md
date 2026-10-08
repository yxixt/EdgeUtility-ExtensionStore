# EdgeUtility Extension Store

公開用の拡張配布リポジトリです。拡張のソースコードは置かず、審査済みの署名済み `.edgeext` と署名済みfeedだけを配布します。

## 現在の状態

QR Generator 1.0.0を公開しています。x64 / ARM64用の署名済み`.edgeext`はGitHub Releasesに置き、署名済み`extension-feed.json`からSHA-256付きで参照します。拡張ソースはPrivateリポジトリで管理し、この公開リポジトリには含めません。

## 配布ルール

- パッケージとfeedはEdgeUtility本体に登録された発行者公開鍵と一致する署名で検証できること
- feedのPublisher、拡張manifest、SHA-256、runtime、要求capabilityを相互に一致させること
- パッケージはGitHub Releasesのアセットとして保管し、feedからHTTPSで参照すること
- 秘密鍵、PFX/P12、トークン、個人情報、拡張ソースコードはこの公開リポジトリに置かないこと
- 公開前に、パッケージをクリーン環境で検証し、拡張ID・バージョン・権限・ライセンスをレビューすること

## feed URL

署名済みfeedのRaw URLは以下です。

`https://raw.githubusercontent.com/yxixt/EdgeUtility-ExtensionStore/main/extension-feed.json`

対応するEdgeUtilityでは、Paletteで「Extension Store」を開き、Store画面で拡張を検索できます。取得後は署名・SHA-256・manifestを検証し、権限確認とHost健康確認を経て利用を許可します。アンインストールはStore管理画面の「インストール済み」から行えます。

## 公開済み拡張

- **QR Generator 1.0.0** — URLやテキストからローカルでQRを生成し、PNG/SVGのコピー・保存に対応。要求機能は`commands`、`detail`、`forms`、`image-preview`、`clipboard.read`、`clipboard.write`、`file.save`です。

パッケージとfeedはEdgeUtilityの固定公開者証明書で署名しています。署名用秘密鍵、PFX/P12、トークン、個人情報はこの公開リポジトリやGitHub Releasesに置きません。
