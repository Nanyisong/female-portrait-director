[English](README.md) | [简体中文](README_zh.md) | [日本語](README_ja.md) | [한국어](README_ko.md)

# 女性ポートレート・プロンプトディレクター Skill

女性ポートレート・プロンプトディレクター Skill は、AI 画像生成向けの構造化プロンプト生成・視覚ディレクションシステムです。V1.3 では、明示されたパラメータを固定し、年齢表現、顔立ち、体型、ポーズ、衣服、シーン、カメラ、光、フィルターを詳細化してから、一つの自然な撮影瞬間へ統合します。

このプロジェクトは単なるプロンプト集ではなく、拡張可能な女性ポートレート用 Skill フレームワークです。

## プロジェクトの目的

少数の入力パラメータから完全なプロンプトを生成します。ユーザーが明示した条件を保持しながら、顔立ち、体型、衣服、シーン、カメラとポーズ、光、フィルター、利用プラットフォーム、ネガティブ制約を視覚的に拡張します。対象人物は成人女性であることを明確にし、リアルな写真表現、節度のある演出、統一感、安定した生成を重視します。

## 対応スタイル

- ナチュラルなライフスタイル写真
- 抑制の効いた曲線美ライフスタイル写真
- 都会的なファッション写真
- 古風・仙侠テイストの人物画
- EC 向け衣服モデル画像

## 主な機能

- ユーザーが指定したパラメータを固定し、詳細化と安定化のみを行います。
- 目的に合うスタイルテンプレートを選択し、矛盾するスタイル語の混在を避けます。
- 顔立ち、体型、衣服、シーン、カメラとポーズ、光、フィルターをモジュールとして解析します。
- 短いパラメータを具体的な視覚ディレクションへ展開し、機械的な言い換えを避けます。
- 展開したモジュールを自然で詳細なコピー可能プロンプトへ統合します。
- EC 画像では衣服表示を優先し、曲線美スタイルでは明確な安全境界を維持します。

## クイックスタート

このリポジトリを Codex Skill として利用する場合は、`$female-portrait-director` を呼び出します。最小入力例：

```text
スタイル：ナチュラルなライフスタイル写真
シーン：カフェの窓際席
服装：白いニットカーディガン + 淡色のインナー
雰囲気：清潔感があり、やさしい
アスペクト比：9:16
```

システムは固定済みパラメータ、コピーして使える完全なプロンプト、ネガティブ制約を返します。全入力項目は [parameter_schema.md](skill/parameter_schema.md)、使用例は [usage_examples.md](skill/usage_examples.md) を参照してください。

## インストール

リポジトリを Codex の skills ディレクトリにクローンします。

Windows PowerShell：

```powershell
git clone https://github.com/liyue-aigc/female-portrait-director.git "$env:USERPROFILE\.codex\skills\female-portrait-director"
```

macOS または Linux：

```bash
git clone https://github.com/liyue-aigc/female-portrait-director.git "${CODEX_HOME:-$HOME/.codex}/skills/female-portrait-director"
```

新しい Codex 会話を開始し、次を呼び出します。

```text
$female-portrait-director
```

## 例：パラメータからディレクション付きプロンプトへ

この Skill は入力を言い換えるだけではありません。明示された条件を保持し、不足している視覚要素を補完し、固定済みパラメータ、モジュール解析、完全なプロンプト、ネガティブ制約を出力します。

```text
スタイル：古風・仙侠テイストの人物画
シーン：霧深い山水の中にある古風な庭園回廊
服装：月白色の唐風幻想大袖衫 + 軽やかな披帛 + 銀刺繍の腰帯
雰囲気：清冷、距離感、仙気
顔立ち：古典的な東洋美人
体型：細身で繊細な体型
カメラ：軽い横向きの立ち姿、半身から太ももまで
光：冷調の柔光
フィルター：清冷で仙気のある古風フィルター
アスペクト比：9:16
用途：キャラクターポートレート
```

![古風仙侠プロンプト展開例](assets/examples/gufeng-director-output.jpg)

## 出力形式

```text
1. 固定済みパラメータ
2. モジュール解析
3. 最終プロンプト
4. ネガティブ制約
```

## リポジトリ構成

```text
.
├── README.md
├── README_zh.md
├── README_ja.md
├── README_ko.md
├── SKILL.md
├── agents/openai.yaml
├── assets/examples/
├── skill/
│   ├── skill.md
│   ├── public_instructions.md
│   ├── parameter_schema.md
│   ├── usage_examples.md
│   ├── references/
│   │   ├── director-expansion.md
│   │   └── visual-libraries.md
│   └── routes/
├── docs/
│   ├── style_guide.md
│   ├── prompt_safety.md
│   ├── versioning.md
│   └── faq.md
└── examples/
```

## 安全境界

このプロジェクトは、架空の成人を対象とした、露骨ではなく有害でもない視覚プロンプト生成にのみ使用できます。未成年者の性的表現、露骨なヌード、同意のない画像、なりすましを目的としたコンテンツ、嫌がらせ、名誉毀損、プライバシー侵害、その他の違法な目的には使用できません。詳細は [prompt_safety.md](docs/prompt_safety.md) と [DISCLAIMER.md](DISCLAIMER.md) を参照してください。

## ライセンス

このプロジェクトは [MIT License](LICENSE) の下で公開されています。MIT License は、使用、複製、変更、結合、公開、配布、再許諾、複製物の販売を許可します。安全境界は責任ある利用のためのガイドラインであり、標準 MIT License の条件を変更するものではありません。

## 作者とバージョン

- 作者：Li Yue（李岳）
- バージョン：`FEMALE-PORTRAIT-DIRECTOR-V1.3`
- プロジェクト：`Female Portrait Prompt Director Skill`
