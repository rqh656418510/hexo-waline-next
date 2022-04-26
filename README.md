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
# Waline
# For more information: https://waline.js.org, https://github.com/walinejs/waline
waline:
  enable: false
  serverURL: https://waline.vercel.app # Waline server address url
  placeholder: Just go go # Comment box placeholder
  meta: [nick, mail, link] # Custom comment header
  pageSize: 10 # Pagination size
  lang: # Language, available values: en, zh-cn
  # Warning: Do not enable both `waline.visitor` and `leancloud_visitors`.
  visitor: false # Article reading statistic
  comment_count: true # If false, comment count will only be displayed in post page, not in home page
  requiredMeta: [] # Set required fields: [nick] | [nick, mail]
  qiniuDebug: false # print the error message of the picture uploaded by qiniu
  qiniuDomain: # The custom domain for qiniu, e.g https://qiniu.example.cn
  qiniuTokenUrl: # The api to get qiniu upload token, e.g https://api.example.cn/qiniu/sdk/token/upload
  allowUploadImage: true # Allow upload picture
```

## Qiniu Upload Token API Return Data Description

``` json
{
    "data": "tdvdhnpSs2JFt8U9-c9hL74ddWtEj",
    "msg": "success"
}
```

| parameter name | type   | value                         | explain                                                                                                                                              |
| -------------- | ------ | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| status code    | Number | 200                           | http status code, 200 returned successfully, 403 returned illegal request source, 429 returned too many requests, 500 returned system internal error |
| data           | String | tdvdhnpSs2JFt8U9-c9hL74ddWtEj | the value of upload token                                                                                                                            |
| msg            | String | success                       | message                                                                                                                                              |

## Compatibility

| Plugin version | NexT version |
| -------------- | ------------ |
| 1.0.8          | <= 8.3       |
| 2.0.0+         | >= 8.4       |

## Blog

- [Waline how to upload pictures to qiniu](https://www.techgrow.cn/posts/ae18fb85.html#上传图片至七牛图床)

