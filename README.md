<h1 align="center">Hi 👋 I'm HIROSHI</h1>

<p align="center"><b>要件定義から設計・実装・検証・公開まで、一通り自分の手で進めることを大切にしています。</b></p>

- 🫀 CPR訓練システム「CPR BEAT」の本体ソフトを担当。大規模なリファクタリングの中で、**採点ロジックの不具合を 24 件見つけて修正**
- 🏁 ハッカソン **SPAJAM2026 の予選で優秀賞を受賞し、本選に出場**。本選では企画（原案）・MVP の実装・3D と音の制作・発表を担当
- 💼 福祉事業所の業務システムを **Excel VBA → C# / WPF** に置き換え。請求CSVが旧システムと **実データで完全一致** することを確認
- 🤝 チーム開発では **サーバ・データ層**（Supabase / Firebase の設計、認証、セキュリティルール）を担当することが多い
- 🌐 Web（React / Next.js）、Android（Java）、デスクトップ（C# / WPF）、IoT（ESP32）、信号処理（Python）まで、目的に合わせて技術を選ぶ
- 🤖 Claude Code を使い、**要件定義書 → 実装計画 → 実装 → 実装者とは別の視点でのレビュー** の流れで開発

---

## 📋 作品一覧

| 作品 | 内容 | 体制・担当 | 主な技術 | リンク |
|---|---|---|---|---|
| **[バレー部 分析アプリ](#バレー部-サーブレシーブアタック分析アプリ)** | 試合中にスマホで記録し、集計・AIコメント・LINE通知で振り返る | 3人／データ・サーバ側 | React, Supabase, Claude API, LINE | [コード](https://github.com/rururena6607/KazuoLovers) · [サイト](https://kazuo-lovers.vercel.app) |
| **[もふっと](#もふっと--ペット推し活プラットフォーム)** | 保護犬猫を「推す」体験で支援につなげるプラットフォーム | 個人 | Next.js, TypeScript, Firebase | [コード](https://github.com/rururena6607/mofutto) · [サイト](https://mofutto.vercel.app) · [スライド](https://canva.link/mjis63bg8rc0i8c) |
| **[PBL-B](#pbl-b--エアレスポンプ稼働音声解析システム)** | 工場の稼働音から塗装機の動作回数を自動カウント（企業連携） | 個人 | Python, NumPy, SciPy | [コード](https://github.com/rururena6607/PBL-B) · [スライド](https://canva.link/ha6acgbabmh01le) |
| **[CPR BEAT 公式サイト](#cpr-beat-公式サイト)** | ライブラリを使わずに作った静的サイト | 個人 | HTML, CSS, JavaScript | [コード](https://github.com/rururena6607/CPRBEATwebsite) · [サイト](https://cprbeat-5150c.web.app) |
| **[CPR BEAT](#cpr-beat--cpr訓練システム)** 🔒 | センサで胸骨圧迫を採点する CPR 訓練システム | チーム／本体ソフトの主担当・サーバ | Unity, C#, Cloudflare Workers | — |
| **[SPAJAM2026](#spajam2026--予選で優秀賞本選出場)** 🔒 | ハッカソンの予選で優秀賞、本選に出場。本選は救命をためらう気持ちをはずす体験アプリ「CPR CLEAR」 | 本選2人・予選3人／企画・実装・3Dと音・発表 | Kotlin, Jetpack Compose, Blender, Claude API | — |
| **[業務システム](#福祉事業所の業務システム受託開発)** 🔒 | 福祉事業所の Excel VBA システムを Windows アプリに置き換え | 個人（Claude Code と開発） | C#, .NET 8 WPF, SQLite | — |
| **[CPR DASH](#cpr-dash--aed緊急出動管理システム)** 🔒 | 事故現場近くの AED ボックスが光と音で知らせる救急支援システム | チーム／ハードウェア以外 | React, Firebase, ESP32 | [スライド](https://canva.link/95q0rkfy870015k) |
| **[陣取りアプリ](#陣取りアプリ--歩いた軌跡で陣地を取る-android-アプリ)** 🔒 | 歩いた軌跡で囲んだ範囲が陣地になる（自治体連携PBL） | 4人／全画面・サーバ側 | Java, Android, Firestore | — |
| **[ドローンエミュレーター](#ドローンエミュレーター)** 🔒 | 実機なしでドローン制御プログラムを試せるシミュレーター | 個人 | Python, NumPy, three.js | [デモ（iPad 向け）](https://drone-flightlab.web.app/) |
| **[NITK365](#nitk365--高専生活ポータルアプリ)** 🔒 | 行事・課題・学食などをまとめた学生生活ポータル | 4人 | Next.js, Supabase | — |

🔒 はソースコード非公開（下に詳細を書いています）

---

## 📂 ソースコードを公開している作品

### バレー部 サーブ・レシーブ・アタック分析アプリ

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/KazuoLovers)
[![Demo](https://img.shields.io/badge/公開サイト-kazuo--lovers.vercel.app-000000?style=flat&logo=vercel&logoColor=white)](https://kazuo-lovers.vercel.app)

> **バレー部の試合中に、サーブ・サーブレシーブ・アタックを1本2〜5タップで記録。選手別・ゾーン別に集計し、AIが練習アドバイスを書き、部のLINEグループに結果が届くWebアプリ**（授業「APIを用いた自由課題」、3人チーム）

**担当：データ・サーバ側**
- 3人が並行して作れるよう、画面・データ・計算の間の型の約束（`contracts`）を最初に設計
- Supabase のテーブル設計と RLS（行レベルセキュリティ）、ログイン
- 記録の保存・読み込みと、**体育館で電波が切れても記録が消えない送信待ち・自動再送**（IndexedDB）
- Supabase Edge Function で Claude API を呼ぶ AI コメント（**外部AIには背番号と数値だけを送り、名前は送らない**）
- LINE Messaging API の Webhook（Botへのメンションで試合結果を返信）と、公式戦終了時の自動投稿
- Supabase Realtime による複数端末での同時記録

**アプリの主な機能**
- 着弾点を座標で保存し、ヒートマップ・散布図・コース割合で「相手が崩れやすい狙い所」「自チームが崩される場所」を可視化
- セット別の結果・得点の推移、練習モード、紅白戦の記録、作戦ボード
- PWA としてホーム画面に追加でき、iPhone / Android どちらでも同じURLで使える

**使用技術**

![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)
![Claude API](https://img.shields.io/badge/Claude_API-191919?style=flat&logo=anthropic&logoColor=white)
![LINE](https://img.shields.io/badge/LINE_Messaging_API-00C300?style=flat&logo=line&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat&logo=pwa&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat&logo=vitest&logoColor=white)

---

### もふっと — ペット推し活プラットフォーム

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/mofutto)
[![Demo](https://img.shields.io/badge/デモ-mofutto.vercel.app-000000?style=flat&logo=vercel&logoColor=white)](https://mofutto.vercel.app)
[![Slides](https://img.shields.io/badge/発表スライド-19ページ-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/mjis63bg8rc0i8c)

> **保護犬猫を「アイドルのように推せる」プラットフォーム。「寄付」ではなく「推す・贈る・応援する」体験で、一頭ずつの個性と物語を主役にする**

**担当**

企画・設計・実装・デプロイまで単独で開発。

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

### PBL-B — エアレスポンプ稼働音声解析システム

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/PBL-B)
[![Slides](https://img.shields.io/badge/発表スライド-36ページ-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/ha6acgbabmh01le)

> **防爆室内にセンサーを設置できない工場環境において、室外から録音した音声データを解析し、塗装機の稼働回数を自動カウントするデスクトップ解析ツール**（高専のPBL授業における企業連携プロジェクト）

**担当**

解析手法の検討から実装・検証まで単独で開発。

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

### CPR BEAT 公式サイト

[![Repo](https://img.shields.io/badge/ソースコード-GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/rururena6607/CPRBEATwebsite)
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

## 🔒 ソースコード非公開の作品

### CPR BEAT — CPR訓練システム

> **「救命講習をより楽しく、スマートに。」センサで胸骨圧迫の深さとリズムを測り、リズムゲーム感覚で採点する CPR トレーニングシステム**

**体制と担当**

2025年秋（高専プロコンの直後）にチームに参加し、まず **公式サイト** を設計から公開まで単独で担当。2026年春から本体ソフトの開発に加わり、7月からは **本体ソフト（Unity）の主担当** です。あわせて、イベント版、ランキングサーバ、Web 版も開発しています（ハードウェアと XR 版は別のメンバーが担当）。

**① 本体の品質改善：リファクタリングと、採点の不具合の発見・修正**
- 139 ファイル・+16,000 行規模のリファクタリングを担当
- 作業の途中で **採点ロジックの不具合を 24 件見つけて記録** し、影響の大きいものから修正
  - 例：圧迫速度とリコイル速度が入れ替わって採点されていた → 修正し、過去データ 1,081 件の移行スクリプトも作成
  - 例：毎拍の生データが 1/10 に書き換えられていた、窓平均の割る数の誤り、システム時刻の巻き戻り
- 主要クラスを分割（例：424 → 108 行、204 → 90 行）。コンパイラ警告を 14 → 1 件に
- アセットを整理して **プロジェクトサイズを 783MB → 323MB** に削減。Enter Play Mode Options を有効にして、エディタでの起動待ちを短縮
- 本体の開発に加わった当初は、リザルト画面の表示崩れ、ゲーム中の停止、2回目のプレイに前回のデータが残る、などのバグ修正と、メモリが溜まり続ける問題の解消、ゲーム時間の可変化を担当

**② イベント出展版：対戦モードとランキング**
- 1台の PC にセンサを2台つなぐ **1 対 1 対戦モード** を、要件定義から実装まで担当
- 有線シリアルに加えて **BLE センサに対応**。入力をインターフェースで抽象化し、Windows（C++）と macOS（Objective-C++）のネイティブプラグインを用意
- **ランキング・アカウントサーバ** を Cloudflare Workers + D1 + Durable Objects で構築し、本番で運用
  - Google サインインの不具合（CSP / Referrer-Policy）を修正
  - メンバー判定を「末尾一致」にすると誰でもメンバーになれてしまう問題に気づき、完全一致に変更
- 会場にネットがなくても使えるよう、結果を **HMAC-SHA256 で署名して QR に入れ、あとでスマホから登録する方式** を設計

**③ そのほか**
- **Web 版 CPR BEAT**：Unity 版を React + TypeScript で作り直し、センサ（Web Serial）・カメラ（MediaPipe Pose）・タッチの3つの入力に対応（個人開発）
- **公式サイト**（チームに入って最初の担当）：設計からデプロイまで単独で開発（[公開しているコード](https://github.com/rururena6607/CPRBEATwebsite)）。メンバーがブラウザから投稿できるブログ機能（Firebase Auth / Firestore）や、note 記事の自動同期（GitHub Actions）も追加
- **チームの開発環境**：企画 → 設計 → 実装 → レビューを Claude Code のサブエージェントで回すプラグインを作り、チームで共有

**使用技術**

![Unity](https://img.shields.io/badge/Unity-100000?style=flat&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers_/_D1-F38020?style=flat&logo=cloudflare&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![ESP32](https://img.shields.io/badge/ESP32_(BLE)-E7352C?style=flat&logo=espressif&logoColor=white)

---

### SPAJAM2026 — 予選で優秀賞・本選出場

> スマホアプリ開発ハッカソン **SPAJAM2026** に CPR BEAT のメンバーで出場。予選で **優秀賞** をいただき、本選（2026年11月・箱根）に出場しました。どちらも当日に出されたテーマから、企画・実装・発表までを決められた時間内で行います。

#### 本選：CPR CLEAR — 「ためらい」をはずす救命体験アプリ（2人チーム）

> **駅のホームで倒れた女性を一人称の視点で助ける体験アプリ。周りの人に119番・AED を頼み、胸骨圧迫をして、服をずらして AED のパッドを貼り、救急隊に引き継ぐ。** テーマ「色」から、「訴えられたら？」「疑われたら？」という思い込みを“色眼鏡”として描き、迷っている間に倒れた人のいのちの色が抜けていく形にした

**担当：企画（原案）、MVP の実装、3D の絵と音の制作、プレゼン**
- 女子生徒への AED のパッド使用率が低いという研究データから、「手技の訓練」ではなく **「ためらいをはずす」体験** という企画を立てた
- 3D エンジンを使わず、Blender（Python スクリプト）で書き出した画像とカメラの値を使い、**Jetpack Compose の Canvas に一人称の3Dを描画**。スマホの回転ベクトルセンサーで周りを見まわせる
- 効果音・環境音・駅のメロディを Python（numpy）で合成
- 「青い服の方、119番お願いします」という呼びかけを端末内の音声認識で判定。通信なしで、入れてすぐ動く
- 単体テストと、Robolectric で端末なしに各場面の画面を書き出して見た目を確かめるテスト
- 本選に向けて、Claude Code が GitHub の Issue を順に実装・PR・マージし、止まったら別の PC が引き継ぐ **夜間自動開発の仕組み** をチームで用意

#### 予選：スパにゃん119 — 119番通報の練習ゲーム（3人チーム・🏆 優秀賞）

> **ランダムな時刻に倒れる「スパにゃん」を助けるため、AI 指令員と音声で模擬通報し、現在地の住所や周りの目印を正しく伝えられたかをスコアで振り返る育成型ゲーム。** テーマ「つなぐ」から、救命の連鎖の最初の輪である“通報”を日常で身につけられるようにした

**担当：バックエンド関連と UI の修正**
- 通報内容の採点ロジック（伝えた場所の採点を含む）と単体テスト
- Claude API を使った AI 指令員のプロンプト設計と、実際の応答で確かめる評価テスト
- AI 指令員の音声の事前合成（AITalk）、シナリオの追加、UI の演出

**使用技術**

![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat&logo=jetpackcompose&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat&logo=android&logoColor=white)
![Blender](https://img.shields.io/badge/Blender-E87D0D?style=flat&logo=blender&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Claude API](https://img.shields.io/badge/Claude_API-191919?style=flat&logo=anthropic&logoColor=white)

---

### 福祉事業所の業務システム（受託開発）

> **放課後等デイサービス事業所で使われていた Excel + VBA の業務システムを、Windows アプリ（C# / .NET 8 WPF + SQLite）に置き換え**

**ポイント**
- **請求CSVをバイト単位で仕様化** し、移行したデータで **実運用の請求CSV（1か月分）と完全一致** することを確認してから画面の開発に進めた
- 事業所内の共有フォルダに置いた SQLite を **複数台から同時に書き込む負荷試験**（`gate` / `stress` コマンド）を自作し、書き込み件数の一致を検証
- アカウントとロール、月次締め、バックアップ、操作履歴、業務日誌、児童マスタ
- 既存の Excel 帳票テンプレートのセルに値を書き込む方式で、記録票ほか7種類の帳票を印刷
- 旧システムからのデータ移行スクリプト（Python）、CLI の `selftest` による自己検査
- Claude Code を使って実装し、作業記録・レビュー記録・セキュリティレビューを文書で残しながら開発

**使用技術**

![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_8_WPF-512BD4?style=flat&logo=dotnet&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

---

### CPR DASH — AED緊急出動管理システム

[![Slides](https://img.shields.io/badge/発表スライド-27ページ-00C4CC?style=flat&logo=canva&logoColor=white)](https://canva.link/95q0rkfy870015k)

> **管理者がマップ上で事故現場を指定すると、半径500m以内のAEDボックス（ESP32）がLED点滅・音声アラートで自動通知し、救助者をナビゲートするリアルタイム救急支援システム**

**担当**

ハードウェア以外（管理者Webアプリ、Firebase の設計、ESP32 のプログラム、救助者向けナビゲーション）を担当。

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

### 陣取りアプリ — 歩いた軌跡で陣地を取る Android アプリ

> **市内を歩いた軌跡でループを閉じると、囲んだ範囲が自分の陣地になる。自治体（合志市）との連携PBLで、市の健康アプリ『うぇるこ』の「歩数（量）」に「どこを歩いたか（面）」を足す拡張モジュールとして提案**（4人チーム）

**担当：すべての画面とサーバ側**
- 地図と陣地の描画、記録中画面、ランキング、チュートリアルなど **全画面と画面遷移・アプリ全体の見た目**
- Firestore のリポジトリ層、トランザクション、**セキュリティルールとそのテスト**、週次リセット、チーム戦
- Gradle マルチモジュールで **モジュールの境界＝担当の境界** にし、PRのレビュアーを「実装者以外の検証担当」に固定する運用

**設計上の工夫**
- 位置情報は端末内に留め、サーバへ送るのはポリゴン頂点とメッシュセルIDだけ。**記録開始から最初の150mを捨てて自宅の位置を隠す**
- 面積・ループ判定は平面直角座標系（EPSG:6670）と JTS で計算
- 発表用に、1か月後の盤面を早回しで再生するデモモード

**使用技術**

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat&logo=android&logoColor=white)
![Firebase](https://img.shields.io/badge/Firestore-FFCA28?style=flat&logo=firebase&logoColor=black)
![Google Maps](https://img.shields.io/badge/Google_Maps_SDK-4285F4?style=flat&logo=googlemaps&logoColor=white)

---

### ドローンエミュレーター

[![Demo](https://img.shields.io/badge/デモ-drone--flightlab.web.app-FFCA28?style=flat&logo=firebase&logoColor=black)](https://drone-flightlab.web.app/)

> 💡 ブラウザ版のデモは **iPad に最適化** しています。

> **実機なしでドローン制御プログラムを開発・テストするための、クアッドコプターのエミュレーター。Tello SDK 風のテキストコマンド（UDP）で操作でき、既存の Tello 用コードをそのまま向けられる**

**主な機能**
- 6自由度の剛体物理（RK4 積分 500Hz）、位置→速度→姿勢→角速度のカスケード制御、風・突風（Ornstein–Uhlenbeck 過程）
- IMU・気圧計・GPS・ToF などのセンサーノイズ、運動量理論によるバッテリー消費と電圧降下
- テレメトリ CSV と、依存ライブラリなしの SVG グラフによる HTML フライトレポート
- 同じ物理・制御を JavaScript に移植したブラウザ版（three.js、[公開中](https://drone-flightlab.web.app/)・iPad に最適化）。6〜10歳向けのブロックプログラミング版と、高校の授業向けの本格版

**使用技術**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat&logo=threedotjs&logoColor=white)

---

### NITK365 — 高専生活ポータルアプリ

> **「これ一つ開けば、学校の今がすべてわかる」。イベント・課題・学食・バス電車・部活動などを統合する、熊本高専の学生生活ポータル（Web）**

**体制**

4人チームで開発。

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

**Mobile / Desktop**

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_WPF-512BD4?style=flat&logo=dotnet&logoColor=white)

**Backend / Data**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Claude API](https://img.shields.io/badge/Claude_API-191919?style=flat&logo=anthropic&logoColor=white)
![LINE](https://img.shields.io/badge/LINE_Messaging_API-00C300?style=flat&logo=line&logoColor=white)

**Game / Embedded / IoT**

![Unity](https://img.shields.io/badge/Unity-100000?style=flat&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat&logo=espressif&logoColor=white)

**Infra / Tools**

![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![Firebase Hosting](https://img.shields.io/badge/Firebase_Hosting-FFCA28?style=flat&logo=firebase&logoColor=black)
![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=flat&logo=cloudflare&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)

---

## 📫 Contact

[![Email](https://img.shields.io/badge/Email-te23hirohashi@g.kumamoto--nct.ac.jp-D14836?style=flat&logo=gmail&logoColor=white)](mailto:te23hirohashi@g.kumamoto-nct.ac.jp)
[![Instagram](https://img.shields.io/badge/Instagram-hiroshi__4869-E4405F?style=flat&logo=instagram&logoColor=white)](https://www.instagram.com/hiroshi_4869/)
