+ 2018年5月24日
    + API初始化

+ 2018年6月26日
    + 修改公众号结构，包括以下几点
    	+ 添加qrCode字段
    	+ 修改region字段为regionId
    	+ 修改classfy字段为categoryId
+ 2018年6月28日
    + 添加地区管理接口
    + 添加分类管理接口
+ 2018年8月3日
    +  添加公众号管理接口
+ 2018年8月28日
    +  修改分类结构，包括以下几点
        + 添加quotes字段
        + 添加displayOrder字段
## 文件上传
### 获取上传文件验证 (GET) [/upload] (本接口是support服务提供的，所以完整url为/support/upload)
+ Data
    + code (string) - 固定值
    + isPublic (int) - 固定值
    + time (long) - 时间戳
    + userId (long) - 当前用户id
    + key (string) - 验证串
+ Description
    + [MUST] Authenticated
+ Response 200 (application/json)

        {
          "data": {
            "isPublic": 1,
            "code": "20160725001",
            "time": 1527152862645,
            "userId": 1031,
            "key": "456c1c8ae1f5223527b0478219303145"
          }
        }
### 上传文件 (POST) [http://192.168.1.248/upload/image] [http://static.mifanxing.com/upload/image]
+ Request (application/form-data)

        {
          "code": "20160725001",
          "isPublic": 1,
          "time": 1491885189308,
          "userId": 12,
          "key": "afb66afa0404f92ac4670f6f4a721779"
          "file": "avatar.jpg"
        }
+ Response 200 (application/json)

        {
              "code": 100,
              "message": null,
              "data": {
                  "url":"http://static.budee.com/iyyren/image/201704/11/1234/195238888195899392.jpg"
              },
              "error": null
          }

## 公众号管理
+ Data
    + articleSeedId (Long) - seed与article的seed表id对应表 
    + title (String) - 微信号名称
    + wechatId (String) - 微信号wechat_id
    + funcIntro (String) - 功能介绍
    + biz (String) - 公众号唯一识别符（唯一）
    + logo (String) - 公众号logo
    + qrCode (String) - 二维码
    + accountType (int) - 订阅号0   服务号1
    + accountSubject (int) - 企业和个人
    + subject (String) - 帐号主体
    + companyName (String) - 企业全称
    + businessRegNo (String) - 工商执照注册号
    + serviceTel (String) - 客服电话
    + companyType (String) - 企业类型
    + businessScope (String) - 经营范围
    + establishDate (date) - 企业成立日期
    + operatingPeriod (date) - 企业经营期限
    + regionId (long) - 地区
    + categoryId (long) - 分类
    + description (String) - 描述
    + updateRate (int) - 更新频率
    + language (int) - 0中文  1英文
    + enabled (int)  - 使能  0禁止 1启用
    + creator (long) - 创建人
    + modifier (long) - 修改人
    + created (date) - 创建时间
    + modified (date) - 修改时间
    
### 增加 [POST] /wxSeeds
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
    + articleSeedId
    + title 必填
    + wechatId 必填
    + funcIntro
    + biz
    + logo
    + qrCode
    + accountType
    + accountSubject
    + companyName
    + businessRegNo
    + serviceTel
    + companyType
    + businessScope
    + establishDate
    + operatingPeriod
    + regionId 
    + categoryId
    + description
    + updateRate
    + language
+ Request（application/json）

        {
         "data":{
         		"title":"生活大爆炸",
        		"wechatId":"yulida",
        		"regionId":"99",
        		"categoryId":"10",
        		"tags":[
            			"娱乐",
            			"媒体",
            			"搞笑"
            	]
          }
        }
       
+ Response 201 (application/json)  

         {
        "data": {
            "id": 124,
            "type": "wxSeeds"
        }
       }
       
### 修改 [PATCH] /wxSeeds/{id}
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
    + articleSeedId
    + title 必填
    + wechatId 必填
    + funcIntro
    + biz
    + logo
    + qrCode
    + accountType
    + accountSubject
    + companyName
    + businessRegNo
    + serviceTel
    + companyType
    + businessScope
    + establishDate
    + operatingPeriod
    + regionId
    + categoryId
    + description
    + updateRate
    + language
       
+ 修改Request 200（application/json）

        {
         "data":{
         		"title":"生活大爆炸NO1",
        		"wechatId":"yulida",
        		"regionId":"98",
        		"categoryId":"2",
        		"tags":[
            			"生活",
            			"媒体",
            			"搞笑"
            	]
          }
         }
