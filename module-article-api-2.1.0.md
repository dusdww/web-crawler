FORMAT: 1A
HOST: http://192.168.1.138/

# 米饭平台2.1.0
+ 2017年11月28日
    + 增加产品分类
    
+ 2017年11月23日
    + 增加索引管理API
        + 增加或重建topics索引API
        + 删除topics索引API

+ 2017年11月14日
    + 增加获取模型状态列表的API

+ 2017年11月8日
    + 增加模型管理相关API
        + 添加模型
        + 修改模型
        + 设置主模型, 即修改模型的优先级
        + 训练模型
        + 查看详情, 过滤列表等等

+ 2017年11月7日
    + 增加调度中心管理相关API
        + 增加调度任务
        + 删除调度任务
        + 修改调度任务(运行任务, 停止任务, 修改定时表达式等)
        + 查询任务列表与状态等信息

+ 2017年11月1日
    + 新增类别相关API

+ 2017年10月31日
    + 新增种子相关API
## (GET) [/article/forumCategories]

### 显示产品分类列表 [GET]

+ Description
    + 查询一级列表参数 filter[parentId]=0&filter[forum_id]=1&sort=-displayOrder&page[size]=16

+ Field
    + name (string) - 状态名称
    + forumId (long) - 版块ID
    + rootId (long) - 根节点ID
    + parentId (long) - 父节点ID
    + title (string) - 标题
    + filename (string) - 附件名称
    + path (string) - 面包屑路径
    + depth (int) - 深度
    + leaf (int) - 是否是叶子节点
    + displayOrder (long) - 显示顺序 数值越大越靠前 默认为0
    + titleChinese (string) - 标题中文
    
+ Parameters
    + parentId (int) - 过滤条件,父级分类id 0：根
    + forum_id(int) - 过滤条件, 1： 产品
    + displayOrder - 排序字段
    
+ Response 200 (application/json) 
```
{
    "meta": {
        "totalPages": 2,
        "totalElements": 17,
        "size": 16,
        "number": 1,
        "numberOfElements": 16,
        "first": true,
        "last": false,
        "sort": [
            {
                "direction": "DESC",
                "property": "display_order",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
            }
        ]
    },
    "links": {
        "self": "/article/forumCategories?filter[parentId]=0&filter[forum_id]=1&sort=-displayOrder&page[number]=1&page[size]=16",
        "first": "/article/forumCategories?filter[parentId]=0&filter[forum_id]=1&sort=-displayOrder&page[number]=1&page[size]=16",
        "next": "/article/forumCategories?filter[parentId]=0&filter[forum_id]=1&sort=-displayOrder&page[number]=2&page[size]=16",
        "last": "/article/forumCategories?filter[parentId]=0&filter[forum_id]=1&sort=-displayOrder&page[number]=2&page[size]=16"
    },
    "data": [
        {
            "id": 2151,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "forumId": 1,
            "rootId": 2151,
            "parentId": 0,
            "title": "Sheet Music, Books, CDs and DVDs",
            "filename": "",
            "path": "2151",
            "depth": 1,
            "leaf": 1,
            "displayOrder": 250000,
            "titleChinese": "歌单/书/CD/DVD"
        },
        {
            "id": 1909,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:13:07",
            "modified": "2017-10-31 17:13:07",
            "forumId": 1,
            "rootId": 1909,
            "parentId": 0,
            "title": "Wind Instruments",
            "filename": "",
            "path": "1909",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 240000,
            "titleChinese": "管乐器"
        },
        {
            "id": 1684,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:12:49",
            "modified": "2017-10-31 17:12:49",
            "forumId": 1,
            "rootId": 1684,
            "parentId": 0,
            "title": "Traditional",
            "filename": "",
            "path": "1684",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 230000,
            "titleChinese": "传统乐器"
        },
        {
            "id": 1522,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:12:35",
            "modified": "2017-10-31 17:12:35",
            "forumId": 1,
            "rootId": 1522,
            "parentId": 0,
            "title": "Studio Equipment",
            "filename": "",
            "path": "1522",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 220000,
            "titleChinese": "演播室设备"
        },
        {
            "id": 1473,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:12:32",
            "modified": "2017-10-31 17:12:32",
            "forumId": 1,
            "rootId": 1473,
            "parentId": 0,
            "title": "Software",
            "filename": "",
            "path": "1473",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 210000,
            "titleChinese": "软件"
        },
        {
            "id": 1315,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:12:12",
            "modified": "2017-10-31 17:12:12",
            "forumId": 1,
            "rootId": 1315,
            "parentId": 0,
            "title": "PA Equipment",
            "filename": "",
            "path": "1315",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 200000,
            "titleChinese": "专业扩声"
        },
        {
            "id": 1179,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:11:53",
            "modified": "2017-10-31 17:11:53",
            "forumId": 1,
            "rootId": 1179,
            "parentId": 0,
            "title": "Microphones",
            "filename": "",
            "path": "1179",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 190000,
            "titleChinese": "麦克风"
        },
        {
            "id": 984,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:11:22",
            "modified": "2017-10-31 17:11:23",
            "forumId": 1,
            "rootId": 984,
            "parentId": 0,
            "title": "Lighting + Stage",
            "filename": "",
            "path": "984",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 180000,
            "titleChinese": "照明+舞台"
        },
        {
            "id": 831,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:10:56",
            "modified": "2017-10-31 17:10:57",
            "forumId": 1,
            "rootId": 831,
            "parentId": 0,
            "title": "Keys",
            "filename": "",
            "path": "831",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 170000,
            "titleChinese": "键盘"
        },
        {
            "id": 604,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:09:54",
            "modified": "2017-10-31 17:09:54",
            "forumId": 1,
            "rootId": 604,
            "parentId": 0,
            "title": "Guitars and Basses",
            "filename": "",
            "path": "604",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 160000,
            "titleChinese": "吉他和贝司"
        },
        {
            "id": 560,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:09:47",
            "modified": "2017-10-31 17:09:47",
            "forumId": 1,
            "rootId": 560,
            "parentId": 0,
            "title": "Effects + Signal Proc.",
            "filename": "",
            "path": "560",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 150000,
            "titleChinese": "效果器/处理器"
        },
        {
            "id": 391,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:09:18",
            "modified": "2017-10-31 17:09:18",
            "forumId": 1,
            "rootId": 391,
            "parentId": 0,
            "title": "Drums + Percussion",
            "filename": "",
            "path": "391",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 140000,
            "titleChinese": "鼓+打击乐器"
        },
        {
            "id": 323,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:08:43",
            "modified": "2017-10-31 17:08:43",
            "forumId": 1,
            "rootId": 323,
            "parentId": 0,
            "title": "DJ Equipment",
            "filename": "",
            "path": "323",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 130000,
            "titleChinese": "DJ设备"
        },
        {
            "id": 258,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:08:33",
            "modified": "2017-10-31 17:08:33",
            "forumId": 1,
            "rootId": 258,
            "parentId": 0,
            "title": "Cases",
            "filename": "",
            "path": "258",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 120000,
            "titleChinese": "箱/包"
        },
        {
            "id": 131,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2017-10-31 17:08:15",
            "modified": "2017-10-31 17:08:15",
            "forumId": 1,
            "rootId": 131,
            "parentId": 0,
            "title": "Cables + Plugs",
            "filename": "",
            "path": "131",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 110000,
            "titleChinese": "线缆"
        },
        {
            "id": 1,
            "enabled": 1,
            "creator": 0,
            "modifier": 11,
            "created": "2017-10-31 17:07:52",
            "modified": "2017-11-01 13:16:01",
            "forumId": 1,
            "rootId": 1,
            "parentId": 0,
            "title": "Accessories",
            "filename": "“”",
            "path": "1",
            "depth": 1,
            "leaf": 0,
            "displayOrder": 100000,
            "titleChinese": "配件"
        }
    ]
}
```


