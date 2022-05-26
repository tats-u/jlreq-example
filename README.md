# HTMLとCSSだけでなるべく日本語の組版規則に近づける<br />Conform to the Requirements for Japanese Text Layout as much as possible using only HTML and CSS

[サンプルページ / Sample Page](https://tats-u.github.io/jlreq-example/)（HTML・CSSのみ / Only HTML & CSS）

## これは何？<br />What is this?

普通にHTMLを書くと、一部の日本語組版規則が守られません。具体的に言うと、  
If you write HTML as usual, you will not be able to comply with some of the Requirements for Japanese Text Layout:

- 日本語と英数字の間に四分アキ（全角1/4幅の空白）が入るべき  
  You MUST add quarter em spacing between hiragana, katakan or ideographic characters (kanji / han) and Western characters or European numerals.
- 約物（括弧や中点など）が連続した際には、字間を詰めて余計なスペースを減らすべき  
  You MUST reduce spaces in sequences of punctuation marks.
- 数字と単位の間は四分アキにすべき  
  You SHOULD add quarter em spacing between numerics and unit indicators (km, kg, mm etc.) in Latin letters.

です。上のページでは、CSSの`margin`・`padding`・`letter-spacing`属性を駆使することにより、擬似的に上の規則をほぼ遵守させることができます。  
The above page almost complies with the above rules in a pseudo way by making full use of the CSS `margin`, `padding`, and `letter-spacing` attributes.

## どんなことに応用できる？<br />What can this be applied to?

React等のプラグインとして、コンポーネント内の文字列を解析し、適切な空白の挿入・削除をするものを開発できれば、簡単に規則を守ったサイトやアプリができます。

現在、ブログや技術サイトで欧文間隔（`U+0020`）を利用して四分アキの代わりに使用する例を多く見かけますが、日本語の組版規則では認められない上（中国語では認められていますが、第一選択肢ではありません）、検索性が大きく犠牲になっています。四分アキよりも広い幅を取ってしまう上、Prettier等のツールがないと手動でスペースを挿入しないといけないため、文書作成のUXが落ちます。
