---
name: suno
description: Suno AIで音楽を生成するための最適化されたプロンプトを作成します。「/suno」で起動し、ジャンル、ムード、テンポ、楽器、ボーカル、曲構造などの入力からSunoのStyle of Music欄に貼り付けられる英語プロンプトを生成します。
argument-hint: [ジャンルや雰囲気の簡単な説明（省略可）]
---

# Suno 音楽生成プロンプトビルダー

Suno AI で高品質な楽曲を生成するための最適化されたプロンプトを対話形式で作成します。

## ユーザーの入力

$ARGUMENTS

## 動作フロー

### STEP 1: 入力収集

**引数がある場合**: 引数の内容を音楽的な意図として解釈し、不足パラメータを補完してプロンプトを生成します。

**引数がない場合**: 以下のフォームをユーザーに提示して入力を求めます。

---

```
🎵 Suno プロンプトビルダー
━━━━━━━━━━━━━━━━━━━━━━━━━━━

以下の項目を教えてください。
不要な項目は空欄のままでOKです。

① ジャンル／スタイル
   （例: J-Pop / Lo-fi Hip Hop / Synthwave / Acoustic Folk）
   複数組み合わせると独自の雰囲気になります。
   →

② ムード／感情
   （例: melancholic / euphoric / dreamy / aggressive / nostalgic）
   →

③ テンポ／BPM
   （例: slow ballad / mid-tempo groove / fast-paced / 120 BPM）
   →

④ 使用楽器・サウンド
   （例: acoustic guitar, piano, strings / heavy distortion guitar, 808 bass）
   →

⑤ ボーカルの特徴
   （例: female soft Japanese / male raspy English / instrumental only）
   性別・歌い方・言語を指定できます。
   →

⑥ 曲の構造
   （例: verse-chorus-verse-chorus-bridge-chorus）
   省略するとデフォルト構成を使います。
   →

⑦ リファレンス表現
   （例: 90s Japanese city pop feel with groovy bass lines）
   アーティスト名より「スタイルを言葉で」書く方が安定します。
   →

⑧ その他の味付け
   （例: reverb-heavy / lo-fi crackling / 80s retro / 約3分）
   →
```

---

### STEP 2: プロンプト生成

ユーザーから情報を受け取ったら、以下のルールでSunoプロンプトを生成します。

#### 生成ルール

1. **英語で出力** — Sunoは英語プロンプトが最も安定して機能する
2. **アーティスト名は使わない** — 「Taylor Swift-like」ではなく「powerful female pop vocals with country influences」のように言葉で表現する
3. **具体的な楽器名を使う** — 「guitar」より「fingerpicked acoustic guitar」が効果的
4. **カンマ区切りで簡潔に** — スタイル欄は120文字以内が理想
5. **ムードは形容詞で** — 「happy」より「euphoric and uplifting」など感情を豊かに表現する

#### 出力フォーマット

```
[ジャンル/スタイル], [ムード], [テンポ], [楽器], [ボーカル], [リファレンス], [その他]
```

### STEP 3: 最終出力

以下の形式で出力します。

---

**▼ Style of Music（Sunoのスタイル欄に貼り付け）**
```
[生成されたスタイルプロンプト（英語）]
```

**▼ 曲の構造タグ（歌詞の冒頭に追加）**
```
[Intro]

[Verse]
（ここに歌詞）

[Chorus]
（ここに歌詞）

[Verse]
（ここに歌詞）

[Chorus]
（ここに歌詞）

[Bridge]
（ここに歌詞）

[Chorus]
（ここに歌詞）

[Outro]
```
※ユーザーが曲構造を指定した場合はそれに従う

**▼ パラメータ解説**
各要素がプロンプトにどう反映されたかを日本語で簡潔に説明します。

---

## 生成例

**入力:**
- ジャンル: J-Pop, City Pop
- ムード: nostalgic, dreamy
- テンポ: mid-tempo, 95 BPM
- 楽器: electric piano, bass guitar, light drums, saxophone
- ボーカル: female, soft, breathy, Japanese
- リファレンス: 80s Japanese city pop with smooth groovy bass lines
- その他: reverb-heavy, warm analog sound

**生成プロンプト:**
```
J-Pop, City Pop, 80s Japanese city pop, nostalgic dreamy atmosphere, mid-tempo 95 BPM, electric piano, groovy bass guitar, light jazz drums, smooth saxophone, soft breathy female vocals, reverb-heavy, warm analog sound, lush and sophisticated
```
