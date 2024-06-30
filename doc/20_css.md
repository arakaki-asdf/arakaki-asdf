
# CSS設計
CSSは常にすべてのページで読み込まれ、増えれば増えるほど相互に上書きし合う
状態が起きやすく、他の言語に比べてかなり壊れやすい言語と言えます


そこで設計によってCSSを管理し壊れにくくすることを目標としています。

## スコープ付きcss

`scoped`属性をもつ`<style>`タグを利用するとき、そのCSSは現在のコンポーネントの要素にのみ適用されます。これはShadow DOMのスタイルのカプセル化に似ています。

例)
```css
<style scoped>
    .example {
        color: red;
    }
</style>

<template>
    <div class="example">hi</div>
</template>
```
以下の通りになります

```css
<style>
.example[data-v-f3f3eg9] {
    color: red;
}
</style>

<template>
    <div class="example" data-v-f3f3eg9>hi</div>
</template>
```

つまり
```css
<style>
    /* グローバルスタイル */
</style>

<style scoped>
    /* ローカルスタイル */
</style>
```
を意味することができます。

`scoped`によって、親コンポーネントのスタイルは子コンポーネントにもれません。
ただし、子コンポーネントのルートノードは親スコープのCSSと子コンポーネントのCSSの両方によって影響を受けます。これは設計上、親親はレイアウトが目的で子のルート要素をスタイルすることができます。