### 新增索引 [POST]

+ Request (application/json)

        {
            "data": {
                "id": 1,
                "array": [
                    1,
                    2
                ],
                "start": 1,
                "end": 2
            }
        }

+ Response 200 (application/json)

        {
            "data": "some information"
        }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }
        
## (DELETE)  [/article/topics/index/{id}]

+ Description
    + [MUST] ROLE_ADMIN

+ Parameters
    + id (long) - topic ID

### 删除主题索引 [DELETE]

+ Response 200 (application/json)

        {
            "data": {
                "context": {
                    "empty": true
                },
                "headers": [],
                "shardInfo": {
                    "total": 2,
                    "successful": 1,
                    "failures": [],
                    "failed": 0
                },
                "index": "topic-0928",
                "id": "1",
                "type": "post",
                "version": 24,
                "found": true,
                "contextEmpty": true
            }
        }

+ Response 204 (application/json)    
    
## (GET) 分类模型状态集合 [/article/topicsModel/modelStatus?filter[type]={type}]

+ Description
    + [MUST] ROLE_ADMIN
    + 不写filter就查询全部的枚举类型

+ Field
    + name (string) - 状态名称
    + value (string) - 状态值

+ Parameters
    + type (enum, nullable) - 过滤条件, MANUAL:人工类型(可修改), AUTO:自动类型(不可修改)

### 查询分类模型的枚举状态类型列表 [GET]

+ Response 200 (application/json)

        {
            "data": [
                {
                    "name": "训练",
                    "value": "RUNNABLE"
                },
                {
                    "name": "分类",
                    "value": "CLASSIFICATION"
                }
            ]
        }

## (POST|GET) 分类模型 [/article/topicsModel]

+ Description
    + [MUST] ROLE_ADMIN
    + [POST] 新增暂时只需要以下字段
        + forumId
        + modelName

+ Field
    + id (long) - 模型ID
    + forumId (long) - 版块ID
    + modelName (string) - 模型名称, 全局应该唯一
    + modelStatus (string) - 模型状态枚举
    + modelStatusValue (string) - 模型状态枚举中文描述
    + priority (int) - 模型优先级, 取值[0,100]
    + confRandomSelection (int) - [5, 50] 测试数据占样本数据百分比
    + confOverwrite (int) - 是否覆盖 0:否, 1:是
    + resultSamples (int) - 模型样本总数
    + resultText (string, nullable) - 模型分析结果数据或一样信息

+ Meta
    + number (int) - 当前页
    + size (int) - 每页大小
    + numberOfElements (int) - 当前页有多少记录
    + last (boolean) - 是否是最后一页
    + totalPages (int) - 总页数
    + sort (object) - 排序相关信息
    + first (boolean) - 是否是第一页
    + totalElements - 总记录数

### 新增分类模型 [POST]

+ Request (application/json)

        {
            "data": {
                "forumId": 1,
                "modelName": "topic-1"
            }
        }

+ Response 201 (application/json)

    + Headers

            Location: /article/topicsModel/1

    + Body

            {
                "data": {
                    "id": 1,
                    "type": "topicsModel"
                }
            }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }

### 查询分类模型列表 [GET]

+ Response 200 (application/json)

        {
            "meta": {
                "totalPages": 1,
                "totalElements": 1,
                "size": 10,
                "number": 1,
                "numberOfElements": 1,
                "first": true,
                "last": true,
                "sort": null
            },
            "links": {
                "self": "/article/topicsModel?page[number]=1&page[size]=10",
                "first": "/article/topicsModel?page[number]=1&page[size]=10",
                "last": "/article/topicsModel?page[number]=1&page[size]=10"
            },
            "data": [
                {
                    "id": 1,
                    "enabled": 1,
                    "creator": 11,
                    "modifier": 11,
                    "created": "2017-11-08 16:26:38",
                    "modified": "2017-11-08 16:32:10",
                    "forumId": 1,
                    "modelStatus": "RUNNABLE",
                    "modelName": "topic-2",
                    "priority": 0,
                    "confRandomSelection": 20,
                    "confOverwrite": 1,
                    "resultSamples": 0,
                    "modelStatusValue": "模型训练中"
                }
            ]
        }
        
## (GET|DELETE|PATCH) 分类模型  [/article/topicsModel/{id}]

+ Description
    + [MUST] ROLE_ADMIN
    + [PATCH] 后台对修改模型做了如下限制, 强制修改会返回错误提示信息
        + modelName 模型名称不能修改
        + forumId 不能修改
        + modelStatus 状态为RUNNABLE的模型不能修改
    + 执行训练模型
        + 将状态修改为RUNNABLE

+ Parameters
    + id (long) - 模型ID

### 查询分类模型详情 [GET]

+ Response 200 (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "creator": 11,
                "modifier": 11,
                "created": "2017-11-08 16:26:38",
                "modified": "2017-11-08 16:26:38",
                "forumId": 1,
                "modelStatus": "NEW",
                "modelName": "topic-1",
                "priority": 0,
                "confRandomSelection": 20,
                "confOverwrite": 1,
                "resultSamples": 0,
                "modelStatusValue": "新建"
            }
        }

### 删除分类模型 [DELETE]

+ Response 204 (application/json)

### 修改分类模型 [PATCH]

+ Request (application/json)

        {
            "data": {
                "priority": 22,
                "modelStatus": "RUNNABLE"
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)

## (POST|GET)爬虫种子网站 [/article/seeds]

+ Description
    + [MUST] ROLE_ADMIN

+ Field
    + url (string) - 种子URL
    + source (string) - 种子来源名称/简称
    + conf (string) - 种子配置, JSON格式的大文本
    + name (string, nullable) - 类型名称 e.g products产品 | brands品牌
    + agencyIp (string, nullable) - 代理IP
    + agencyIpPort (string, nullable) - 代理端口
    + charset (string, nullable) - 字符集你
    + description (string, nullable) - 种子描述
    + language (string) - 语言 1:中文, 2英文

+ Meta
    + number (int) - 当前页
    + size (int) - 每页大小
    + numberOfElements (int) - 当前页有多少记录
    + last (boolean) - 是否是最后一页
    + totalPages (int) - 总页数
    + sort (object) - 排序相关信息
    + first (boolean) - 是否是第一页
    + totalElements - 总记录数

### 新增种子 [POST]

+ Request (application/json)

        {
            "data": {
                "url": "https://www.sweetwater.com/store/detail/KM183",
                "source": "Sweetwater",
                "conf": "{}",
                "name": "products",
                "agencyIp": "192.168.1.234",
                "agencyIpPort": 9000,
                "charset": "UTF-8",
                "description": "甜水网",
                "language": 1
            }
        }

+ Response 201 (application/json)

    + Headers

            Location: /article/seeds/1

    + Body

            {
                "data": {
                    "id": 1,
                    "type": "seeds"
                }
            }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }

### 查询种子列表 [GET]

