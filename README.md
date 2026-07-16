<h1 align="center">Hi 👋</h1>

<p align="center">
  第一級陸上無線技術士に挑戦中。
</p>

---

## 📂 ソースコードが見られるプロジェクト

コードを公開している3件です。それぞれのリポジトリに、設計意図・技術的な工夫をまとめたREADMEを置いています。

| プロジェクト | 概要 | ソースコード | 公開サイト | スライド |
|---|---|---|---|---|
| **もふっと** | 保護犬猫の「推し活」プラットフォーム（Next.js / TypeScript） | [rururena6607/mofutto](https://github.com/rururena6607/mofutto) | [mofutto.vercel.app](https://mofutto.vercel.app) | [Canva](https://canva.link/mjis63bg8rc0i8c) |
| **CPR BEAT 公式サイト** | 素のHTML/CSS/JSで構築した静的サイト（Firebase Hosting） | [rururena6607/CPRBEATwebsite](https://github.com/rururena6607/CPRBEATwebsite) | [cprbeat-5150c.web.app](https://cprbeat-5150c.web.app) | — |
| **PBL-B** | 工場の稼働音を解析して塗装機の動作回数を自動カウント（Python） | [rururena6607/PBL-B](https://github.com/rururena6607/PBL-B) | — | [Canva](https://canva.link/ha6acgbabmh01le) |

---

### もふっと — ペット推し活プラットフォーム

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/mofutto)
[![Demo](https://img.shields.io/badge/デモ-mofutto.vercel.app-000000?style=flat&logo=vercel&logoColor=white)](https://mofutto.vercel.app)
[![Slides](https://img.shields.io/badge/スライド-Canva-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/mjis63bg8rc0i8c)

> **保護犬猫を「アイドルのように推せる」プラットフォーム。「寄付」ではなく「推す・贈る・応援する」体験で、一頭ずつの個性と物語を主役にする**

**主な機能**
- 推し活フィード：推せる子の一覧（推し数・性格タグ・物語）
- 子の詳細：性格まるわかりカードと物語、応援／迎えるCTA
- 4段ラダーの応援（おやつ → 継続 → 医療費 → 里親）
- おうち日記：迎えた後の成長記録を共有、迎えた子が次の「推し」に
- 応援額の使い道を透明に公開する設計思想

**使用技術**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)

---

### CPR BEAT 公式サイト

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/CPRHomePage)
[![Site](https://img.shields.io/badge/公開サイト-cprbeat--5150c.web.app-FFCA28?style=flat&logo=firebase&logoColor=black)](https://cprbeat-5150c.web.app)

> **CPR訓練システム「CPR BEAT」のコーポレートサイト。ライブラリを使わず素のHTML/CSS/JavaScriptで構築し、Firebase Hostingで配信**

**担当**

設計・実装・デプロイまで単独で開発。

**技術的なポイント**
- トップページ初回訪問時に、Canvasで心電図の波形をリアルタイム描画するスプラッシュ演出（波形のピークとハートの拍動を同期、Retina対応で2倍解像度描画）
- `sessionStorage` で再訪問時はスプラッシュをスキップ。加えて最長3秒のフェイルセーフを置き、描画性能や画面幅によってコンテンツ到達が妨げられないよう保証
- 画像をWebP・動画をWebM（VP9 + Opus）に統一。変換はffmpegを呼ぶ自作の一括スクリプトで実施
- 静的アセットへの長期キャッシュヘッダ付与、`IntersectionObserver` によるスクロール連動アニメーション
- 料金プランはPCではグリッド、モバイルでは横スクロール＋中央カード自動アクティブ化に切り替わる比較UI

**使用技術**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase_Hosting-FFCA28?style=flat&logo=firebase&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

---

### PBL-B — エアレスポンプ稼働音声解析システム

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/PBL-B)
[![Slides](https://img.shields.io/badge/スライド-Canva-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/ha6acgbabmh01le)

> **防爆室内にセンサーを設置できない工場環境において、室外から録音した音声データを解析し、塗装機の稼働回数を自動カウントするデスクトップ解析ツール**（大学PBL授業における企業連携プロジェクト）

**主な機能**
- WAVファイルの一括バッチ解析・稼働イベント自動検出
- 15〜20kHz帯域パスフィルタによる金属音ノイズ除去
- クレストファクタを用いたファイル事前スクリーニング
- 動的閾値調整（局所ノイズレベルに適応）
- 波形ビューア・エンベロープ表示・ピーク可視化
- タイムスタンプ付きCSVエクスポート

**検証実績:** 1分間音声125ファイル・合計3,852回の稼働検出

**使用技術**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)

---

## 🔒 その他の開発実績（ソースコード非公開）

### CPR BEAT — CPR訓練システム

> **「救命講習をより楽しく、スマートに。」リズムゲーム感覚で胸骨圧迫の正しいリズムと深さを身体で覚えられる、高専発のCPRトレーニングシステム**

※ 本体のソースコードは非公開ですが、[公式サイト](https://github.com/rururena6607/CPRHomePage)は単独で開発しコードを公開しています。

**担当**

初期開発者ではなく、既存コードベースへの参加メンバーとして最適化・機能追加・バグ修正を担当。

- **消費電力の大幅削減**（処理ロジック見直しによる最適化）
- **ゲーム時間の可変化**と、それに伴うUIの設計・実装
- 既存ロジックのバグ修正

**プロダクトの機能**
- リアルタイムフィードバックで圧迫のリズム・深さを採点（Hampel法による独自ノイズ除去アルゴリズムで高精度判定）
- 既存の訓練人形に後付けできるラック＆ピニオン式の外付け深度センサー（低コスト・高精度）
- QRコードでトレーニング結果をスマホに保存、成長をグラフ化。緊急時マニュアル・クイズ機能も搭載

**プロジェクト受賞歴**
- 第36回全国高等専門学校プログラミングコンテスト **最優秀賞・文部科学大臣賞** ほか（情報処理学会／電子情報通信学会 若手奨励賞、チームラボ企業賞、NICT賞）
- BCN ITジュニア賞
- 令和7年度 起業家甲子園 NICT理事長賞・SGインキュベート賞

**使用技術**

![Unity](https://img.shields.io/badge/Unity-100000?style=flat&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat&logo=espressif&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

---

### CPR DASH — AED緊急出動管理システム

[![Slides](https://img.shields.io/badge/スライド-Canva-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/95q0rkfy870015k)

> **管理者がマップ上で事故現場を指定すると、半径500m以内のAEDボックス（ESP32）がLED点滅・音声アラートで自動通知し、救助者をナビゲートするリアルタイム救急支援システム**

**主な機能**
- 管理者Webアプリから事故現場をマップ指定 → Firebase経由でAED端末へリアルタイム配信
- ESP32デバイスがLED（NeoPixel 24灯）と音声で現場アラートを発報
- NFCタグにタッチで救助者スマホにナビゲーション表示
- Firebase Realtime Database による双方向データ同期

**使用技術**

![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?style=flat&logo=leaflet&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)

---

### NITK365 — 高専生活ポータルアプリ

> **「これ一つ開けば、学校の今がすべてわかる」。イベント・課題・学食・バス電車・部活動などを統合する、熊本高専の学生生活ポータル（Web）**

**主な機能**
- 学内Googleアカウント（`@g.kumamoto-nct.ac.jp`）限定のSSOログイン（学外アカウントは自動サインアウト）
- 行事カレンダーの作成・編集・表示
- 課題まとめ：ソース別（Classroom / Teams / WebClass / 手動）管理、期限による色分け・警告バナー
- Teams連携API（Power Automate からDBへ直接登録）
- 受験生向け匿名Q&A、落とし物、学内知恵袋、学食メニュー など全10機能を設計
- 管理者・教職員・学生・OB・ゲストの5段階権限とガバナンス（通報・操作ログ）

**使用技術**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)

---

## 🛠️ Tech Stack

**Frontend**

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)

**Backend / Data**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)

**Game / Embedded / IoT**

![Unity](https://img.shields.io/badge/Unity-100000?style=flat&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat&logo=espressif&logoColor=white)

**Infra**

![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)

---


## 📫 Contact

[![Email](https://img.shields.io/badge/Email-te23hirohashi@g.kumamoto--nct.ac.jp-D14836?style=flat&logo=gmail&logoColor=white)](mailto:te23hirohashi@g.kumamoto-nct.ac.jp)
[![Instagram](https://img.shields.io/badge/Instagram-hiroshi__4869-E4405F?style=flat&logo=instagram&logoColor=white)](https://www.instagram.com/hiroshi_4869/)
