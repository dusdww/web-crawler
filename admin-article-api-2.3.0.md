FORMAT: 1A
HOST: http://192.168.1.138/

# topics-2.3.0

2.3.0 mifan admin API

+ 2018年01月31日
    + 增加文章中心二级列表post相关api描述
    + 增加配置管理-人工辅助相关接口描述

+ 2018年01月25日
    + 增加文章中心相关api描述

#配置管理-人工辅助 API
## 操作对象描述
  + Data
    + boost (double) - 搜索引擎助推数, 值越高排名越靠前
    + trainSample (int) - 是否加入到训练样本集中, 0:否, 1:是
    + categoryId (long) - 人工标注的分类ID

## (PATCH) 后台配置管理-人工辅助更新[/article/admin/Topics/{id}]  

## (GET) 后台文章更新索引[/admin/Index?id={id}]

## (DELETE) 后台文章删除索引[/article/admin/Index/{id}]   

#文章中心二级列表 API

## 操作对象描述
  + Data
    + postType (int) - 1:爬取, 2:机翻, 3:精翻, 4:原创
    + postTypeValue (string) - 类型:精翻, 原创, 机翻, 爬取
    + priority (int) - 机器翻译默认为50, 按翻译质量降序排序
    + title (string) - 主题标题
    + language (int) - 语言 1:英文 2:中文 0:未知
    + content (string) - 内容富文本
    + categories (array) - 分类
    + tags (array) - 标签/关键词/等等
    + features (array) - 特性集合
    + parentId （long）- 父节点
    + creator （long）- 创建者id

## (POST) 后台文章中心二级列表新增[/article/admin/Posts]

## (PATCH) 后台文章中心二级列表更新[/article/admin/Posts/{id}]

## (GET)后台文章中心主题列表 [article/admin/Posts/topic/{id}]
+ Parameters
    + id (long) - topic id

### 查询主题 [GET]
+ Response 200 (application/json)
        {
          "data": [
            {
              "id":3,
              "enabled":1,
              "creator":0,
              "modifier":0,
              "created":"2016-10-12 09:55:39",
              "modified":"2017-04-05 21:19:07",
              "parentId":0,
              "topicId":3,
              "priority":0,
              "language":2,
              "title":"Xone:23",
              "postTypeValue":"爬取",
              "postType":1
            },
            {
              "id":398635,
              "enabled":1,
              "creator":0,
              "modifier":0,
              "created":"2017-01-17 11:27:28",
              "modified":"2017-09-08 16:00:47",
              "parentId":3,
              "topicId":3,
              "priority":0,
              "language":1,
              "title":"Xone:23",
              "postTypeValue":"机翻",
              "postType":2
            }
          ]
        }

## (GET)后台文章中心主题 [article/admin/Posts/{id}]

# 文章中心 API

## 操作对象描述

+ Description
    + topic类型 : [产品|品牌|新闻|评测|直播|美频]
    + post 类型 : [原创|爬取|精翻|机翻]
    + forumId = [1], 有product数据;
    + forumId = [3|4|5], 有document数据;
    + forumId = [6], 有tune数据;