+ Response 200 (application/json)

        {
            "meta": {
                "totalPages": 8,
                "totalElements": 74,
                "size": 10,
                "number": 1,
                "numberOfElements": 10,
                "first": true,
                "last": false,
                "sort": null
            },
            "links": {
                "self": "/article/seeds?page[number]=1&page[size]=10",
                "first": "/article/seeds?page[number]=1&page[size]=10",
                "next": "/article/seeds?page[number]=2&page[size]=10",
                "last": "/article/seeds?page[number]=8&page[size]=10"
            },
            "data": [
                {
                    "id": 1,
                    "enabled": 0,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2016-06-16 10:29:36",
                    "modified": "2017-10-31 09:57:01",
                    "url": "http://www.music123.com/browse/shopByBrand/shopByBrand.jsp",
                    "source": "Music123",
                    "conf": "",
                    "name": "products",
                    "description": "Music123",
                    "rank": 500,
                    "updateRate": 1,
                    "language": 2
                },
                {
                    "id": 2,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "url": "https://www.sweetwater.com/store/detail/KM183",
                    "source": "Sweetwater",
                    "conf": "",
                    "name": "products",
                    "description": "甜水网",
                    "rank": 0,
                    "updateRate": 1,
                    "language": 2
                },
                {
                    "id": 3,
                    "enabled": 0,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2016-06-22 10:29:36",
                    "modified": "2016-06-22 10:29:36",
                    "url": "http://www.guitarcenter.com",
                    "source": "Guitar Center",
                    "conf": "",
                    "name": "products",
                    "description": "GuitarCenter",
                    "rank": 400,
                    "updateRate": 1,
                    "language": 2
                }
            ]
        }

## (GET|DELETE|PATCH)爬虫种子网站 [/article/seeds/{id}]

+ Description
    + [MUST] ROLE_ADMIN

+ Parameters
    + id (long) - 种子ID

### 查询种子详情 [GET]

+ Response 200 (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 0,
                "creator": 0,
                "modifier": 0,
                "created": "2016-06-16 10:29:36",
                "modified": "2017-10-31 09:57:01",
                "url": "http://www.music123.com/browse/shopByBrand/shopByBrand.jsp",
                "source": "Music123",
                "conf": "",
                "name": "products",
                "description": "Music123",
                "rank": 500,
                "updateRate": 1,
                "language": 2
            }
        }

### 删除种子 [DELETE]

+ Response 204 (application/json)

### 修改种子[PATCH]

+ Request (application/json)

        {
            "data": {
                "url": "https://www.sweetwater.com/store/detail/KM183",
                "source": "Sweetwater",
                "conf": "{}",
                "name": "products",
                "agencyIp": "192.168.1.234",
                "agencyIpPort": 9000,
                "charset": "UTF-8",
                "description": "甜水网",
                "language": 1
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)

## (POST|GET)类别 [/article/forumCategories]

+ Description
    + [MUST] ROLE_ADMIN

+ Field
    + forumId (long) - forum ID
    + parentId (long) - 父节点ID
    + title (string) - 类别名称
    + displayOrder (int, nullable) - 排序字段, 可选

+ Meta
    + number (int) - 当前页
    + size (int) - 每页大小
    + numberOfElements (int) - 当前页有多少记录
    + last (boolean) - 是否是最后一页
    + totalPages (int) - 总页数
    + sort (object) - 排序相关信息
    + first (boolean) - 是否是第一页
    + totalElements - 总记录数

### 新增类别 [POST]

+ Request (application/json)

        {
            "data": {
                "forumId": 1,
                "parentId": 2147,
                "title": "吉他和贝斯",
                "displayOrder": 0
            }
        }

+ Response 201 (application/json)

    + Headers

            Location: /article/forumCategories/1

    + Body

            {
                "data": {
                    "id": 1,
                    "type": "forumCategories"
                }
            }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }

### 查询类别列表 [GET]

+ Response 200 (application/json)

        {
            "meta": {
                "totalPages": 215,
                "totalElements": 2143,
                "size": 10,
                "number": 1,
                "numberOfElements": 10,
                "first": true,
                "last": false,
                "sort": null
            },
            "links": {
                "self": "/article/forumCategories?page[number]=1&page[size]=10",
                "first": "/article/forumCategories?page[number]=1&page[size]=10",
                "next": "/article/forumCategories?page[number]=2&page[size]=10",
                "last": "/article/forumCategories?page[number]=215&page[size]=10"
            },
            "data": [
                {
                    "id": 1,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 11,
                    "created": "2017-10-31 17:07:52",
                    "modified": "2017-11-01 13:16:01",
                    "forumId": 1,
                    "rootId": 1,
                    "parentId": 0,
                    "title": "Accessories",
                    "path": "1",
                    "depth": 1,
                    "leaf": 0,
                    "displayOrder": 0
                },
                {
                    "id": 2,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2017-10-31 17:07:52",
                    "modified": "2017-10-31 17:07:52",
                    "forumId": 1,
                    "rootId": 1,
                    "parentId": 1,
                    "title": "Accessories for Mics",
                    "path": "1.2",
                    "depth": 2,
                    "leaf": 0,
                    "displayOrder": 0
                },
                {
                    "id": 3,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2017-10-31 17:07:52",
                    "modified": "2017-11-01 11:46:46",
                    "forumId": 1,
                    "rootId": 1,
                    "parentId": 2,
                    "title": "Booms & Handles",
                    "path": "1.2.3",
                    "depth": 3,
                    "leaf": 1,
                    "displayOrder": 0
                }
            ]
        }        

## (GET|DELETE|PATCH)类别 [/article/forumCategories/{id}]

+ Description
    + [MUST] ROLE_ADMIN
    
+ Field
    + id (long) - 类别ID标识符
    + forumId (long) - forum ID
    + rootId (long) - 根节点ID
    + parentId (long) - 父节点ID
    + title (string) - 类别名称
    + path (string) - 节点路径
    + depth (int) - 深度
    + leaf (int) - 是否是叶子节点 0:否, 1:是
    + displayOrder (int) - 排序字段

+ Parameters
    + id (long) - 类别ID

### 查询类别详情 [GET]

+ Response 200 (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 11,
                "created": "2017-10-31 17:07:52",
                "modified": "2017-11-01 13:16:01",
                "forumId": 1,
                "rootId": 1,
                "parentId": 0,
                "title": "Accessories",
                "path": "1",
                "depth": 1,
                "leaf": 0,
                "displayOrder": 0
            }
        }

### 删除类别 [DELETE]

+ Response 204 (application/json)

### 修改类别[PATCH]

+ Request (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "title": "Accessories",
                "displayOrder": 0
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)

## (POST|GET)双语词典 [/article/wordDictionary]

+ Description
    + [MUST] ROLE_ADMIN

+ Field
    + wordEn (string) - 英文词
    + wordEn (string) - 中文词

+ Meta
    + number (int) - 当前页
    + size (int) - 每页大小
    + numberOfElements (int) - 当前页有多少记录
    + last (boolean) - 是否是最后一页
    + totalPages (int) - 总页数
    + sort (object) - 排序相关信息
    + first (boolean) - 是否是第一页
    + totalElements - 总记录数

### 新增双语词典 [POST]

+ Request (application/json)

        {
            "data": {
                "wordEn": "accessories",
                "wordCn": "配件"
            }
        }

+ Response 201 (application/json)

    + Headers

            Location: /article/wordDictionary/1

    + Body

            {
                "data": {
                    "id": 1,
                    "type": "wordDictionary"
                }
            }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }

### 查询双语词典列表 [GET]