+  Response 200       


### 列表 [GET] /wxSeeds?filter[title:like]=%25Midifan%25&page[number]=1&page[size]=5&sort=-modified      
       
+ Parameters
  + id 
  + title
     + 查询示例：filter[title]=%25助手%25 （'%25'为'%'的转义） 
  + sort -modified(从新到旧) | modified(从旧到新)       
       
+ Response 200 (application/json)       

        {
        "meta": {
            "totalPages": 28,
            "totalElements": 136,
            "size": 5,
            "number": 1,
            "numberOfElements": 5,
            "first": true,
            "last": false,
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
            "self": "/wxSeeds?sort=-modified&page[number]=1&page[size]=5",
            "first": "/wxSeeds?sort=-modified&page[number]=1&page[size]=5",
            "next": "/wxSeeds?sort=-modified&page[number]=2&page[size]=5",
            "last": "/wxSeeds?sort=-modified&page[number]=28&page[size]=5"
        },
        "data": [
            {
                "id": 149,
                "enabled": 1,
                "creator": 0,
                "modifier": 2371,
                "created": "2018-08-22 19:01:40",
                "modified": "2018-08-23 17:47:45",
                "title": "定时深V发版",
                "wechatId": "gfbb",
                "logo": "",
                "qrCode": "",
                "funcIntro": "权威、实力，源自人民。",
                "accountSubject": 0,
                "subject": "阿斯顿撒旦飞洒的范德萨范德萨发",
                "regionId": 99,
                "categoryId": 10,
                "tags": [
                    "哦我我我我我我我",
                    "哈哈哈哈哈哈哈哈",
                    "新鲜好",
                    "活力多",
                    "美味强"
                ],
                "categoryTitle": "文化类",
                "regionTitle": "宁波市"
            },
            {
                "id": 150,
                "enabled": 1,
                "creator": 0,
                "modifier": 2371,
                "created": "2018-08-23 16:48:16",
                "modified": "2018-08-23 17:44:30",
                "title": "花样滑冰很丰富",
                "wechatId": "cvggb",
                "logo": "",
                "qrCode": "",
                "funcIntro": "我就是那个你知道的如假包换的冷兔！爱生活，爱讲冷笑话~ 每日游走于各大社交平台分享各种精彩热门搞笑内容~ 想看冷笑话？关注我一个就够了！",
                "accountSubject": 0,
                "subject": "asDSAd阿斯蒂",
                "regionId": 97,
                "categoryId": 13,
                "tags": [
                    "哦我我我我我我我",
                    "活力",
                    "青春",
                    "美好",
                    "快乐"
                ],
                "categoryTitle": "创业类",
                "regionTitle": "浙江省"
            },
            {
                "id": 118,
                "enabled": 1,
                "creator": 1058,
                "modifier": 1058,
                "created": "2018-08-06 13:39:40",
                "modified": "2018-08-23 10:16:22",
                "articleSeedId": 247,
                "title": "中大华堂科技",
                "wechatId": "zdht_keji",
                "biz": "MzA5Njk4NDE3Mg==",
                "logo": "//static.mifanxing.com/iyyren/image/201808/06/1339/369926353170087936.jpg",
                "accountSubject": 0,
                "regionId": 0,
                "categoryId": 0
            },
            {
                "id": 148,
                "enabled": 1,
                "creator": 1031,
                "modifier": 1031,
                "created": "2018-08-22 18:50:36",
                "modified": "2018-08-22 18:50:36",
                "title": "feilon",
                "wechatId": "feig11",
                "biz": "woshiwshaaaa",
                "accountSubject": 0,
                "regionId": 0,
                "categoryId": 0,
                "tags": [
                    "哦我我我我我我我",
                    "biaozi"
                ]
            },
            {
                "id": 147,
                "enabled": 1,
                "creator": 1031,
                "modifier": 1031,
                "created": "2018-08-22 18:46:21",
                "modified": "2018-08-22 18:46:21",
                "title": "feilongzaitian111",
                "wechatId": "feiguohai123111",
                "biz": "woshiwshifuaaaaa",
                "accountSubject": 0,
                "regionId": 0,
                "categoryId": 0,
                "tags": [
                    "哦我我我我我我我",
                    "哈哈哈哈哈哈哈哈",
                    "biaozi111"
                ]
            }
        ]
       }

### 删除 [DELETE] /wxSeeds/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 204

