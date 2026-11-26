# INTRO MASTER

テレビの音楽クイズ番組をイメージした、個人利用向けのブラウザーアプリ。

## 起動（Windows / VS Code）

```powershell
git clone https://github.com/nakacy0919-Git/intromaster.git
cd intromaster
py -m http.server 8000 --bind 127.0.0.1
```

ブラウザーで http://localhost:8000/ を開く。すでにクローン済みの場合は main を pull する。Python がない場合は VS Code の Live Server 等を使う。YouTube の参照元識別のため file:// で直接開く方法は推奨しない。

## 機能

- オリジナル合成音の10曲デモ。架空の曲名・独自順位で、インターネット接続不要。
- 昭和・平成・令和、1970〜2020年代、発売年別、ジャンル別、全曲。
- 登録順位順のカウントダウン / ランダム、5・10・20曲設定（登録曲数が上限）。
- 1・3・5・10秒のイントロ、正解発表、指定サビ、結果画面。
- 4チームの名前と得点、司会者ショートカット、全画面表示、効果音の切替。
- 公式YouTube動画のURL、発売日、独自順位、イントロ位置とサビ位置の登録・編集・削除。プレビュー中の現在位置を取得。
- ブラウザーの localStorage に保存。JSONでバックアップ・インポート。

## YouTube の利用

YouTube IFrame Player API を使用。公式プレーヤーは常時表示し、映像やタイトル、広告、コントロールを隠さない。音源のダウンロード・抽出・保存は行わない。埋め込みが無効な動画、広告やブラウザーの自動再生制限、キーフレームによる開始位置の差があり得る。動画によってタイトルや映像で正解が見えることがある。

デモ曲は既存音源ではなく、ブラウザーで生成するオリジナル合成音。市販曲・ランキングデータの初期登録は行っていない。登録順位は利用者独自の順位。講演・イベントで実際の音楽を再生する場合は権利と利用規約を確認する。

- https://developers.google.com/youtube/iframe_api_reference
- https://developers.google.com/youtube/terms/developer-policies
- https://www.youtube.com/t/terms

## 配信

現時点では静的HTMLのみ。VercelやGitHub Pagesへのデプロイは行わない。リポジトリ自体の公開範囲はGitHubの設定で管理する。個人用の楽曲ライブラリーJSONは公開リポジトリにコミットしないこと。
