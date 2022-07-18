# 一言

提供随机的一句话服务，仅用于学习和测试。如果您有非常喜欢并且非常深情的动漫台词，欢迎联系我们添加！

本站并未启用 HTTPS，请勿发送你的任何个人信息，本站也不会保存和统计任何信息。

**Base URL**: `http://api.lolive.top`

## 随机一言

```http
GET /v2/hitokoto
```

查询参数（Query Params）

| 参数名 | 变量   | 类型   | 必填 | 描述                                                       |
| ------ | ------ | ------ | ---- | ---------------------------------------------------------- |
| 分类   | cat    | string | 否   | 返回指定分类的一言，cat的值只能是【a,b,c,d,e,f,g,l】其中之一 |
| 长度   | length | int    | 否   | 一言的长度限制                                             |

请求示例

```http
/v2/hitokoto?cat=a&cat=b&cat=c&length=30
```

返回成功示例

```json
{
  "id": "1318956647000",
  "hitokoto": "我们所过的每个平凡的日常，也许就是连续发生的奇迹。",
  "cat": "a",
  "catname": "Anime - 动画",
  "author": "桜花幻影",
  "source": "日常",
  "date": "2011-10-19 00:50:47"
}
```