---
title: "Chromeの拡張機能開発の初心者"
emoji: "✨"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["chrome","chrome拡張"]
published: false
---

# Chrome拡張機能
Chrome拡張機能って作成できるんだってことを最近知ったので、Chrome拡張機能を作る簡単な方法を説明します！

# 例：zennの背景色を赤にする拡張機能を作る！
まずは拡張機能用`zenn`のフォルダを作って、その中に`manifest.json`と`style.css`を作ります。

```
zenn
├─ manifest.json
└─ style.css
```

`manifest.json`には設定を書きます.

```json
{
    "manifest_version": 3,
    "name": "zenn background",
    "version": "1.0.0",
    "description": "zennの背景色をキモくする",
    "content_scripts": [
      {
        "matches": ["https://zenn.dev/*"],
        "css": ["style.css"]
      }
    ]
}
```

`style.css`には見た目の変更点を書きます。

```css
* {
    background-color: red;
}
```

これで[chrome://extensions/](chrome://extensions/)にアクセスしましょう！

![](/images/chrome-extensinon-first/first.png)

デベロッパーモードをオンにして、パッケージ化されていない拡張機能を読み込むを押して、拡張機能を作成したフォルダを読み込みます！

zennにアクセスしてみたら。。。
![](/images/chrome-extensinon-first/2.png)

背景色が赤になってますね！完成です！