+ Data
    + enabled (int) - 逻辑删除标志, 1:启用 0:禁用
    + forumId (long) - 版块ID, 1:产品, 2:品牌, 3:新闻, 4:评测, 5:视频, 6:直播, 7:美频. @see forumName
    + forumName (string) - 版块名称, @see forumId
    + topicType (int) - 主题类型, 0:正常, 1:置顶, 2:公告. @see topicTypeValue
    + topicTypeValue (String) - 主题类型值, @see topicType
    + reviews (int) - 检阅数/浏览数
    + replies (int) - 评论数
    + thumbsUp (int) - 喜欢数
    + thumbsDown (int) - 不喜欢数
    + thumbs (int) - thumbsUp 减去 thumbsDown
    + locked (int) - _保留字段_, 是否锁定, 0:否,1:是, 被锁定主题不能被评论
    + moderated (int) - _保留字段_, 是否审核此主题, 0:否, 1:是
    + imageSingle (boolean) - 是否是单图
    + imageRotation (boolean) - 是否有旋转图
    + liked (int) - -1:踩, 0:无, 1:赞
    + favorite (int) - 0:否, 1:已加入收藏
    + rotations (array) - 旋转图集合
    + images (array) - 图片集合
    + audios (array) - 音频集合
    + videos (array) - 视频集合
    + from (object, nullable) - 来源
    + from.seedId (int) - 种子ID
    + from.origin (int) - 数据来源URL
    + from.rating (double, nullable) - 爬取的评分 区间[0, 1]
    + from.reviews (int, nullable) - 爬取的浏览数 区间[0, 1]
    + from.host (string) - 网站地址
    + from.source (string) - 来源名称
    + from.image (string) - 来源名称
    + from.channelId (string) - 频道ID
    + product (object, nullable) - 产品相关数据;
    + product.price (decimal, nullable) - [MUST]Authenticated, 价格
    + product.priceUnit (string, nullable) - [MUST]Authenticated, 价格单位编码 e.g : USD
    + product.priceSign (string, nullable) - [MUST]Authenticated, 价格单位符号 e.g : $
    + product.brand (string, nullable) - 品牌名称
    + product.brandInfo (object, nullable) - 品牌详细
    + product.brandInfo.name (string) - 品牌名称
    + product.brandInfo.logo (string) - 品牌LOGO
    + product.brandInfo.rating (int) - 品牌评分 区间[0, 1]
    + product.brandInfo.reviews (int) - 品牌浏览数 区间[0, 1]
    + product.brandInfo.top (boolean) - true: 品牌有详情, false: 无详情
    + product.histories (array) - [MUST]Authenticated, 品牌历史价格
    + product.histories.price (decimal) - 价格
    + product.histories.effectiveDate (date) - 生效时间
    + topicsBrand(object, nullable) - 品牌相关数据;
    + topicsBrand.id(long) - 品牌id
    + topicsBrand.topicId(long) - 关联的topicId
    + topicsBrand.logo(string) - 品牌LOGO
    + document (object, nullable) - 新闻和评测相关数据;
    + document.postDate (date, nullable) - 文章发表时间
    + document.author (string, nullable) - 文章作者
    + document.brands (array) - 文章关联的品牌
    + tune (object, nullable) - 美频相关数据;
    + tune.id (long) -  美频id
    + tune.topicId (long) - 关联的topicId
    + tune.type (long) - 美频文章类型, 1:产品, 2:品牌, 3:新闻, 4:评测, 5:视频, 6:直播, 7:美频.
    + tune.name (string) - 段标题名称, 别名
    + tune.brand (string, nullable) - 品牌名称
    + tune.download (string) - 下载地址
    + post (object) - 内容文本数据; 标题, 摘要, 参数, 内容等.
        + 优先级: 精翻|原创 > 机翻 > 爬取
    + post.postType (int) - 1:爬取, 2:机翻, 3:精翻, 4:原创
    + post.postTypeValue (string) - 类型:精翻, 原创, 机翻, 爬取
    + post.priority (int) - 机器翻译默认为50, 按翻译质量降序排序
    + post.title (string) - 主题标题
    + post.language (int) - 语言 1:英文 2:中文 0:未知
    + post.description (string, nullable) - 摘要/描述
    + post.content (string， nullable) - 内容富文本
    + post.categories (array) - 分类, 有可能是机器学习出来的
    + post.tags (array) - 标签/关键词/等等
    + post.features (array) - 特性集合
    + post.parentId （long）- 父节点
    + post.creator （long）- 创建者id
        + 如果creator==0 parentId==0 则文章为爬取
        + 如果creator!=0 parentId==0 则文章为原创
        + 如果creator==0 parentId!=0 则文章为机翻
        + 如果creator!=0 parentId!=0 则文章为精翻
    + post.parent (object) - post的parent节点
        + 如果post是[机翻|精翻], 那么post.parent指向其原文节点
    + similarities (array) - 排重后的相同主题数据;
        + 如果该topic是clustering数据, 会返回相同数据来源不同的topics

## (POST) 后台文章中心新增[article/admin/Topics]
+ Parameters
  + 注意事项
    + seedId
    + creator
    + post.parentId

## (DELETE) 后台文章中心删除[article/admin/Topics/{id}]
+ Parameters
    + id (long) - topic id

### 删除主题 (DELETE)
+ Response 204 (application/json)
+ Response 400 (application/json)
        {
            "errors": [
                {
                    "status": "400",
                    "code": "应用程序code编码",
                    "title": "Bad Request",
                    "detail": "错误信息描述"
                }
            ]
        }

## (POST) 后台文章中心修改[article/admin/Topics]

## (GET)后台文章中心主题 [article/admin/Topics/{id}]
+ Parameters
    + id (long) - topic id

