+ 2018年7月2日
     + API初始化
+ 2018年8月28日     
     + 添加标签列表

## 微信榜单订阅号
+ Data
     + maxStarIndex (Double) - 最大米饭星指数
     + maxRanking (long) - 最大排名
     + allReviewsUp (String) - 总阅读数变化值
     + rankingUp (String) - 排名变化值
     + allPraisesUp (String) - 总点赞数变化值
     + averageReviewsUp (String) - 平均阅读数变化值
     + topReviewsUp (String) - 头条阅读数变化值
     + starIndexUp (String) - 米饭星指数变化值
     + categories (Object) - 公众号分类
    + regions (Object) -  公众号地区
    + tags (String) -  公众号标签
### 查询公众号详情 (客户端) [GET]/wxSeeds/{id}
+ Parameters
    + id  
+ Description
    + ranking 
        + 当ranking为null时没有排名,当ranking为0时同样没有排名,即ranking不能为空且不为0.
    
+ Response 200 (Application/json)

       {
        "data": {
            "id": 1,
            "title": "AKAI雅佳乐园",
            "wechatId": "AKAIPro",
            "biz": "MzIxNzY3MTc0OA==",
            "logo": "//static.mifanxing.com/iyyren/image/201802/01/1554/302556114032148480.jpg",
            "subject": "阿斯顿发第三方",
            "regionId": 11,
            "categoryId": 10,
            "info": {
                "maxStarIndex": 254.98,
                "maxRanking": null,
                "allReviewsUp": 151,
                "rankingUp": 0,
                "allPraisesUp": 3,
                "averageReviewsUp": 151,
                "topReviewsUp": 151,
                "starIndexUp": 229
            },
            "ranks": [
                {
                    "id": 12280,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-07-10 06:00:05",
                    "modified": "2018-07-10 06:00:05",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180625,
                    "endDate": 20180625,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 151,
                    "topReviews": 151,
                    "maxReviews": 151,
                    "allPraises": 3,
                    "topPraises": 3,
                    "maxPraises": 3,
                    "starIndex": 229,
                    "ranking": 0,
                    "averageReviews": 151
                },
                {
                    "id": 852,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-06-05 16:15:41",
                    "modified": "2018-06-05 16:15:41",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180530,
                    "endDate": 20180530,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 0,
                    "topReviews": 0,
                    "maxReviews": 0,
                    "allPraises": 0,
                    "topPraises": 0,
                    "maxPraises": 0,
                    "starIndex": 0,
                    "ranking": 0,
                    "averageReviews": 0
                },
                {
                    "id": 849,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-06-05 16:15:39",
                    "modified": "2018-06-05 16:15:39",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180418,
                    "endDate": 20180418,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 248,
                    "topReviews": 248,
                    "maxReviews": 248,
                    "allPraises": 1,
                    "topPraises": 1,
                    "maxPraises": 1,
                    "starIndex": 254.98,
                    "ranking": 0,
                    "averageReviews": 248
                },
                {
                    "id": 845,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-06-05 16:15:32",
                    "modified": "2018-06-05 16:15:32",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180115,
                    "endDate": 20180115,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 89,
                    "topReviews": 89,
                    "maxReviews": 89,
                    "allPraises": 0,
                    "topPraises": 0,
                    "maxPraises": 0,
                    "starIndex": 146.29,
                    "ranking": 0,
                    "averageReviews": 89
                }
            ],
            "categories": {
                "id": 10,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:44:21",
                "modified": "2018-08-03 17:56:40",
                "title": "文化类"
            },
            "regions": {
                "id": 11,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-08-09 14:42:40",
                "parentId": 5,
                "title": "保定市",
                "leaf": 1,
                "quotes": 4,
                "displayOrder": 0,
                "parent": {
                    "id": 5,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-06-08 13:49:23",
                    "modified": "2018-08-09 14:42:40",
                    "parentId": 0,
                    "title": "河北省",
                    "leaf": 0,
                    "quotes": 4,
                    "displayOrder": 0
                }
            },
            "tags": [
                "体育",
                "健康"
            ]
        }
      }
## 微信客户端标签列表
+ Data
     + id (Long) - ID
     + title (String) - 标签名
     + quotes (Long) - 公众号引用次数
     + display_order (Long) - 排序
     + enabled (int) - 启用
     + creator (Long) - 创建人
     + modifier (Long) - 修改人
     + created  (date) - 创建时间
     + modified (date) - 修改时间
### 列表 (客户端) [GET] /wxTags?page[number]=1&page[size]=20&categoryId=10
    
+ Parameters
     + quotes 公众号引用次数/公众号的个数
     + sort -quotes(引用次数由多到少) 
     + isShow  分类选择后的标签 1：展示，0：不展示
