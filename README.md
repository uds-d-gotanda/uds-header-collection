# uds-header-collection

IT部門ポータルサイト向けのクリエイティブ・ヘッダーコレクションです。
「デジタルアクアリウム」と「デジタルダスト（積雪）」の2種類の視覚効果を提供します。

## フォルダ構成

```text
uds-header-collection/
├── aquarium/            # デジタルアクアリウム版
│   └── it_header_aquarium.html
└── digital-dust/        # デジタルダスト（積雪）版
    └── it_header_dust.html
```

## カスタマイズ：表示テキストの変更方法

各ファイル、1箇所の書き換えで好きな文字（社名、プロジェクト名、DXなど）に変更可能です。

### 1. デジタルダスト（積雪）版の場合
プログラムが自動的に文字の形状をスキャンするため、JavaScript内の変数を書き換えるだけで、どのような文字にも粒子が積もります。

```javascript
// it_header_dust.html の 130行目付近
/**
 * 【カスタマイズ】表示したい文字をここに入れてください
 */
const DISPLAY_TEXT = "IT"; // ← ここを "DX" や "UDS" などに変更
```

### 2. デジタルアクアリウム版の場合
HTML内のテキスト要素を直接書き換えます。

```html
<div class="text-container">
    <h1 class="it-title" id="it-text">IT</h1> </div>
```

## 主な機能と調整パラメータ

### デジタルダスト版の物理設定
雪の降り方や吹き飛ばしの強さを調整したい場合は、以下の定数を変更してください。

```javascript
const PARTICLE_COUNT = 500; // 粒子の数（密度）
const GRAVITY = 0.025;      // 重力（小さいほどゆっくり降ります）
const FRICTION = 0.97;      // 空気抵抗
```

### 共通のスタイル設定
背景色や文字の色は、CSS変数を変更することでサイトのデザインに合わせられます。

```css
:root {
    --bg-color: #ffffff;   /* 背景色 */
    --text-main: #475569;  /* 文字の基本色（Slate 600） */
    --accent-blue: #0078ff; /* 粒子のアクセントカラー1 */
}
```

## ライセンス

本プロジェクトは [MIT License](LICENSE) の下で公開されています。