+ Response 200 (application/json)

        {
            "meta": {
                "totalPages": 270,
                "totalElements": 2694,
                "size": 10,
                "number": 1,
                "numberOfElements": 10,
                "first": true,
                "last": false,
                "sort": null
            },
            "links": {
                "self": "/article/wordDictionary?page[number]=1&page[size]=10",
                "first": "/article/wordDictionary?page[number]=1&page[size]=10",
                "next": "/article/wordDictionary?page[number]=2&page[size]=10",
                "last": "/article/wordDictionary?page[number]=270&page[size]=10"
            },
            "data": [
                {
                    "id": 1,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2017-10-31 18:30:30",
                    "modified": "2017-10-31 18:30:30",
                    "wordEn": "accessories",
                    "wordCn": "配件"
                },
                {
                    "id": 2,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2017-10-31 18:30:31",
                    "modified": "2017-10-31 18:30:31",
                    "wordEn": "accessories for mics",
                    "wordCn": "麦克风配件"
                },
                {
                    "id": 3,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2017-10-31 18:30:31",
                    "modified": "2017-10-31 18:30:31",
                    "wordEn": "booms & handles",
                    "wordCn": "吊杆和手柄配件"
                }
            ]
        }
        
## (GET|DELETE|PATCH)双语词典  [/article/wordDictionary/{id}]

+ Description
    + [MUST] ROLE_ADMIN

+ Parameters
    + id (long) - 标识符ID

### 查询双语词典详情 [GET]

+ Response 200 (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2017-10-31 18:30:30",
                "modified": "2017-10-31 18:30:30",
                "wordEn": "accessories",
                "wordCn": "配件"
            }
        }

### 删除双语词典 [DELETE]

+ Response 204 (application/json)

### 修改双语词典 [PATCH]

+ Request (application/json)

        {
            "data": {
                "wordEn": "accessories",
                "wordCn": "配件"
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)

## (PATCH)主题 [/topics/{id}]

+ Description
    + [MUST] ROLE_ADMIN
    + 用于修改影响搜索结果排名的助推数
    + 用于训练时选择的样本集合
    + 用户人工标注类别
    + 一下三个参数通常都是单独在API里进行修改的

+ Field
    + boost (double) - 搜索引擎助推数, 值越高排名越靠前
    + trainSample (int) - 是否加入到训练样本集中, 0:否, 1:是
    + categoryId (long) - 人工标注的分类ID

### 修改主题[PATCH]

+ Request (application/json)

        {
            "data": {
                "boost": 1,
                "trainSample": 1,
                "categoryId": 1
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)

## (POST|GET) 调度任务 [/article/quartzJobs]

+ Description
    + [MUST] ROLE_ADMIN
    + 修改调度任务执行状态
        + RUNNABLE 

+ Field
    + id (long) - 唯一标识符
    + jobName (string) - 任务名称
    + jobClass (string) - 任务策略类全限定名称 
    + jobData (string, nullable) - json格式的任务参数, 不同的策略类有不同的参数
    + triggerName (string) - 触发器名称
    + triggerCronExpression (string) - cron表达式
    + description (string) - 描述,
    + jobStatus (enum) - NEW:新建, SUSPEND:暂停, RUNNABLE:运行中, TERMINATED:终止
        + 新增任务时, 默认都是NEW状态
        + 当修改任务的状态为RUNNABLE时, 加入自动调度管理中心
        + 当修改任务的状态为非RUNNABLE时, 撤销在自动调度中心的任务
        + 前端要有一个控制每个任务状态的按钮以管理任务
        + SUSPEND状态暂时不同考虑, 该枚举为扩展类型
    + jobStatusValue (string) - 对应jobStatus的中文描述值
    + version (int) - 版本号, 修改数据时需要该参数以防止并发修改带来的问题
    + auto (int) - 是否加入到应用启动自动部署中, 0:否, 1:是

+ Meta
    + number (int) - 当前页
    + size (int) - 每页大小
    + numberOfElements (int) - 当前页有多少记录
    + last (boolean) - 是否是最后一页
    + totalPages (int) - 总页数
    + sort (object) - 排序相关信息
    + first (boolean) - 是否是第一页
    + totalElements - 总记录数

### 新增调度任务 [POST]

+ Request (application/json)

        {
            "data": {
                "jobName": "job-3",
                "jobClass": "com.mifan.article.job.SpiderJob",
                "jobData": "{\"seeds\":[1,2,3]}",
                "triggerName": "job-3-trigger",
                "triggerCronExpression": "0/8 * * * * ?",
                "description": "爬虫任务"
            }
        }

+ Response 201 (application/json)

    + Headers

            Location: /article/quartzJobs/1

    + Body

            {
                "data": {
                    "id": 1,
                    "type": "quartzJobs"
                }
            }
            
+ Response 204 (application/json)
        
+ Response 400 (application/json)

        {
            "errors": [
                {
                    "status": "400",
                    "code": "some code",
                    "title": "Bad Request",
                    "detail": "格式错误",
                    "source": {
                        "pointer": "{class} -> {field}"
                    }
                }
            ]
        }

### 查询调度任务列表 [GET]

+ Response 200 (application/json)

        {
            "meta": {
                "totalPages": 1,
                "totalElements": 3,
                "size": 10,
                "number": 1,
                "numberOfElements": 3,
                "first": true,
                "last": true,
                "sort": null
            },
            "links": {
                "self": "/article/quartzJobs?page[number]=1&page[size]=10",
                "first": "/article/quartzJobs?page[number]=1&page[size]=10",
                "last": "/article/quartzJobs?page[number]=1&page[size]=10"
            },
            "data": [
                {
                    "id": 1,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 11,
                    "created": "2017-11-02 16:54:41",
                    "modified": "2017-11-07 10:05:11",
                    "jobStatus": "RUNNABLE",
                    "jobStatusValue": "运行中",
                    "jobGroup": "DEFAULT",
                    "jobName": "job-1",
                    "jobClass": "com.mifan.article.job.SpiderJob",
                    "jobData": "{\"timeout\":8}",
                    "triggerGroup": "DEFAULT",
                    "triggerName": "job-1-trigger",
                    "triggerCronExpression": "0/8 * * * * ?",
                    "version": 22,
                    "auto": 1
                },
                {
                    "id": 2,
                    "enabled": 1,
                    "creator": 11,
                    "modifier": 11,
                    "created": "2017-11-07 11:06:13",
                    "modified": "2017-11-07 11:06:13",
                    "jobStatus": "NEW",
                    "jobStatusValue": "新建",
                    "jobGroup": "DEFAULT",
                    "jobName": "job-2",
                    "jobClass": "com.mifan.article.job.SpiderJob",
                    "jobData": "{\"timeout\":8}",
                    "triggerGroup": "DEFAULT",
                    "triggerName": "job-2-trigger",
                    "triggerCronExpression": "0/8 * * * * ?",
                    "description": "爬虫任务",
                    "version": 0,
                    "auto": 0
                },
                {
                    "id": 3,
                    "enabled": 1,
                    "creator": 11,
                    "modifier": 11,
                    "created": "2017-11-07 11:07:04",
                    "modified": "2017-11-07 11:07:04",
                    "jobStatus": "NEW",
                    "jobStatusValue": "新建",
                    "jobGroup": "DEFAULT",
                    "jobName": "job-3",
                    "jobClass": "com.mifan.article.job.SpiderJob",
                    "jobData": "{\"timeout\":8}",
                    "triggerGroup": "DEFAULT",
                    "triggerName": "job-3-trigger",
                    "triggerCronExpression": "0/8 * * * * ?",
                    "description": "爬虫任务",
                    "version": 0,
                    "auto": 0
                }
            ]
        }
        
## (GET|DELETE|PATCH) 调度中心任务 [/article/quartzJobs/{id}]

+ Description
    + [MUST] ROLA_ADMIN

+ Parameters
    + id (long) - 唯一标识符ID

### 查询调度任务详情 [GET]

+ Response 200 (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 11,
                "created": "2017-11-02 16:54:41",
                "modified": "2017-11-07 10:05:11",
                "jobStatus": "RUNNABLE",
                "jobGroup": "DEFAULT",
                "jobName": "job-1",
                "jobClass": "com.mifan.article.job.SpiderJob",
                "jobData": "{\"timeout\":8}",
                "triggerGroup": "DEFAULT",
                "triggerName": "job-1-trigger",
                "triggerCronExpression": "0/8 * * * * ?",
                "version": 22,
                "auto": 1,
                "jobStatusValue": "运行中"
            }
        }

### 删除调度任务 [DELETE]

+ Response 204 (application/json)

### 修改调度任务 [PATCH]

+ Request (application/json)

        {
            "data": {
                "id": 1,
                "enabled": 1,
                "auto":0
                "version": 21,
                "triggerCronExpression": "0/8 * * * * ?",
                "jobData": "{\"timeout\":8}",
                "jobStatus": "RUNNABLE"
            }
        }
        
+ Response 200 (application/json)

+ Response 204 (application/json)


+ 2017年11月7日
    + API初始化
+ 2018年1月6日
    + 创建任务的时候添加指定翻译人，修改任务时添加修改翻译人
    + 查询结果中添加了翻译人帐号、审核人帐号、修改人帐号、创建人帐号
+ 2018年1月20日
    + 添加tags
    + 任务发起的时候，允许任务发起人给content添加段落标记

## 翻译任务

+ Data
    + topicId (Long) - 主题标识
    + postId (Long) - 翻译标识
    + state (int) - 任务状态，1：待领取，2：未提交，3：待审核，4：审核中，5：审核失败，6：审核成功，7：已支付
    + wordsNum (int) - 单词数
    + wordsNumCn (int) - 中文字数
    + bonus (BigDecimal) - 金额
    + translator (Long) - 翻译人
    + auditor (Long) - 审核人
    + auditOpinion (String) - 审核意见
    + enabled (int) - 是否可用 0/1 ：不可用/可用
    + creator (Long) - 创建人
    + modifier (Long) - 修改人
    + language (int) - 语言 0:缺省, 1:中文, 2英文
    + features (数组) - 属性
    + title (String) - 标题
    + description (String) - 描述
    + content (String) - 内容
    + title (String) - 标题
    + topicType (String) - 文章类型
    + content (String) - 文章内容
    + tags (String[]) - 标签
    + translatorAccount (String) - 翻译人员帐号
    + auditorAccount (String) - 审核人员帐号
    + modifierAccount (String) - 修改人帐号
    + creatorAccount (String) - 创建人帐号

## 审核人员接口
### 开始审核/暂存审核/提交审核结果 [PATCH] /article/translateTasks/auditors/{id}
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AUDITOR
    + 开始审核：审核人员领取审核任务，此时state从3变为4
    + 暂存审核：审核人员暂存审核，此时state从4变为4
    + 提交审核：审核人员提交审核，此时state从4变为5|6
+ Parameters
    + state 必填，开始审核/暂存审核：state=4，提交审核state=5|6
    + wordsNumCn 当state=4|5时不填；当state=6时，可以填写，如果不填则后台计算
    + auditOpinion
    + posts 开始审核-必不填，暂存/提交-必填
    + posts.features
    + posts.title - 必填
    + posts.description
    + posts.content
    + posts.tags

+ 开始审核Request (application/json)

        {
            "data":{
                "state":4
            }
        }
+ 暂存审核/提交审核Request (application/json)
    
        {
            "data":{
                "state":4,
                "auditOpinion":"我草暂存 yi'xia一下 ",
                "posts":{
                    "title":"我草u翻译任务??fan'yi'de翻译的很好",
                    "description":"翻译的很fan'yi翻译 miao'shu描述2222222 ",
                    "content":"翻译的很wo'shi'fan'yi'nei'rong我是翻译内容2222222",
                    "features":[
                                {
                                    "_name":"翻译的很属性2",
                                    "_value":"翻译的很属性2的值"
                                }
                            ],
                    "tags":[
                            "北美","无码"
                        ]
                }
            }
        }
+ Response 20* (application/json)
+ Response 40* (application/json)

### 审核者任务列表 [GET] /article/translateTasks/auditors?filter[state]=3&page[number]=1&page[size]=5
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AUDITOR
+ Parameters
    + filter[state] - 筛选条件，任务状态
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 1,
            "totalElements": 1,
            "size": 5,
            "number": 1,
            "numberOfElements": 1,
            "first": true,
            "last": true,
            "sort": [
              {
                "direction": "DESC",
                "property": "modified",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
              }
            ]
          },
          "links": {
            "self": "/article/translateTask/auditor?filter[state]=4&page[number]=1&page[size]=5",
            "first": "/article/translateTask/auditor?filter[state]=4&page[number]=1&page[size]=5",
            "last": "/article/translateTask/auditor?filter[state]=4&page[number]=1&page[size]=5"
          },
          "data": [
            {
              "id": 4,
              "topicId": 619766,
              "state": 4,
              "wordsNum": 1000,
              "translator": 2425,
              "title": "£1,500 Spector bass stolen from Rimmers Music Blackburn",
              "topicType": "新闻",
              "translatorAccount": "18211021070"
            },
            {
              "id": 1,
              "topicId": 1,
              "state": 4,
              "wordsNum": 10,
              "translator": 1031,
              "title": "Virus TI2 Desktop",
              "topicType": "产品",
              "translatorAccount": "18611194890"
            }
          ]
        }

