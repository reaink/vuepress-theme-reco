---
title: Comment
date: 2021-11-06 23:41:31
---

## Introduction

The theme built-in comment plugin `@vuepress-reco/vuepress-plugin-comments`, currently only supports `Valine`, because `Vssue` has not yet adapted to `Vue3`;

If you want to not load comments by default, but only display comments on certain pages, you can set `hideComments: true` in `valineConfig`, and set `hideComments: false` on pages that need to display comments.

If it is only a certain article that you don't want to enable comments, you can set `hideComments: true` in `front-matter`.

## Option API

### Valine

```ts
// .vuepress/config.ts

import { defineUserConfig } from 'vuepress'
import { recoTheme } from 'vuepress-theme-reco'

export default defineUserConfig({
  theme: recoTheme({
    commentConfig: {
      type: 'valine',
      options: {
        appId: '...', // your appId
        appKey: '...', // your appKey
        hideComments: true, // hide comments globally, default false
      },
    },
  }),
})
```

For other parameters, please refer to [Valine official website](https://valine.js.org/configuration.html).
::: tip
If valine's interface for getting comments reports a `404` error, don't worry, this is because you haven't added a comment, as long as there is 1 comment, no error will be reported, this is just the request processing operation of `leanCloud`;
:::

### Waline

```ts
// .vuepress/config.ts

import { defineUserConfig } from 'vuepress'
import { recoTheme } from 'vuepress-theme-reco'

export default defineUserConfig({
  theme: recoTheme({
    commentConfig: {
      type: 'waline',
      options: {
        serverURL: 'your serverURL',
      },
    },
  }),
})
```

Refer to [Waline official website](https://waline.js.org/guide/get-started.html) for the tutorial and other parameters of options.