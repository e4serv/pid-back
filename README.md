# PID-Back: PIDアーカイブ検索

ウェブページのURLや、DOI・ハンドルなどの永続的識別子（PID）を入力すると、インターネットアーカイブ（Wayback Machine）に保存されたページへのリンクを表示するツールです。識別子は実際のページのURLに解決してから探すので、保存されている本体のページにたどり着けます。

ブラウザだけで動く1ファイルのHTMLで、インストールやサーバーは不要です。

## 使い方

1. `index.html` をブラウザで開きます（GitHub Pages で公開している場合は、そのURLを開きます）。
2. URLまたは識別子を、1行に1つずつ入力します。
3. 必要なら日付を指定し、「Wayback で探す」を押します。

結果として、次のリンクと保存状況が表示されます。

- 指定した日付に最も近い保存版（日付を指定した場合）
- 最新の保存版
- 保存履歴カレンダー
- 配下のURL一覧

## 対応している識別子

| 種類 | 入力例 | 解決方法 |
| --- | --- | --- |
| DOI | `10.00000/00000000`、`doi:…`、`https://doi.org/…` | doi.org の Handle API |
| ハンドル | `hdl:0000/00000000`、`https://hdl.handle.net/…` | hdl.handle.net の Handle API |
| ARK | `ark:/00000/xxxxxxxx` | n2t.net のリダイレクト |
| URN:NBN | `urn:nbn:de:…` など | 各国の解決サービスのリダイレクト |
| PURL・w3id など | 解決サービスのURL | リダイレクト |
| ORCID・ISNI・ROR・arXiv・PMID・PMCID・Wikidata・VIAF | `0000-0000-0000-0000`、`ror:…`、`arXiv:…` など | 公式ページのURLに変換 |
| NDL PID・CRID・NCID・NAID | `info:ndljp/pid/0000000`、`crid:…` など | 公式ページのURLに変換 |
| その他 | `接頭辞:ID`（identifiers.org に登録されているもの） | identifiers.org の解決API |

## 注意事項

- PIDはすべて解決できるとは限りません。その場合は識別子のURLのまま Wayback を探します。特に ARK・URN:NBN・PURL などリダイレクト型の識別子は、ブラウザの制限（CORS）により解決先を取得できないことがあります。
- 入力したURLや識別子は、解決や保存状況の確認のため、doi.org、hdl.handle.net、identifiers.org、archive.org、各識別子の解決サービスに送られます。非公開にしたいURLを調べる場合は注意してください。
- 表示用のフォントを Google Fonts から読み込んでいます。
- ページタイトルの取得には対応していません（ブラウザの制限により、多くのサイトのHTMLを読み取れないため）。

## 著作権

Copyright (c) 2026 N. Nakazono. All rights reserved.

このリポジトリにはライセンスを付けていません。著作権者の許可なく、改変・再配布することはできません。