### 审核者任务详情 [GET] [/article/translateTasks/auditors/{id}]
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AUDITOR

+ Response 200 (application/json)

        {
          "data": {
            "id": 1,
            "enabled": 1,
            "creator": 1031,
            "modifier": 1031,
            "created": "2017-11-07 10:41:56",
            "modified": "2017-11-07 17:18:38",
            "topicId": 1,
            "postId": 1013367,
            "state": 4,
            "wordsNum": 2000,
            "bonus": 100,
            "translator": 1031,
            "auditor": 1031,
            "auditOpinion": "1我草暂存 yi'xia一下 ",
            "post": {
              "id": 1013367,
              "enabled": 0,
              "creator": 1031,
              "modifier": 1031,
              "created": "2017-11-07 15:03:23",
              "modified": "2017-11-07 17:18:38",
              "parentId": 1,
              "topicId": 1,
              "priority": 0,
              "language": 2,
              "categories": [
                "111111111"
              ],
              "tags": [
                "2222222222"
              ],
              "features": [
                {
                  "_name": "翻译的很属性2",
                  "_value": "翻译的很属性2的值"
                }
              ],
              "title": "111111我草u翻译任务??fan'yi'de翻译的很好",
              "description": "1111111翻译的很fan'yi翻译 miao'shu描述2222222 ",
              "content": "1111111翻译的很wo'shi'fan'yi'nei'rong我是翻译内容2222222",
              "parent": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2016-10-12 09:55:37",
                "modified": "2017-10-28 13:33:38",
                "parentId": 0,
                "topicId": 1,
                "priority": 0,
                "language": 2,
                "categories": [
                  "Keyboards & Synthesizers",
                  "Synthesizers"
                ],
                "tags": [
                  "VirusTI2Desk"
                ],
                "features": [
                  {
                    "_name": "Sound Engine Type(s)",
                    "_value": "Analog Modeling"
                  }
                ],
                "title": "Virus TI2 Desktop",
                "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n",
                "postsText": {
                  "id": 1,
                  "category": "Keyboards & Synthesizers,Synthesizers",
                  "tag": "VirusTI2Desk",
                  "title": "Virus TI2 Desktop",
                  "feature": "[{\"_name\":\"Sound Engine Type(s)\",\"_value\":\"Analog Modeling\"}]",
                  "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                  "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n "
                },
                "postType": 1,
                "postTypeValue": "爬取"
              },
              "postsText": {
                "id": 1013367,
                "category": "111111111",
                "tag": "2222222222",
                "title": "111111我草u翻译任务??fan'yi'de翻译的很好",
                "feature": "[{\"_name\":\"翻译的很属性2\",\"_value\":\"翻译的很属性2的值\"}]",
                "description": "1111111翻译的很fan'yi翻译 miao'shu描述2222222 ",
                "content": "1111111翻译的很wo'shi'fan'yi'nei'rong我是翻译内容2222222"
              },
              "postType": 3,
              "postTypeValue": "精翻"
            },
            "title": "Virus TI2 Desktop",
            "topicType": "产品",
            "translatorAccount": "18611194890",
            "auditorAccount": "18611194890"
          }
        }

