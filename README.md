# Hexo Waline NexT

![Theme Version](https://img.shields.io/badge/NexT-v7.3.0+-blue?style=flat-square)
![npm](https://img.shields.io/npm/v/@waline/hexo-next?style=flat-square)

Waline plugin for NexT theme. Waline is a simple, safe comment system inspired by Valine.

## Install

```bash
npm install hexo-waline-next --save
```

## Feature

- upload pictures to [qiniu](https://www.qiniu.com)

## Configure

Set the value `enable` to `true`, add `serverURL`, and edit other configurations in `waline` section in the config file as following. You can config those in both **hexo** or **theme** `_config.yml`:

```yml next/_config.yml
# Waline Config File
# For more information:
# - https://waline.js.org
# - https://waline.js.org/reference/component.html
waline:
  # New! Whether enable this plugin
  enable: false

  # Waline server address url, you should set this to your own link
  serverURL: https://waline.vercel.app

  # Waline library CDN url, you can set this to your preferred CDN
  # libUrl: https://unpkg.com/@waline/client@v2/dist/waline.js

  # Waline CSS styles CDN url, you can set this to your preferred CDN
  # cssUrl: https://unpkg.com/@waline/client@v2/dist/waline.css

  # Custom locales
  # locale:
  #   placeholder: Welcome to comment # Comment box placeholder

  # If false, comment count will only be displayed in post page, not in home page
  commentCount: true

  # Pageviews count, Note: You should not enable both `waline.pageview` and `leancloud_visitors`.
  pageview: false

  # Custom emoji
  # emoji:
  #   - https://unpkg.com/@waline/emojis@1.0.1/weibo
  #   - https://unpkg.com/@waline/emojis@1.0.1/alus
  #   - https://unpkg.com/@waline/emojis@1.0.1/bilibili
  #   - https://unpkg.com/@waline/emojis@1.0.1/qq
  #   - https://unpkg.com/@waline/emojis@1.0.1/tieba
  #   - https://unpkg.com/@waline/emojis@1.0.1/tw-emoji

  # Comment infomation, valid meta are nick, mail and link
  # meta:
  #   - nick
  #   - mail
  #   - link

  # Set required meta field, e.g.: [nick] | [nick, mail]
  # requiredMeta:
  #   - nick

  # Language, available values: en-US, zh-CN, zh-TW, pt-BR, ru-RU, jp-JP
  # lang: zh-CN

  # Word limit, no limit when setting to 0
  # wordLimit: 0

  # Whether enable login, can choose from 'enable', 'disable' and 'force'
  # login: enable

  # comment per page
  # pageSize: 10

  # Display the footer copyright information
  copyright: true

  # Allow upload picture
  allowUploadImage: true

  # Print the error message of the picture uploaded by qiniu
  qiniuDebug: false

  # The custom domain for qiniu
  qiniuDomain: https://qiniu.example.cn

  # The api to get qiniu token
  qiniuTokenUrl: https://api.example.cn/qiniu/sdk/token/upload
```

## Qiniu Token API Return Data Description

``` json
{
    "data": "tdvdhnpSs2JFt8U9-c9hL74ddWtEj",
    "msg": "success"
}
```

| parameter name | type   | value                         | explain                                                                                                                                              |
| -------------- | ------ | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| status code    | Number | 200                           | http status code, 200 returned successfully, 403 returned illegal request source, 429 returned too many requests, 500 returned system internal error |
| data           | String | tdvdhnpSs2JFt8U9-c9hL74ddWtEj | the value of token                                                                                                                                   |
| msg            | String | success                       | message                                                                                                                                              |

## Compatibility

| waline client version | plugin version |
| --------------------- | -------------- |
| <= v1.x               | <= v2.2.9      |
| >= v2.x               | >= v3.x        |

## Blog

- [Waline how to upload pictures to qiniu](https://www.techgrow.cn/posts/ae18fb85.html#上传图片至七牛图床)
