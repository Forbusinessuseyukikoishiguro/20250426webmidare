# 20250426webmidare
Webサイト英語化に伴うレイアウト崩れ修正練習
****
## 【保存版】英単語の改行崩れを防ぐ！CSSで美しくテキスト整列する方法まとめ

Web制作で多言語対応をしていると、日本語と英語のテキストが混在するシーンも多いですよね。特に英語では「単語が長すぎて途中で折り返されてしまう」ことがあり、ユーザー体験を損なう原因になります。

本記事では、HTML/CSSでテキストの整列を美しく保ちつつ、長い英単語が途中で切れてしまう問題を解決する方法を丁寧に解説します。

---

### 🔍 よくある問題：英単語の途中で改行される

たとえば以下のような英語テキスト：

> This is an example of text containing long English words like `supercalifragilisticexpialidocious` and `antidisestablishmentarianism`.

スマホや狭い画面で見ると、単語の途中で強制的に折り返されてしまい、読みづらくなることがあります。

---

### ✅ 解決策1：`word-break: keep-all` と `overflow-wrap: break-word` を使う

CSSで以下のように設定します：

```css
word-break: keep-all;
overflow-wrap: break-word;
```

これにより、英単語が途中で改行されにくくなり、必要なときだけ自然な場所で折り返されます。

---

### ✅ 解決策2：`text-align: justify` と組み合わせて整列

以下のようにすることで、テキスト全体の行頭・行末も揃えつつ、読みやすい表示ができます：

```css
text-align: justify;
overflow-wrap: break-word;
word-break: normal;
```

読みやすさと見た目の美しさを両立できるおすすめの方法です。

---

### ✅ 解決策3：英語テキストには `hyphens: auto` を使おう

自動ハイフネーション（-）を付けて、英単語の途中に自然な改行ポイントをつくる方法です：

```css
hyphens: auto;
text-align: justify;
word-break: normal;
```

ただし、このプロパティは英語などの言語向けです。日本語には効果がありません。

---

### 📱 レスポンシブ対応も忘れずに

長い単語を処理するだけでなく、スマホ・タブレットなどの小さい画面でも読みやすくするために、`@media`クエリでスタイル調整をしましょう。

```css
@media (max-width: 768px) {
  h1 {
    font-size: 20px;
  }
}

@media (max-width: 480px) {
  body {
    padding: 10px;
  }
}
```

---

### ✨ おわりに

この記事では、英語の長い単語による改行崩れをCSSで解決するテクニックを紹介しました。読みやすさや見た目の整ったテキストレイアウトは、ユーザー体験を大きく向上させます。

ぜひ、あなたのサイトやアプリに取り入れてみてくださいね！

