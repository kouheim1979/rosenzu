# Rosenzu Offline

主要都市の地下鉄・都市鉄道・路面電車・市内交通の路線図を、ユーザー自身が取得したPDF/画像/SVGとして端末内に保存し、オフライン閲覧するための個人利用向けPWAです。

## 目的

- 公式路線図のPDF・PNG・JPG・SVGをアプリに同梱しない
- 公式サイトからの自動スクレイピングを行わない
- ユーザーが自分で取得した路線図ファイルを手動登録して閲覧する
- iPhone/Android/PCのブラウザで使えるHTML/PWA構成にする

## 使い方

1. GitHub Pagesでこのリポジトリを公開する
2. iPhoneのSafariで公開URLを開く
3. 共有ボタンから「ホーム画面に追加」する
4. 都市を選ぶ
5. 公式ページURLを自分で登録する
6. 取得済みのPDF/PNG/JPG/SVG路線図を「路線図ファイルを追加」から登録する
7. 登録済みファイルはIndexedDBに保存され、オフラインでも閲覧できます

## GitHub Pages設定

GitHubのリポジトリ画面で以下を設定します。

- Settings
- Pages
- Source: Deploy from a branch
- Branch: main
- Folder: /root
- Save

公開URLは通常、以下の形式になります。

```text
https://kouheim1979.github.io/rosenzu/
```

## 注意

- 公式路線図の著作権は各交通事業者・自治体等にあります。
- このアプリは個人利用を想定しています。
- 配布する場合は、各路線図・データ・ロゴ等の利用規約とライセンス確認が必要です。
- GTFS/GTFS-JPは駅・路線・時刻表データには使えますが、公式デザイン済み路線図そのものではありません。

## 構成

- `index.html`: アプリ本体
- `manifest.webmanifest`: PWA設定
- `sw.js`: オフライン用サービスワーカー
- `.nojekyll`: GitHub Pages用

## MVP機能

- 都市一覧
- 国別表示
- 都市名検索
- お気に入り
- 都市詳細
- 公式ページURL・メモ管理
- PDF/PNG/JPG/SVG手動登録
- IndexedDB保存
- オフライン閲覧
- 画像/SVGのピンチズーム・ドラッグ・明るさ調整
- PDFのブラウザ内表示
- JSONバックアップ/復元
- 都市別キャッシュ削除
