---
marp: true
theme: default
paginate: true
class: lead
math: katex
title: 第1回：TouchDesignerの基本操作とインタラクション入門
header: 情報学課題解決実習2A
footer: TouchDesigner | T.Shimizu © 2025
---

# 情報学課題解決実習2A
## 第1回  TouchDesignerの基本操作とインタラクション入門

授業担当：情報学部 情報学科 情報メディ専攻 清水 哲也

---

# 本日の目標

- TouchDesignerの基本概念とUIに慣れる  
- 画像・動画・カメラ映像の表示を行う  
- マウスとマイクからの入力で映像に変化をつける  
- インタラクティブ表現の基礎を体験する

---

# TouchDesignerとは？

- Derivative社が開発した**ノードベースのビジュアルプログラミング環境**
- 主な用途：
  - リアルタイム映像制作
  - インタラクティブアート
  - 舞台演出・展示空間演出
- 無償版あり（非商用・解像度制限あり）

---

# UI構成と基本操作

- Network Editor（ノード構成画面）
- Parameters パネル（ノードごとの設定）
- Timeline（時間制御）
- Pane（表示切替）
- ショートカット：
  - `Tab`キー：OP作成
  - `Alt+ドラッグ`：複製
  - `Del`キー：削除

---

# 主なオペレータ（OP）


| 種類 | 説明・用途 | 例 |
|------|------------|----|
| TOP  | 画像・映像処理 | Movie File In, Composite |
| CHOP | 時系列データ処理 | Audio In, Mouse In, LFO |
| SOP  | 3D形状制御 | Sphere, Transform |
| DAT  | テキスト／表 | Table, Text |
| COMP | コンポーネント | Slider, Container |

---

# 映像表示の基本（TOP）

1. `Movie File In TOP`で画像・動画を読み込み  
2. `Null TOP` → `Out TOP`へ接続

---

# Webカメラ映像を表示

- `Video Device In TOP`でWebカメラ映像を取得  
- `Null TOP` → `Out TOP`に接続

---

# マウス入力の活用（CHOP）

- `Mouse In CHOP` で座標データ取得  
- `Null CHOP`を挟んで、ビジュアルのパラメータにリンク  
- 使用例：
  - X位置で画像の大きさ変化
  - Y位置で色が変化

---

# 音声入力の活用（CHOP）

- `Audio Device In CHOP` → `Analyze CHOP` で音量など抽出  
- 音の大きさでサイズ・色・動きに変化を加える  
- `Math CHOP`で値の範囲を調整可能

---

# Parameter Linkingの方法

- **Drag & Dropで接続**
- **Export CHOP**: 緑いワイヤー  
- **Expression**: `op('null1')['chan1']` などの記述式

---

# ハンズオン課題①（カメラ）

🎯 **Webカメラの映像にエフェクトを加えよう**

- `Video Device In` → `Blur TOP` → `Level TOP` → `Out TOP`  
- `Level`で明るさ調整、`Blur`でぼかし効果

---

# ハンズオン課題②（音）

🎯 **音に反応してビジュアルが変わる表現を作ろう**

- `Audio Device In CHOP` → `Analyze CHOP`  
- 値を `Transform TOP` の `scale` にリンク  
- 作品例：音量で揺れる円、拡大・縮小する模様

---

# ハンズオン課題③（マウス）

🎯 **マウス位置で映像の色を変える**

- `Mouse In CHOP` → `Math CHOP` で 0-1 に正規化  
- 値を `Level TOP` の `Brightness` や `Gamma` に接続

---

# 発展例：マウス＋音を組み合わせる

- マウス：位置に応じて色・位置変更  
- 音声：サイズや回転の変化に利用  
- `Composite TOP` で多重合成することで表現を増やす

---

# 質疑応答・確認

- 接続がうまくいかないときは `Null TOP` や `Math CHOP` を確認  
- 各ノードの `Viewer Active`（右上）をONにして状況確認

---

# まとめ

- TouchDesignerの基本的な使い方（TOP / CHOP）を習得  
- マウスやマイクなどの入力に反応する作品を作成  
- 次回は時間制御・UIによる構成強化に進む

---

# 次回予告

**第2回：アニメーション制御とUIの活用**

- 時間の流れやトリガーを使った動的表現  
- スライダーやボタンで操作できるUIの作成

---

## 参考リンク

- 公式サイト: https://derivative.ca/  
- 日本語チュートリアル: https://nvoid.com/tutorials  
- YouTube: "TouchDesigner Beginner Tutorials"

---

## ご質問はありますか？

---
