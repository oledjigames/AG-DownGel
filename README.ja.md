PyQt6 で構築されたクロスプラットフォーム GUI ダウンローダー。タグで GelBooru.com から画像、GIF、動画を検索・一括ダウンロード。フィルタリング、AI 除外、整理保存をサポート。

## 機能
- **タグ検索**: スペース区切りのタグ入力（例: `catgirl solo`）；GelBooru 構文（`rating:explicit` など）対応。
- **ファイルフィルタ**: 画像（.jpg、.png など）、GIF、動画（.mp4、.webm）を選択；サブフォルダ（`images/`、`GIF/`、`videos/`）に整理。
- **AI 除外**: チェックボックスで `-ai-generated` を追加し AI コンテンツを除外。
- **API サポート**: オプションの User ID/API Key で制限向上（[GelBooru アカウント](https://gelbooru.com/index.php?page=account&s=options) から取得）。
- **ローカライズ**: 英語（デフォルト）、ロシア語、中国語、日本語；`locales/*.json` で拡張。
- **ダウンロード**: `downloads/[タグ整理]/` に保存。
- **進捗とエラー**: リアルタイムステータス；ページネーション時は不確定進捗。

## インストール
1. Python 3.10+ を確認し依存をインストール:
2. `pip install pyqt6 requests`
3. 2. 実行: `python main.py`（スクリプト名変更時）。
3. 自動作成フォルダ: `downloads/`（出力）と `locales/`（翻訳）。

## 使用方法
1. ドロップダウンから言語選択（上部）。
2. 検索フィールドにタグ入力（例: `brazilian_miku hatsune_miku feet`）。
3. 「AIなし」をチェックで AI 生成除外。
4. ファイルタイプ選択。
5. User ID と API Key 入力。
6. 「すべてダウンロード」クリック – ファイルは `downloads/[タグ]/` に保存。
![alt text](https://github.com/Semiror78/AG-DownGel/blob/main/api.png?raw=true)


## タグ例
`guide.txt` より:

**Kasane_teto -hatsune_miku rating:explicit**  
(teto を miku なしでダウンロード、18+ コンテンツ含む)

**レーティングオプション:**  
- `rating:explicit` (NSFW)  
- `rating:questionable` (境界)  
- `rating:sensitive` (成熟)  
- `rating:general` (安全)

## トラブルシューティング
- **0 投稿？** 関連タグ追加（例: `brazilian_miku` に `hatsune_miku`）；GelBooru [DAPI ドキュメント](https://gelbooru.com/index.php?page=help&topic=dapi) を確認。
- **レート制限:** API Key で >100 結果/ページ。
- **カスタム言語:** `locales/[lang].json` を追加、キー `en.json` に一致。

## ライセンス
MIT ライセンス – 自由に使用/修正。