## 微信文章管理
+ Data
   +  articleTopicId (long) - 与 article topics 表中对应的id
   +  seedId (long) 
   +  type (int) - 主题类型 0:图文，1：视频，2：音视频混合
   +  title (String) - 标题
   +  content (String) - 内容
   +  author (String) - 作者
   +  postDate (date) - 发布时间
   +  top (int) - 是否头条 0:是，1：否
   +  original (int) - 是否原创 0:否，1：是
   +  enabled (int) - 启用/禁用
   +  reviews (int) - 浏览量
   +  thumbsUp (int) - 点赞数
   +  seedTitle (String) - 公众号名
   +  creator (long) - 创建人
   +  modifier (long) - 修改人
   +  created (date) - 创建时间
   +  modified (date) - 修改时间

### 列表[GET]/topics?filter[seedId]=1&filter[modified:like]=%252018-05-03%25&fields[Topics]=id,title,seedId,original,postDate,modified,created
+ Parameters
  + id 
  + seedId
  + title
  + modified 这个必须使用模糊查询，格式为yyyy-MM-dd，例如：2018-05-03
     + 模糊查询示例：filter[title]=%25助手%25 （'%25'为'%'的转义） 
  + sort -modified(从新到旧) | modified(从旧到新)   
+ fields （必须返回的字段，不填则返回全部）
    + id 必须
    + title 必须
    + seedId 必须
    + original 必须
    + postDate 必须
    + modified 必须
    + created 必须
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 6,
            "totalElements": 11,
            "size": 2,
            "number": 1,
            "numberOfElements": 2,
            "first": true,
            "last": false,
            "sort": null
          },
          "links": {
            "self": "/topics?fields[Topics]=id,title,seedId,original,postDate,modified,created&filter[seedId]=1&page[number]=1&page[size]=2",
            "first": "/topics?fields[Topics]=id,title,seedId,original,postDate,modified,created&filter[seedId]=1&page[number]=1&page[size]=2",
            "next": "/topics?fields[Topics]=id,title,seedId,original,postDate,modified,created&filter[seedId]=1&page[number]=2&page[size]=2",
            "last": "/topics?fields[Topics]=id,title,seedId,original,postDate,modified,created&filter[seedId]=1&page[number]=6&page[size]=2"
          },
          "data": [
            {
              "id": 3812,
              "created": "2018-05-03 16:17:15",
              "modified": "2018-05-14 14:34:37",
              "seedId": 1,
              "title": "Tokyo热不热我不知道，我只知道最近黑胶热！",
              "postDate": "2018-04-20T14:48:43.000+0000",
              "original": 0,
              "reviews": 184,
              "thumbsUp": 0,
              "seedTitle": "AKAI雅佳乐园"
            },
            {
              "id": 3813,
              "created": "2018-05-03 16:17:16",
              "modified": "2018-05-22 18:49:34",
              "seedId": 1,
              "title": "贾老板用MPC在演唱会上帅了一把！",
              "postDate": "2018-04-18T07:23:07.000+0000",
              "original": 0,
              "reviews": 236,
              "thumbsUp": 1,
              "seedTitle": "AKAI雅佳乐园"
            }
          ]
         }

### 删除 [DELETE] /topics/{id}

+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+ Response 200

### 文章详情[GET] /topics/{id}
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
+ Response 200 (application/json)

        {
        "data": {
            "id": 1,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-04-27 16:37:11",
            "modified": "2018-05-23 14:31:11",
            "articleTopicId": 997312,
            "seedId": 2,
            "type": 0,
            "title": "知名无线音箱秘密提交上市申请 估值最高30亿美元",
            "titleHash": 5636961133973108502,
            "content": "内容",
            "author": "艾维音响网",
            "postDate": "2018-04-27T05:05:18.000+0000",
            "top": 0,
            "original": 0,
            "groupSign": 1527056915994,
            "reviews": 272,
            "thumbsUp": 2,
            "seedTitle": "艾维音响网"
        }
       }
  
## 地区管理
+ Data
    + id (Long) - ID
    + parentId (Long) - 父节点
    + title (String) - 区域名称
    + leaf (int) - 是否叶子节点 0：否，1：是
    + quotes (Long) - 公众号引用的次数
    + displayOrder (Long) - 排序
    + enabled (int) - 是否可用 
    + creator (Long) - 创建人
    + modifier (Long) - 修改人
    + created (date) - 创建时间
    + modified (date) - 修改时间
  
### 增加 [POST] /wxRegions 
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
    + title 必填
    + parentId 