### 查询主题 [GET]
+ Response 200 (application/json)

        {
            "data": {
                "id": 49226,
                "creator": 0,
                "modifier": 0,
                "created": "2016-10-18 07:10:16",
                "modified": "2017-04-05 13:55:33",
                "forumId": 1,
                "topicType": 0,
                "reviews": 0,
                "replies": 0,
                "thumbsUp": 0,
                "thumbsDown": 0,
                "thumbs": 0,
                "locked": 0,
                "moderated": 0,
                "forumName": "产品",
                "topicTypeValue": "正常",
                "imageSingle": false,
                "imageRotation": true,
                "liked": 1,
                "favorite": 1,
                "rotations": [
                    {
                        "mime": "image/jpeg",
                        "filename": "http://static.budee.com/yyren/image/79/18/1199986.jpg"
                    },
                    {
                        "mime": "image/jpeg",
                        "filename": "http://static.budee.com/yyren/image/79/18/1199987.jpg"
                    }
                ],
                "images": [
                    {
                        "mime": "image/jpeg",
                        "filename": "http://static.budee.com/yyren/image/176/4/307350.jpg"
                    },
                    {
                        "mime": "image/jpeg",
                        "filename": "http://static.budee.com/yyren/image/176/4/307351.jpg"
                    }
                ],
                "audios": [],
                "videos": [],
                "from": {
                    "id": 49226,
                    "seedId": 11,
                    "origin": "https://www.thomann.de/gb/rode_nt2a_studio_solution_set.htm",
                    "rating": 0.94,
                    "reviews": 0,
                    "host": "https://www.thomann.de/gb/cat_brands.html",
                    "source": "Thomann"
                },
                tune: {
                  id: 34,
                  topicId: 634051,
                  type: 3,
                  name: "",
                  download: ""
                },
                "document": {
                    "postDate": "2017-07-07",
                    "author": "作者",
                    "brands": [
                        "2Box",
                        "EV",
                        "Yamaha"
                    ]
                },
                "product": {
                    "id": 49226,
                    "topicId": 49226,
                    "price": 329,
                    "priceUnit": "USD",
                    "priceSign": "$"
                    "brand": "Rode",
                    "histories": [
                        {
                            "price": 329,
                            "effectiveDate": "2017-03-23"
                        },
                        {
                            "price": 299,
                            "effectiveDate": "2016-12-22"
                        },
                        {
                            "price": 299,
                            "effectiveDate": "2016-11-04"
                        },
                        {
                            "price": 339,
                            "effectiveDate": "2016-10-19"
                        },
                        {
                            "price": 339,
                            "effectiveDate": "2016-10-18"
                        }
                    ]
                },
                topicsBrand: {
                  id: 2074,
                  topicId: 400706,
                  logo: "https://thumbs.static-thomann.de/thumb/thumb200x/pics/herstlogos/accent_on_music.jpg"
                },
                "post": {
                    "id": 49226,
                    "parent": null,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2016-10-18 07:10:16",
                    "modified": "2017-04-05 13:55:33",
                    "parentId": 0,
                    "postTypeValue": "爬取",
                    "topicId": 49226,
                    "priority": 0,
                    "title": "NT2-A Studio Solution Set",
                    "description": "",
                    "content": "",
                    "categories": [
                        "Microphones",
                        "Large-diaphragm Mics"
                    ],
                    "tags": [
                        "256707"
                    ],
                    "features": [
                        {
                            "_name": "Media",
                            "_value": "<div></div>"
                        },
                        {
                            "_name": "Category",
                            "_value": "<a href=\"https://www.thomann.de/gb/large_diaphragm_mics.html\">Large-diaphragm Microphones</a>"
                        }
                    ]
                }
            }
        }

## (GET)搜索文章中心列表 [/article/admin/Topics]
+ Parameters
    + 过滤参数
      + filter[title] (string, nullable) - 按标题搜索
      + filter[categoryId] (int, nullable) - 按类别ID别过滤
      + filter[forumId] (int, nullable) - 按版块过滤;
      + filter[topicType] (int, nullable) - 主题类型过滤
      + filter[created:gt] - 查找大于指定时间的新数据, 时间格式yyyy-MM-dd HH:mm:ss
      + filter[enabled] (int, nullable) - 按启用/禁用过滤

    + 排序参数
        + sort=-created - 按主题创建时间降序排序
        + sort=-modified - 按主题修改时间降序排序

    + 分页参数
        + page[size] (int) - 页数
        + page[number] (int) - 页号

### 查询主题列表 [GET]
+ 查询产品中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=1&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1

+ 查询品牌中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=2&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1

+ 查询新闻中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=3&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1    

+ 查询评测中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=4&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1

+ 查询视频中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=5&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1    

+ 查询直播中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=6&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1

+ 查询美频中心列表,按创建时间降序排序,只看未删除的数据
    +
    /article/admin/Topics?filter[forumId]=7&page[size]=10&page[number]=1&sort=-created&filter[enabled]=1