## 翻译人员接口
### 领取/添加翻译/修改翻译/审核失败后继续翻译 [PATCH] /article/translateTasks/translators/{id}
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AD_USER
    + 领取：翻译人员领取任务，此时state从1变为2
    + 添加/修改：翻译人员领取任务后添加翻译，此时state从2变为2|3，当状态变为3后不再允许修改
    + 审核失败后继续翻译：审核结果失败后可以继续翻译，此时state从5变为2

+ Parameters
    + state 必填，领取/继续时：state=2；添加/修改时：state=2|3
    + post 领取/继续翻译-必不填，添加/修改-必填
    + post.language
    + post.features
    + post.title - 必填
    + post.description
    + post.content
    + posts.tags

+ 领取/审核失败后继续翻译Request (application/json)

        {
            "data":{
                "state":2
            }
        }
+ 添加翻译/修改翻译Request (application/json)

        {
            "data":{
                "state":2,
                "post":{
                    "title":"fan'yi'ren'wu翻译任务222222222 ",
                    "language":2,
                    "description":"fan'yi翻译 miao'shu描述2222222 ",
                    "content":"wo'shi'fan'yi'nei'rong我是翻译内容2222222",
                    "features":[
                                {
                                    "_name":"属性2",
                                    "_value":"属性2的值"
                                }
                            ],
                    "tags":[
                            "北美","无码"
                        ]
                }
            }
        }

+ Response 20* (application/json)
+ Response 40* (application/json)    

### 退回任务 [DELETE] /article/translateTasks/translators/{id}
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AD_USER
    + state=2的才能退回

+ Response 20* (application/json)
+ Response 40* (application/json)

### 翻译者任务列表 [GET] /article/translateTasks/translators?filter[state]=1&page[number]=1&page[size]=5
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AD_USER
+ Parameters
    + filter[state] - 筛选条件，任务状态
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 1,
            "totalElements": 1,
            "size": 5,
            "number": 1,
            "numberOfElements": 1,
            "first": true,
            "last": true,
            "sort": [
              {
                "direction": "DESC",
                "property": "modified",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
              }
            ]
          },
          "links": {
            "self": "/article/translateTask/translator?filter[state]=1&page[number]=1&page[size]=5",
            "first": "/article/translateTask/translator?filter[state]=1&page[number]=1&page[size]=5",
            "last": "/article/translateTask/translator?filter[state]=1&page[number]=1&page[size]=5"
          },
          "data": [
            {
              "id": 2,
              "topicId": 2,
              "state": 1,
              "title": "Virus TI2 Keyboard",
              "topicType": "产品"
            }
          ]
        }
### 翻译者任务详情 [GET] [/article/translateTasks/translators/{id}]
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_AD_USER

+ Response 200 (application/json)

        {
          "data": {
            "id": 1,
            "enabled": 1,
            "creator": 1031,
            "modifier": 1031,
            "created": "2017-11-07 10:41:56",
            "modified": "2017-11-07 15:09:33",
            "topicId": 1,
            "postId": 1013367,
            "state": 2,
            "wordsNum": 2000,
            "bonus": 100,
            "translator": 1031,
            "auditor": 0,
            "post": {
              "id": 1013367,
              "enabled": 0,
              "creator": 1031,
              "modifier": 1031,
              "created": "2017-11-07 15:03:23",
              "modified": "2017-11-07 15:09:33",
              "parentId": 1,
              "topicId": 1,
              "priority": 0,
              "language": 2,
              "categories": [],
              "tags": [],
              "features": [
                {
                  "_name": "属性2",
                  "_value": "属性2的值"
                }
              ],
              "title": "fan'yi'ren'wu翻译任务222222222 ",
              "description": "fan'yi翻译 miao'shu描述2222222 ",
              "content": "wo'shi'fan'yi'nei'rong我是翻译内容2222222",
              "parent": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2016-10-12 09:55:37",
                "modified": "2017-10-28 13:33:38",
                "parentId": 0,
                "topicId": 1,
                "priority": 0,
                "language": 2,
                "categories": [
                  "Keyboards & Synthesizers",
                  "Synthesizers"
                ],
                "tags": [
                  "VirusTI2Desk"
                ],
                "features": [
                  {
                    "_name": "Sound Engine Type(s)",
                    "_value": "Analog Modeling"
                  }
                ],
                "title": "Virus TI2 Desktop",
                "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n ",
                "postsText": {
                  "id": 1,
                  "category": "Keyboards & Synthesizers,Synthesizers",
                  "tag": "VirusTI2Desk",
                  "title": "Virus TI2 Desktop",
                  "feature": "[{\"_name\":\"Sound Engine Type(s)\",\"_value\":\"Analog Modeling\"}]",
                  "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                  "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n 
                },
                "postType": 1,
                "postTypeValue": "爬取"
              },
              "postsText": {
                "id": 1013367,
                "category": "",
                "tag": "",
                "title": "fan'yi'ren'wu翻译任务222222222 ",
                "feature": "[{\"_name\":\"属性2\",\"_value\":\"属性2的值\"}]",
                "description": "fan'yi翻译 miao'shu描述2222222 ",
                "content": "wo'shi'fan'yi'nei'rong我是翻译内容2222222"
              },
              "postType": 3,
              "postTypeValue": "精翻"
            },
            "title": "Virus TI2 Desktop",
            "topicType": "产品",
            "translatorAccount": "18611194890"
          }
        }
## 管理员接口
### 增加任务 [POST] /article/translateTasks
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN

+ Parameters
    + topicId - 必填
    + wordsNum
    + bonus
    + translatorAccount
    + post
    + post.id - 如果post不为空，则必填
    + post.content - 如果post不为空，则必填

+ 新增Request (application/json)
    
        {
            "data":{
                "topicId":1,
                "translatorAccount":"18611194890",
                "wordsNum":1000,
                "bonus":50,
                "post":{
                    "id":5,
                    "content":"内容分段测试 "
                }
            }
        }
+ Response 201 (application/json)

        {
            "data": {
                "id": 1,
                "type": "translateTasks"
            }
        }