+ Request (application/json)
    
        {
             "data":{
             	 "parentId":0,
                "title":"测试省"
              }
         }

+ Response 200 (application/json)

        {
            "data": {
                "id": 431,
                "type": "wxRegions"
            }
         }

### 修改 [PATCH] /wxRegions/{id}
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
    + title 必填
    + parentId 

+ Request (application/json)
           
        {
            "data":{
            "title":"测试xx省"
            }
         }

+ Response 200

### 列表 [GET] /wxRegions?filter[parentId]=5

+ Parameters
    +  filter[parentId]
    +  filter[quotes:gt] = 0 引用次数大于零

+ Response 200 (application/json)
    
        {
        "meta": {
            "totalPages": 43,
            "totalElements": 423,
            "size": 10,
            "number": 1,
            "numberOfElements": 10,
            "first": true,
            "last": false,
            "sort": null
        },
        "links": {
            "self": "/wxRegions?page[number]=1&page[size]=10",
            "first": "/wxRegions?page[number]=1&page[size]=10",
            "next": "/wxRegions?page[number]=2&page[size]=10",
            "last": "/wxRegions?page[number]=43&page[size]=10"
        },
        "data": [
            {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:22",
                "modified": "2018-08-06 16:20:20",
                "parentId": 0,
                "title": "北京市",
                "leaf": 0,
                "quotes": 2,
                "displayOrder": 0,
                "children": [
                    [
                        {
                            "id": 2,
                            "parentId": 1,
                            "title": "北京市"
                        }
                    ]
                ]
            },
            {
                "id": 2,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-08-06 16:20:20",
                "parentId": 1,
                "title": "北京市",
                "leaf": 1,
                "quotes": 1,
                "displayOrder": 0
            },
            {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 0,
                "title": "天津市",
                "leaf": 0,
                "quotes": 0,
                "displayOrder": 0,
                "children": [
                    [
                        {
                            "id": 4,
                            "parentId": 3,
                            "title": "天津市"
                        }
                    ]
                ]
            },
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 3,
                "title": "天津市",
                "leaf": 1,
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 5,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-08-09 02:00:00",
                "parentId": 0,
                "title": "河北省",
                "leaf": 0,
                "quotes": 4,
                "displayOrder": 0,
                "children": [
                    [
                        {
                            "id": 6,
                            "parentId": 5,
                            "title": "石家庄市"
                        },
                        {
                            "id": 7,
                            "parentId": 5,
                            "title": "唐山市"
                        },
                        {
                            "id": 8,
                            "parentId": 5,
                            "title": "秦皇岛市"
                        },
                        {
                            "id": 9,
                            "parentId": 5,
                            "title": "邯郸市"
                        },
                        {
                            "id": 10,
                            "parentId": 5,
                            "title": "邢台市"
                        },
                        {
                            "id": 11,
                            "parentId": 5,
                            "title": "保定市"
                        },
                        {
                            "id": 12,
                            "parentId": 5,
                            "title": "张家口市"
                        },
                        {
                            "id": 13,
                            "parentId": 5,
                            "title": "承德市"
                        },
                        {
                            "id": 14,
                            "parentId": 5,
                            "title": "沧州市"
                        },
                        {
                            "id": 15,
                            "parentId": 5,
                            "title": "廊坊市"
                        },
                        {
                            "id": 16,
                            "parentId": 5,
                            "title": "衡水市"
                        }
                    ]
                ]
            },
            {
                "id": 6,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 5,
                "title": "石家庄市",
                "leaf": 1,
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 7,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-08-06 16:20:20",
                "parentId": 5,
                "title": "唐山市",
                "leaf": 1,
                "quotes": 1,
                "displayOrder": 0
            },
            {
                "id": 8,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-08-06 16:20:20",
                "parentId": 5,
                "title": "秦皇岛市",
                "leaf": 1,
                "quotes": 2,
                "displayOrder": 0
            },
            {
                "id": 9,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 5,
                "title": "邯郸市",
                "leaf": 1,
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 10,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 5,
                "title": "邢台市",
                "leaf": 1,
                "quotes": 0,
                "displayOrder": 0
            }
         ]
        }

### 查询地区详情 [GET] /wxRegions/{id}
+ Parameters
    + id 必填

+ Response 200 (application/json)
       
       {
        "data": {
            "id": 68,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-06-08 13:49:24",
            "modified": "2018-06-08 13:49:24",
            "parentId": 67,
            "title": "哈尔滨市",
            "leaf": 1
         }
        }
 