+ Request (application/json)

        {
        "meta": {
            "totalPages": 6,
            "totalElements": 40,
            "size": 7,
            "number": 1,
            "numberOfElements": 7,
            "first": true,
            "last": false,
            "sort": [
                {
                    "direction": "DESC",
                    "property": "quotes",
                    "ignoreCase": false,
                    "nullHandling": "NATIVE",
                    "ascending": false,
                    "descending": true
                }
            ]
        },
        "links": {
            "self": "/wxTags?categoryId=10&page[number]=1&page[size]=7",
            "first": "/wxTags?categoryId=10&page[number]=1&page[size]=7",
            "next": "/wxTags?categoryId=10&page[number]=2&page[size]=7",
            "last": "/wxTags?categoryId=10&page[number]=6&page[size]=7"
        },
        "data": [
            {
                "id": 130,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-27 19:19:30",
                "modified": "2018-08-27 19:42:20",
                "title": "修改标签",
                "quotes": 20,
                "displayOrder": 0,
                "isShow": 0
            },
            {
                "id": 74,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-22 17:46:47",
                "modified": "2018-09-04 23:00:00",
                "title": "~媒体",
                "quotes": 16,
                "displayOrder": 0,
                "isShow": 1,
            },
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-09-05 14:59:30",
                "modified": "2018-09-05 14:59:30",
                "title": "哈哈哈哈哈哈哈哈",
                "quotes": 15,
                "displayOrder": 0,
                "isShow": 1,
            },
            {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-27 15:05:30",
                "modified": "2018-08-27 15:05:30",
                "title": "哦我我我我我我我",
                "quotes": 8,
                "displayOrder": 0,
                "isShow": 1,
            },
            {
                "id": 53,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-06 09:51:11",
                "modified": "2018-09-04 23:00:00",
                "title": "@娱乐",
                "quotes": 8,
                "displayOrder": 0,
                "isShow": 0
            },
            {
                "id": 40,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-22 17:44:21",
                "modified": "2018-09-04 23:00:00",
                "title": "媒体",
                "quotes": 7,
                "displayOrder": 0,
                "isShow": 1,
            },
            {
                "id": 57,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-08-09 14:15:03",
                "modified": "2018-09-04 23:00:00",
                "title": "时事",
                "quotes": 5,
                "displayOrder": 0,
                "isShow": 1,
            }
        ]
      }

### 微信文章榜单-搜索 [GET] /topics/search
+ Response Data
    + wxSeedId - 在大数据这边的公众号id
    + from.source 公众号名称
    + from.image 公众号头像
    + from.fetchThumbsUp - 点赞数
    + from.fetchReviews - 阅读数
    + wxCategoryId - 分类
    + document.original - 是否原创
    + document.documentType - 主题类型(0：图文，1：视频，2：音频，3：音视频混合)
    + created 发布时间
    

+ Parameters
    + filter[wx]=1  在大数据的页面使用这个接口时，应添加的必要筛选条件
    + filter[created:gt] 日期大于，参数值格式为yyyy-MM-dd
    + filter[created:lt] 日期小于，参数值格式为yyyy-MM-dd
    + filter[items.original] 过滤是否原创0/1:否/是
    + filter[items.fetchReviews:gt]=10000 阅读一万+
    + filter[items.documentType] 主题类型(0：图文，1：视频，2：音频，3：音视频混合)

+ Description
    + 接口和米饭星新闻的搜索接口是同一个即/topics/search
    + 排行，不填写sort参数为根据相关度排序，sort=-items.fetchReviews为根据阅读降序，sort=-items.fetchThumbsUp为根据点赞数降序，sort=-created
    + 当点击公众号，到公众号详情，此时取的公众号id为wxSeedId
    + 当点击这篇文章查看详情时，文章id应取字段'articleTopicId'，如果articleTopicId=null或者articleTopicId=0则说明这篇文章在数据库中没有保存内容，因此只能去取外部连接from.origin进行跳转。

