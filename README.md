# 読書記録アプリ紹介動画

読書記録アプリの画面とイラストを使った、53秒・1920×1080の紹介動画プロジェクトです。アプリ本体のソースコードは含みません。

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

## 動画の書き出し

```bash
npm run check
npm run render
```

`check`で構成と表示を検証し、`render`でMP4を書き出します。

## 素材とライセンス

- フォント：Zen Old Minchoは[SIL Open Font License 1.1](assets/fonts/OFL.txt)です。
- BGM：[BGMer「ひよこの冒険」](https://bgmer.net/music/372/)（[利用規約](https://bgmer.net/terms/)）。通常のBGM利用は個人・商用とも無料で、クレジット表記は任意です。
- アプリ画面とイラスト：`assets/`に収録。これらの素材の再利用条件は、このリポジトリには明記されていません。
