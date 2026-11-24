# 読書記録アプリ紹介動画

読書記録アプリの画面とイラストを使った、53秒・1920×1080・30 fpsの紹介動画プロジェクトです。完成版は1,590映像フレームと音声トラックを含みます。アプリ本体のソースコードは含みません。

完成版は`読書記録アプリ_紹介動画.mp4`です。構成はオープニング0～5秒、ホーム5～11秒、機能紹介11～40.5秒、全件一覧とエンドカード40.5～53秒です。エンドカードは45.6秒から全件一覧に重なって現れます。

## 使用技術

- HyperFrames（HTML・CSSによる動画構成とMP4書き出し）
- GSAP 3.15.0（シーン内のアニメーション）

## セットアップと起動

Node.jsとnpmを用意し、リポジトリのルートで実行します。初回は`npx`が`package.json`で指定されたHyperFrames 0.9.84を取得します。

```bash
npm run dev
```

ローカルプレビューが起動します。終了するときは`Ctrl+C`を押します。

## 主な構成

| パス | 内容 |
| --- | --- |
| `index.html` | 全4シーンの構成と再生時間 |
| `compositions/` | オープニング、ホーム、機能紹介、エンディングの各シーン |
| `assets/screens/` | アプリ画面の画像と全件一覧の録画 |
| `assets/illustrations/` | 背景と装飾イラスト |
| `assets/audio/` | BGM音源 |
| `assets/fonts/` | Zen Old Minchoのフォントとライセンス文書 |
| `renders/` | 書き出した動画 |

現行の全件一覧には`assets/screens/all-books-scroll-v2.mp4`を使用します。旧録画や別案の画面素材は編集履歴として保持しています。

## 動画の書き出し

```bash
npm run check
npm run render
```

`check`で構成と表示を検証し、`render`でMP4を書き出します。
ルート構成は`index.html`にあり、BGMは`assets/audio/hiyoko-no-bouken.mp3`を0～53秒に配置しています。書き出し済みの完成版MP4を再生成するときは、上書きせず別名で保存して比較してください。

## 素材とライセンス

- 装飾イラストと書籍の表紙画像：生成AIで制作しました。
- アプリ画面：自作アプリを撮影しました。表示されるデモデータは自分で登録したものです。
- フォント：見出しにZen Old Mincho（Regular・SemiBold）、本文にNoto Sans JPを使用しています。どちらもSIL Open Font License 1.1です。Zen Old Minchoの実ファイルと[ライセンス文書](assets/fonts/OFL.txt)は`assets/fonts/`に収録しています（[Noto Sans JPのライセンス](https://github.com/google/fonts/blob/main/ofl/notosansjp/OFL.txt)）。
- BGM：[BGMer「ひよこの冒険」](https://bgmer.net/music/372/)（[利用規約](https://bgmer.net/terms/)）。個人・商用利用可、クレジット表記は任意です。