+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 1,
            "totalElements": 2,
            "size": 10,
            "number": 1,
            "numberOfElements": 2,
            "first": true,
            "last": true,
            "sort": null
          },
          "links": {
            "self": "/topics/search?filter[wx]=1&agg[size]=-1&filter[created:gt]=2018-09-27 17:58:11&sort=-items.fetchReviews&page[number]=1&page[size]=10",
            "first": "/topics/search?filter[wx]=1&agg[size]=-1&filter[created:gt]=2018-09-27 17:58:11&sort=-items.fetchReviews&page[number]=1&page[size]=10",
            "last": "/topics/search?filter[wx]=1&agg[size]=-1&filter[created:gt]=2018-09-27 17:58:11&sort=-items.fetchReviews&page[number]=1&page[size]=10"
          },
          "data": [
            {
              "id": 1413476,
              "meta": {
                "score": "NaN"
              },
              "forumId": 3,
              "forumName": "新闻",
              "topicType": 0,
              "topicTypeValue": "正常",
              "imageSingle": false,
              "imageRotation": false,
              "creator": 0,
              "created": "2018-09-27 18:20:23",
              "modified": "2018-09-28 10:11:35",
              "wx": 1,
              "wxTopicId": 70402,
              "articleTopicId": 1413476,
              "reviews": 0,
              "replies": 0,
              "thumbsUp": 0,
              "thumbsDown": 0,
              "thumbs": 0,
              "liked": 0,
              "favorite": 0,
              "brand": null,
              "rotations": null,
              "images": [],
              "coverImages": null,
              "from": {
                "image": "http://static.budee.com/iyyren/image/201803/15/1453/317761140065189888.jpg",
                "fetchReviews": 0,
                "reviews": 0,
                "wxSeedId": 60,
                "seedId": 185,
                "origin": "http://mp.weixin.qq.com/s?__biz=MzIyMDkwMzczOQ==&mid=2247518058&idx=7&sn=f8f2ba5b6798b5446704415108db40eb&chksm=97c6273ea0b1ae284c6f6ea082bc071976e42ac393b5d1c5baf6f40b4c5ca44a3568f377447d&scene=27#wechat_redirect&seedId=60&groupSign=1538100095992&top=0&original=100time=1538054754",
                "host": "null://null",
                "rating": null,
                "source": "摇滚客",
                "channelId": 172
              },
              "wxCategoryId": 20,
              "post": {
                "postType": 1,
                "postTypeValue": "爬取",
                "title": "除了开挂民族和黑人大兄弟，全世界的老铁都在被痘痘困扰...",
                "tags": [
                  "痘痘",
                  "皮肤",
                  "印度",
                  "油脂",
                  "曼秀雷敦",
                  "洗面奶",
                  "长痘痘",
                  "痘",
                  "尖",
                  "毛孔"
                ]
              },
              "document": {
                "postDate": "2018-09-27",
                "author": "摇滚客",
                "documentType": 0,
                "original": 0
              },
              "similarities": []
            },
            {
              "id": 1413471,
              "meta": {
                "score": "NaN"
              },
              "forumId": 3,
              "forumName": "新闻",
              "topicType": 0,
              "topicTypeValue": "正常",
              "imageSingle": false,
              "imageRotation": false,
              "creator": 0,
              "created": "2018-09-27 18:13:51",
              "modified": "2018-09-28 10:11:35",
              "wx": 1,
              "wxTopicId": 70397,
              "articleTopicId": 1413471,
              "reviews": 0,
              "replies": 0,
              "thumbsUp": 0,
              "thumbsDown": 0,
              "thumbs": 0,
              "liked": 0,
              "favorite": 0,
              "brand": null,
              "rotations": null,
              "images": [],
              "coverImages": null,
              "from": {
                "image": "http://static.budee.com/iyyren/image/201803/15/1453/317761140065189888.jpg",
                "fetchReviews": 0,
                "reviews": 0,
                "wxSeedId": 60,
                "seedId": 185,
                "origin": "http://mp.weixin.qq.com/s?__biz=MzIyMDkwMzczOQ==&mid=2247518058&idx=5&sn=2f05155d8186ddd04484aa1047712da9&chksm=97c6273ea0b1ae286f3a2d012f2fc62bcdd7bd241e60d136a033278352fa053b5ae5b1f047d9&scene=27#wechat_redirect&seedId=60&groupSign=1538100095992&top=0&original=11time=1538054754",
                "host": "null://null",
                "rating": null,
                "source": "摇滚客",
                "channelId": 172
              },
              "wxCategoryId": 20,
              "post": {
                "postType": 1,
                "postTypeValue": "爬取",
                "title": "只有这20张老照片能证明，这支乐队曾经存在过，而且还特牛逼！",
                "tags": [
                  "楷",
                  "哥",
                  "摇滚",
                  "乐队",
                  "领悟",
                  "年代",
                  "师兄",
                  "商演",
                  "滚君",
                  "排练"
                ]
              },
              "document": {
                "postDate": "2018-09-27",
                "author": "摇滚客",
                "documentType": 2,
                "original": 1
              },
              "similarities": []
            }
          ]
        }

### 公众号搜索 [GET] /wxSeeds/search
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
    + region (object) - 地区
    + category (object) - 分类
    + tags (List<Object>) - 标签
    + topic (object) - 最近更新的新闻
    + description (String) - 描述
    + language (int) - 0中文  1英文
    + created (date) - 创建时间
    + modified (date) - 修改时间