### 删除 [DELETE] /wxRegions/{id}
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Response 204

## 分类管理
+ Data
  + id (Long) - ID
  + title (String) - 公众号分类名
  + description (String) - 分类描述
  + quotes (Long) - 公众号引用次数
  + display_order (Long) - 排序
  + enabled (int) - 是否可用 
  + creator (Long) - 创建人
  + modifier (Long) - 修改人
  + created (date)  - 创建时间
  + modified (date) - 修改时间

### 增加 [POST] /wxCategories
+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
    + title 必填
    + description 必填
+ Request (application/json)
   
        {
        	"data":{
        		"title":"不一样的类",
        		"description":"描述同样的事"
        	}
       }

+ Response 200 (application/json)

    {
    "data": {
        "id": 3,
        "type": "wxCategories"
     }
    }
  
### 修改 [PATCH] /wxCategories/{id}
+ Description
+ [MUST] Authenticated
+ [MUST] ROLE_ADMIN

+ Parameters
    + title 必填
    + description 必填
+ Request (application/json)

        {
        	"data":{
        		"title":"不一样的xxx类",
        		"description":"描述同样的事xxx"
        	}
        }

+ Response 200
 
### 列表 [GET] /wxCategories?sort=-quotes
+ Parameters
    + sort -quotes(引用次数由多到少)
+ Response 200 (application/json)

        {
        "meta": {
            "totalPages": 2,
            "totalElements": 16,
            "size": 10,
            "number": 1,
            "numberOfElements": 10,
            "first": true,
            "last": false,
            "sort": [
                {
                    "direction": "DESC",
                    "property": "quotes",
                    "ignoreCase": false,
                    "nullHandling": "NATIVE",
                    "descending": true,
                    "ascending": false
                }
            ]
        },
        "links": {
            "self": "/wxCategories?sort=-quotes&page[number]=1&page[size]=10",
            "first": "/wxCategories?sort=-quotes&page[number]=1&page[size]=10",
            "next": "/wxCategories?sort=-quotes&page[number]=2&page[size]=10",
            "last": "/wxCategories?sort=-quotes&page[number]=2&page[size]=10"
        },
        "data": [
            {
                "id": 12,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:45:35",
                "modified": "2018-07-31 16:45:35",
                "title": "科技类",
                "quotes": 13,
                "displayOrder": 0
            },
            {
                "id": 8,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:39:55",
                "modified": "2018-07-31 16:39:55",
                "title": "生活类",
                "quotes": 9,
                "displayOrder": 0
            },
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:29:30",
                "modified": "2018-08-09 14:03:01",
                "title": "体育类",
                "quotes": 5,
                "displayOrder": 0
            },
            {
                "id": 14,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:48:15",
                "modified": "2018-07-31 16:48:15",
                "title": "职场类",
                "quotes": 3,
                "displayOrder": 0
            },
            {
                "id": 5,
                "enabled": 1,
                "creator": 0,
                "modifier": 2371,
                "created": "2018-07-31 16:29:49",
                "modified": "2018-08-02 15:10:30",
                "title": "明星类",
                "description": "dnf521",
                "quotes": 1,
                "displayOrder": 0
            },
            {
                "id": 11,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:45:29",
                "modified": "2018-07-31 16:45:29",
                "title": "搞笑类",
                "quotes": 1,
                "displayOrder": 0
            },
            {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-25 16:48:36",
                "modified": "2018-06-25 16:50:57",
                "title": "不一样的xxx类",
                "description": "描述同样的事xxx",
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 6,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:30:47",
                "modified": "2018-07-31 16:30:47",
                "title": "测试类",
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 9,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:43:10",
                "modified": "2018-07-31 16:43:10",
                "title": "健康类",
                "quotes": 0,
                "displayOrder": 0
            },
            {
                "id": 10,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:44:21",
                "modified": "2018-08-23 17:47:45",
                "title": "文化类",
                "quotes": 0,
                "displayOrder": 0
            }
        ]
      }

### 查询分类详情 [GET] /wxCategories/{id}
+ Parameters
    + id 必填
   
+ Response 200 (application/json)     
           
         {
            "data": {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-25 16:48:36",
                "modified": "2018-06-25 16:50:57",
                "title": "不一样的xxx类",
                "description": "描述同样的事xxx"
            }
          }

### 删除 [DELETE] /wxCategories/{id}

+ Description
    + [MUST] Authenticated
    + [MUST] ROLE_ADMIN
    
+ Response 200 