### 修改任务 [PATCH] /article/translateTasks/{id}

+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN

+ Parameters
    + state
    + wordsNum
    + wordsNumCn
    + bonus
    + translatorAccount

+ 修改Request (application/json)
    
        {
            "data":{
                "translatorAccount":"18611194890",
                "wordsNum":2000,
                "wordsNumCn":2500,
                "bonus":100
            }
        }
+ Response 200 (application/json)

### 删除任务 [DELETE] /article/translateTasks/{id}

+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
    + [MUST] 只有state=1的才能被删除

+ Response 204 (application/json)
+ Response 400 (application/json)

### 任务集合 [GET] [/article/translateTasks?page[number]=1&page[size]=5&filter[state]=1&filter[enabled]=1

+ Parameters
    + filter[enabled] - 筛选条件，是否可用
    + filter[state] - 筛选条件，任务状态

+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 1,
            "totalElements": 2,
            "size": 5,
            "number": 1,
            "numberOfElements": 2,
            "first": true,
            "last": true,
            "sort": null
          },
          "links": {
            "self": "/article/translateTask?filter[state]=1&filter[enabled]=1&page[number]=1&page[size]=5",
            "first": "/article/translateTask?filter[state]=1&filter[enabled]=1&page[number]=1&page[size]=5",
            "last": "/article/translateTask?filter[state]=1&filter[enabled]=1&page[number]=1&page[size]=5"
          },
          "data": [
            {
              "id": 1,
              "enabled": 1,
              "creator": 1031,
              "modifier": 1031,
              "created": "2017-11-07 10:41:56",
              "modified": "2017-11-07 11:09:06",
              "topicId": 1,
              "postId": 0,
              "state": 1,
              "wordsNum": 2000,
              "bonus": 100,
              "translator": 0,
              "auditor": 0,
              "title": "Virus TI2 Desktop",
              "topicType": "产品",
              "translatorAccount": "18611194890",
              "auditorAccount": "18611194890",
              "modifierAccount": "18611194890",
              "creatorAccount": "18611194890"
            },
            {
              "id": 2,
              "enabled": 1,
              "creator": 1031,
              "modifier": 1031,
              "created": "2017-11-07 11:07:30",
              "modified": "2017-11-07 11:07:30",
              "topicId": 2,
              "postId": 0,
              "state": 1,
              "wordsNum": 500,
              "bonus": 25,
              "translator": 0,
              "auditor": 0,
              "title": "Virus TI2 Keyboard",
              "topicType": "产品",
              "translatorAccount": "18611194890",
              "modifierAccount": "18611194890",
              "creatorAccount": "18611194890"
            }
          ]
        }
### 任务详情 [GET] [/article/translateTasks/{id}]
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN

+ Response 200 (application/json)   

        {
          "data": {
            "id": 1,
            "enabled": 1,
            "creator": 1031,
            "modifier": 1031,
            "created": "2017-11-07 10:41:56",
            "modified": "2017-11-07 15:09:33",
            "topicId": 1,
            "postId": 1013367,
            "state": 2,
            "wordsNum": 2000,
            "bonus": 100,
            "translator": 1031,
            "auditor": 0,
            "post": {
              "id": 1013367,
              "enabled": 0,
              "creator": 1031,
              "modifier": 1031,
              "created": "2017-11-07 15:03:23",
              "modified": "2017-11-07 15:09:33",
              "parentId": 1,
              "topicId": 1,
              "priority": 0,
              "language": 2,
              "categories": [],
              "tags": [],
              "features": [
                {
                  "_name": "属性2",
                  "_value": "属性2的值"
                }
              ],
              "title": "fan'yi'ren'wu翻译任务222222222 ",
              "description": "fan'yi翻译 miao'shu描述2222222 ",
              "content": "wo'shi'fan'yi'nei'rong我是翻译内容2222222",
              "parent": {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2016-10-12 09:55:37",
                "modified": "2017-10-28 13:33:38",
                "parentId": 0,
                "topicId": 1,
                "priority": 0,
                "language": 2,
                "categories": [
                  "Keyboards & Synthesizers",
                  "Synthesizers"
                ],
                "tags": [
                  "VirusTI2Desk"
                ],
                "features": [
                  {
                    "_name": "Sound Engine Type(s)",
                    "_value": "Analog Modeling"
                  }
                ],
                "title": "Virus TI2 Desktop",
                "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n ",
                "postsText": {
                  "id": 1,
                  "category": "Keyboards & Synthesizers,Synthesizers",
                  "tag": "VirusTI2Desk",
                  "title": "Virus TI2 Desktop",
                  "feature": "[{\"_name\":\"Sound Engine Type(s)\",\"_value\":\"Analog Modeling\"}]",
                  "description": "Analog Modeling Desktop Synthesizer and 24-bit/192kHz Audio/MIDI Interface",
                  "content": "<div> \n <h2>Access Steps Up The Renowned Virus!</h2> \n 
                },
                "postType": 1,
                "postTypeValue": "爬取"
              },
              "postsText": {
                "id": 1013367,
                "category": "",
                "tag": "",
                "title": "fan'yi'ren'wu翻译任务222222222 ",
                "feature": "[{\"_name\":\"属性2\",\"_value\":\"属性2的值\"}]",
                "description": "fan'yi翻译 miao'shu描述2222222 ",
                "content": "wo'shi'fan'yi'nei'rong我是翻译内容2222222"
              },
              "postType": 3,
              "postTypeValue": "精翻"
            },
            "title": "Virus TI2 Desktop",
            "topicType": "产品",
            "translatorAccount": "18611194890",
            "auditorAccount": "18611194890",
            "modifierAccount": "18611194890",
            "creatorAccount": "18611194890"
          }
        }


## 爬虫爬取数据统计

+ Data
    + seedId (Integer) - 网站种子ID
    + name (String) - 名字（在seeds表中设置）
    + description (String) - 网站描述 （在seeds表中设置）
    + counts (Long) - 爬取topic数据合计

## 爬虫爬取数据统计详情 [GET] /spider/statistics?filter[priortime]=2017-01-09%2023:11:45&filter[latertime]=2017-11-08%2023:11:45&page[number]=1&page[size]=5
+ Description

+ Parameters
    + filter[priortime] 起始时间,默认时间为当前时间减去一天
    + filter[latertime] 结束时间,默认时间为当前时间
    + page[number] 页数
    + page[size]  每页多少条记录
+ Response 200 (application/json)
    
        {
            "meta": {
            "totalPages": 13,
            "totalElements": 63,
            "size": 5,
            "number": 1,
            "numberOfElements": 5,
            "first": true,
            "last": false,
            "sort": null
        },
            "links": {
                "self": "/spider/statistics?filter[priortime]=2017-01-09 23:11:45&filter[latertime]=2017-11-08 23:11:45&page[number]=1&page[size]=5",
                "first": "/spider/statistics?filter[priortime]=2017-01-09 23:11:45&filter[latertime]=2017-11-08 23:11:45&page[number]=1&page[size]=5",
                "next": "/spider/statistics?filter[priortime]=2017-01-09 23:11:45&filter[latertime]=2017-11-08 23:11:45&page[number]=2&page[size]=5",
                "last": "/spider/statistics?filter[priortime]=2017-01-09 23:11:45&filter[latertime]=2017-11-08 23:11:45&page[number]=13&page[size]=5"
        },
        "data": [
                {
                    "seedId": 1,
                    "name": "products",
                    "description": "Music123",
                    "counts": 5724
                },
            {
                "seedId": 2,
                "name": "products",
                "description": "甜水网",
                "counts": 3445
            },
            {
                "seedId": 3,
                "name": "products",
                "description": "GuitarCenter",
                "counts": 1555
            },
            {
                "seedId": 4,
                "name": "products",
                "description": "VintageKing",
                "counts": 143
            },
            {
                "seedId": 5,
                "name": "products",
                "description": "MartinAudio",
                "counts": 14
            }
        ]
        }