+ Parameters
    + filter[q] 搜索关键字
    + filter[tagId] 标签可多选，用逗号分隔
    + filter[categoryId] 分类
    
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 21,
            "totalElements": 42,
            "size": 2,
            "number": 1,
            "numberOfElements": 2,
            "first": true,
            "last": false,
            "sort": null
          },
          "links": {
            "self": "/seeds/search?filter[tagId]=8,11&page[number]=1&page[size]=2",
            "first": "/seeds/search?filter[tagId]=8,11&page[number]=1&page[size]=2",
            "next": "/seeds/search?filter[tagId]=8,11&page[number]=2&page[size]=2",
            "last": "/seeds/search?filter[tagId]=8,11&page[number]=21&page[size]=2"
          },
          "data": [
            {
              "id": 271,
              "meta": {
                "score": 5.465853
              },
              "starIndex": 295.41,
              "created": "2018-09-07 23:09:51",
              "subject": "个人",
              "accountType": null,
              "companyName": "个人",
              "description": null,
              "accountSubject": 0,
              "language": null,
              "funcIntro": "执着于推广优秀贝斯手及发布贝斯资讯的组织与贝斯干货分享",
              "title": "贝斯乌托邦",
              "articleSeedId": 423,
              "tags": [
                {
                  "id": 23,
                  "title": "乐器"
                },
                {
                  "light": 1,
                  "id": 8,
                  "title": "吉他/贝斯"
                },
                {
                  "light": 1,
                  "id": 11,
                  "title": "个人主体"
                }
              ],
              "biz": "MzUzNzE4NjgyNQ==",
              "qrCode": "//static.mifanxing.com/iyyren/image/201809/07/2304/381664982615605248.jpg",
              "regionId": 2,
              "wechatId": "BassUtopia",
              "modified": "2018-09-17 16:00:32",
              "logo": "//static.mifanxing.com/iyyren/image/201809/07/2304/381664974784839680.jpg",
              "category": {
                "id": 24,
                "title": "交流社区"
              },
              "region": {
                "id": 2,
                "parentId": 1,
                "title": "北京市",
                "parent": {
                  "id": 1,
                  "parentId": 0,
                  "title": "北京市"
                }
              },
              "lastPublish": "2018-09-13 00:54:46",
              "topic": {
                "id": 60024,
                "title": "MI学院贝斯学生的一天！",
                "postDate": "2018-09-12T16:54:46.000+0000",
                "reviews": 0,
                "thumbsUp": 0,
                "openUpdate": 0
              }
            },
            {
              "id": 68,
              "meta": {
                "score": 5.015912
              },
              "starIndex": 0,
              "created": "2017-12-12 00:00:00",
              "subject": "个人",
              "accountType": null,
              "companyName": null,
              "description": null,
              "accountSubject": 0,
              "language": null,
              "funcIntro": "音乐领域权威门户，内容涵盖音乐人专业提升的乐器知识、创作技巧、录音制作乃至运营推广理念，还有最新的行业资讯和产业分析。旗下拥有“吉他攻略”垂直公众号。",
              "title": "音乐人攻略",
              "articleSeedId": 193,
              "tags": [
                {
                  "id": 81,
                  "title": "二手交易"
                },
                {
                  "id": 1,
                  "title": "录音"
                },
                {
                  "id": 162,
                  "title": "制作"
                },
                {
                  "id": 23,
                  "title": "乐器"
                },
                {
                  "light": 1,
                  "id": 8,
                  "title": "吉他/贝斯"
                },
                {
                  "id": 40,
                  "title": "鼓/打击乐"
                },
                {
                  "light": 1,
                  "id": 11,
                  "title": "个人主体"
                },
                {
                  "id": 30,
                  "title": "培训"
                }
              ],
              "biz": "MjM5NjE2OTY0MA==",
              "qrCode": "https://open.weixin.qq.com/qr/code?username=musicianguide",
              "regionId": 224,
              "wechatId": "musicianguide",
              "modified": "2018-09-17 16:00:08",
              "logo": "//static.mifanxing.com/iyyren/image/201803/15/1448/317759747891806208.jpg",
              "category": {
                "id": 24,
                "title": "交流社区"
              },
              "region": {
                "id": 224,
                "parentId": 218,
                "title": "佛山市",
                "parent": {
                  "id": 218,
                  "parentId": 0,
                  "title": "广东省"
                }
              },
              "lastPublish": "2017-10-15 20:07:54",
              "topic": {
                "id": 52115,
                "title": "5种方法打破小调五声音阶的套路",
                "postDate": "2017-12-03T14:01:41.000+0000",
                "reviews": 0,
                "thumbsUp": 0,
                "openUpdate": 0
              }
            }
          ]
        }
