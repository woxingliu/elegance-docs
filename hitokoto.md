# 一言

提供随机的一句话服务，仅用于学习和测试。如果您有非常喜欢并且非常深情的动漫台词，欢迎联系我们添加！

下面是接口说明。

## 随机一言

```http
GET http://api.lolive.top/v2/hitokoto
```

查询参数（Query Params）

| 参数名 | 变量   | 类型   | 必填 | 描述                                                       |
| ------ | ------ | ------ | ---- | ---------------------------------------------------------- |
| 分类   | cat    | string | 否   | 返回指定分类的一言，cat的值只能是【a,b,c,d,e,f,g】其中之一 |
| 长度   | length | int    | 否   | 一言的长度限制                                             |

请求示例

```http
http://api.lolive.top/v2/hitokoto?cat=a&cat=b&cat=c&length=30
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

## 搜索一言

```
POST http://api.lolive.top/v1/hitokoto/search
```

查询参数（Body Params）

| 参数名   | 变量      | 类型   | 必填 | 描述                                                       |
| -------- | --------- | ------ | ---- | ---------------------------------------------------------- |
| 一言     | hitokoto  | string | 否   | 要搜索的一言内容，可以是短语、单词、拼音                   |
| 分类     | cat       | string | 否   | 返回指定分类的一言，cat的值只能是【a,b,c,d,e,f,g】其中之一 |
| 作者     | author    | string | 否   | 作者                                                       |
| 来源     | source    | string | 否   | 来源                                                       |
| 开始时间 | startDate | string | 否   | 必须是 `2011-10-20 23:04:56`  格式                         |
| 结束时间 | endDate   | string | 否   | 必须是 `2011-10-20 23:04:56`  格式                         |
| 页码     | page      | int    | 否   | 页码                                                       |
| 条       | pageSize  | int    | 否   | 每页的条数                                                 |


请求示例

```json
{
  "hitokoto": "人生",
  "cat": "a",
  "author": "Sai",
  "source": "幸运星",
  "startDate": "2011-10-20 23:04:56",
  "endDate": "2012-10-20 23:04:56",
  "page": 1,
  "pageSize": 10
}
```

返回成功示例

```json
{
    "code": 0,
    "data": {
        "total": 1,
        "list": [
            {
                "id": 1319123096000,
                "hitokoto": "我并不羡慕别人的人生，这就是所谓幸福。",
                "cat": "a",
                "catname": "Anime - 动画",
                "author": "Sai",
                "source": "幸运星",
                "date": "2011-10-20 23:04:56"
            }
        ]
    },
    "msg": ""
}
```
