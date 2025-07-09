# Marp でスライドを作成する際の記述方法

## marp の有効化

先頭に下記のように記述することで、Marp のスライドとして認識されます。

```markdown
---
marp: true
---
```

## ページの区切り

### 明示的な区切り

スライドの区切りは、`---` で行います。

```markdown
# ページ 1

---

# ページ 2
```

### 暗黙的な区切り

<!-- headingDivider: 2 -->を追加すると、見出しレベル2以上の場合はスライドタイトルとしてみなされ、スライドが自動的に区切られるようになる。

## Local directives

ページ先頭に指定することでページ全体に適用される。

| Name               | Description                                       |
| ------------------ | ------------------------------------------------- |
| marp               | marp の有効化                                     |
| theme              | テーマの指定(default, gaia, uncover)              |
| paginate           | true を指定した場合は、スライドにページ番号を表示 |
| header             | ヘッダーの内容を指定                              |
| footer             | フッターの内容を指定                              |
| class              | スライドの<section>要素の HTML クラスを指定(※2)   |
| backgroundColor    | background-color のスタイル                       |
| backgroundImage    | background-image のスタイル                       |
| backgroundPosition | background-position のスタイル                    |
| backgroundRepeat   | background-repeat のスタイル                      |
| backgroundSize     | background-size のスタイル                        |
| color              | color のスタイル                                  |
| style              | 後述                                              |

スタイルの適用対象は主に下記対象となる。

| style   | description    |
| ------- | -------------- |
| h1      | 見出し 1       |
| h2      | 見出し 2       |
| h3      | 見出し 3       |
| h4      | 見出し 4       |
| h5      | 見出し 5       |
| h6      | 見出し 6       |
| a       | ハイパーリンク |
| p       | 段落           |
| ul      | 箇条書き       |
| ol      | 順序付きリスト |
| section | スライド全体   |
| table   | 表             |
| tr      | 行全体         |
| th      | 表の見出し     |
| td      | データ         |
| 他      |                |

ページの途中で Local directives を使用することも可能。
ページの先頭で下記のように先頭に'\_'を付けて記述することで、対象ページにのみ適用される。

```markdown
<!--
# 背景色
_backgroundColor: black
# 文字色
_color: white
-->
```

VSCode の設定`markdown.marp.themes`でテーマを指定可能。

## 背景画像の指定

背景画像は、`backgroundImage`で指定します。

```markdown
![bg brightness:0.5](background_img.jpg)
![bg left brightness:0.5](background_img.jpg)
![bg right brightness:0.5](background_img.jpg)
```

## css

先頭でデフォルトテーマを import 可能

```css
@import "default";
```