## RabbitMq Connections连接状态汇总

+ Data
    + name(String) - 客户端名字
    + user(String) - 账户登陆名字
    + host (String) - 客户端IP
    + ssl(Boolean) - 是否加密
    + state(String) - 运行状态
    + timeout (int) - HeartBeat心跳时间
    + protocol (String) - 协议名称
    + connected_at(Long) -建立连接时间

## Connections连接状态汇总 [GET] /spider/rabbitmq/connections
+ Description

+ Parameters

+ Response 200 (application/json)
    
        {
            "data": [
                    {
                    "garbage_collection": {
                        "minor_gcs": 71,
                        "min_bin_vheap_size": 46422,
                        "min_heap_size": 233,
                        "fullsweep_after": 65535
                    },
                    "reductions": 35848,
                    "ssl_cipher": null,
                    "connected_at": 1510898081568,
                    "type": "network",
                    "ssl": false,
                    "timeout": 60,
                    "frame_max": 131072,
                    "protocol": "AMQP 0-9-1",
                    "send_oct_details": {
                        "rate": 40
                    },
                    "client_properties": {
                        "connection_name": "rabbitConnectionFactory#0",
                        "product": "RabbitMQ",
                        "copyright": "Copyright (c) 2007-2016 Pivotal Software, Inc.",
                        "capabilities": {
                            "exchange_exchange_bindings": true,
                            "connection.blocked": true,
                            "authentication_failure_close": true,
                            "basic.nack": true,
                            "publisher_confirms": true,
                            "consumer_cancel_notify": true
                        },
                        "information": "Licensed under the MPL. See http://www.rabbitmq.com/",
                        "version": "4.0.2",
                        "platform": "Java"
                    },
                    "send_pend": 0,
                    "host": "192.168.1.138",
                    "auth_mechanism": "PLAIN",
                    "state": "running",
                    "recv_oct_details": {
                        "rate": 44
                    },
                    "ssl_protocol": null,
                    "ssl_key_exchange": null,
                    "peer_cert_subject": null,
                    "peer_cert_validity": null,
                    "recv_cnt": 178,
                    "peer_port": 58275,
                    "ssl_hash": null,
                    "peer_cert_issuer": null,
                    "send_cnt": 178,
                    "recv_oct": 7367,
                    "vhost": "/",
                    "node": "rabbit@dev",
                    "channel_max": 0,
                    "channels": 2,
                    "peer_host": "192.168.1.130",
                    "port": 5672,
                    "send_oct": 6050,
                    "name": "192.168.1.130:58275 -> 192.168.1.138:5672",
                    "user": "rabbitmq",
                    "reductions_details": {
                        "rate": 218.4
                    }
                },
                {
                    "garbage_collection": {
                        "minor_gcs": 377,
                        "min_bin_vheap_size": 46422,
                        "min_heap_size": 233,
                        "fullsweep_after": 65535
                    },
                    "reductions": 15039405,
                    "ssl_cipher": null,
                    "connected_at": 1510822344221,
                    "type": "network",
                    "ssl": false,
                    "timeout": 60,
                    "frame_max": 131072,
                    "protocol": "AMQP 0-9-1",
                    "send_oct_details": {
                        "rate": 40
                    },
                    "client_properties": {
                        "connection_name": "rabbitConnectionFactory#0",
                        "product": "RabbitMQ",
                        "copyright": "Copyright (c) 2007-2016 Pivotal Software, Inc.",
                        "capabilities": {
                            "exchange_exchange_bindings": true,
                            "connection.blocked": true,
                            "authentication_failure_close": true,
                            "basic.nack": true,
                            "publisher_confirms": true,
                            "consumer_cancel_notify": true
                        },
                        "information": "Licensed under the MPL. See http://www.rabbitmq.com/",
                        "version": "4.0.2",
                        "platform": "Java"
                    },
                    "send_pend": 0,
                    "host": "192.168.1.138",
                    "auth_mechanism": "PLAIN",
                    "state": "running",
                    "recv_oct_details": {
                        "rate": 44
                    },
                    "ssl_protocol": null,
                    "ssl_key_exchange": null,
                    "peer_cert_subject": null,
                    "peer_cert_validity": null,
                    "recv_cnt": 75413,
                    "peer_port": 55984,
                    "ssl_hash": null,
                    "peer_cert_issuer": null,
                    "send_cnt": 75412,
                    "recv_oct": 2765947,
                    "vhost": "/",
                    "node": "rabbit@dev",
                    "channel_max": 0,
                    "channels": 2,
                    "peer_host": "192.168.1.181",
                    "port": 5672,
                    "send_oct": 2513850,
                    "name": "192.168.1.181:55984 -> 192.168.1.138:5672",
                    "user": "rabbitmq",
                    "reductions_details": {
                        "rate": 217.6
                    }
                    }
                    ]
                }
               
  ## 通过SeedId获取爬取的数据详情

+ Data
    + id(Long) - id
    + topicId(Long) - topicId
    + seedId(Long) - 种子ID
    + origin(String) - 被爬取的url

## Connections连接状态汇总 [GET] /spider/statistics/topicsfetch/{seedId}
+ Description

+ Parameters
    + page[number] 页数
    + page[size]  每页多少条记录
    + seedId  种子ID

+ Response 200 (application/json)
    
        {
        "meta": {
            "totalPages": 16449,
            "totalElements": 65795,
            "size": 4,
            "number": 2,
            "numberOfElements": 4,
            "first": false,
            "last": false,
            "sort": [
                {
                    "direction": "DESC",
                    "property": "id",
                    "ignoreCase": false,
                    "nullHandling": "NATIVE",
                    "descending": true,
                    "ascending": false
                }
            ]
        },
        "links": {
            "self": "/spider/statistics/topicsfetch/1?page[number]=2&page[size]=4",
            "first": "/spider/statistics/topicsfetch/1?page[number]=1&page[size]=4",
            "prev": "/spider/statistics/topicsfetch/1?page[number]=1&page[size]=4",
            "next": "/spider/statistics/topicsfetch/1?page[number]=3&page[size]=4",
            "last": "/spider/statistics/topicsfetch/1?page[number]=16449&page[size]=4"
        },
        "data": [
            {
                "id": 620042,
                "topicId": 620302,
                "seedId": 1,
                "origin": "http://www.music123.com/classroom-kids/a-days-work-20-brass-bar-chime-tree/472925000000000"
            },
            {
                "id": 620041,
                "topicId": 620301,
                "seedId": 1,
                "origin": "http://www.music123.com/classroom-kids/a-days-work-a-days-work-hand-held-chime-and-holder/472918000914000"
            },
            {
                "id": 620040,
                "topicId": 620300,
                "seedId": 1,
                "origin": "http://www.music123.com/classroom-kids/a-days-work-wheelchair-tray-table-multi-instrument-holder/472921000000000"
            },
            {
                "id": 620039,
                "topicId": 620299,
                "seedId": 1,
                "origin": "http://www.music123.com/accessories/a-days-work-36-peg-soprano-recorder-stand/472923000000000"
            }
        ]
    }
