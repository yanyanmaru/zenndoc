---
title: "tailwind cssのエラー No utility classes were detected ~の対処法"
emoji: "💬"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["tailwindcss","nextjs"]
published: true
---

# next.jsでnpm run devをしたら〜
npm run devをしたら、今までには見たことのないエラーが出ました。

```
warn - No utility classes were detected in your source files. If this is unexpected, double-check the `content` option in your Tailwind CSS configuration.
warn - https://tailwindcss.com/docs/content-configuration
```

Deepl翻訳してみると
```
warn - ソースファイルにユーティリティクラスが検出されませんでした。これが予期しない場合は、Tailwind CSS設定の`content`オプションを再チェックしてください。
warn - https://tailwindcss.com/docs/content-configuration
```

どうやらソースファイルに１つもtailwindcssのクラスを作っていないことが問題でした。

そのため、適当なところに

```react
<p className='text-red-800'>{todo.name}</p>
```

と足したところ解決しました！

## 参考
https://zenn.dev/hayato94087/articles/038a6b01d60911

https://tailwindcss.com/docs/content-configuration

よくある間違いとしては、tailwind.config.tsのcontentのところのファイルパスが間違ってるパターンみたいです！


私の場合はただ単に１つも使っていないことが問題だったので、あんまり同じパターンの人はいないかもしれませんが、共有させていただきます！