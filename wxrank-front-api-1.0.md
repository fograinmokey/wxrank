## 微信榜单
+ 2018年5月21日
    + API初始化
+ 2018年5月25日
    + 添加展示详情接口

+ Data
    + Topics - 文章表
        + seedId (long) - 来源id
        + type (int) - 主题类型(0：图文，1：视频，2：音频，3：音视频混合)
        + articleTopicId (long) - 米饭关联id
        + title (String) - 标题
        + content (String) - 内容
        + author (String) - 作者
        + postDate (date) - 文章发布时间
        + top (int) - 是否头条 0：否，1：是
        + original (int) - 是否原创 0：否，1：是
        + reviews (int) - 浏览量
        + thumbsUp (int) - 点赞数
        + seedTitle (String) - 公众号标题
        + seedLogo （String） - 公众号logo
        + enabled (int) - 是否可用
        + created (date) - 创建时间
        + modified (date) - 修改时间
        + creator (long) - 创建人
        + modifier (long) - 修改人
    + Rank - 排行表
        + type (int) - 类型，0：日榜 1:周榜 2：月榜
        + seedId (long) - 来源标识
        + startDate (int) - 开始日期
        + endDate (int) - 结束日期
        + postNum (int) - 发布次数
        + topicNum (int) - 文章数量
        + allReviews (int) - 总阅读数
        + topReviews (int) - 头条阅读数
        + maxReviews (int) - 最高阅读数
        + allPraises (int) - 总点赞数
        + topPraises (int) - 头条点赞数
        + maxPraises (int) - 最高点赞数
        + starIndex (double) - 米饭星指数
        + ranking (int) - 排名
        + averageReviews (int) - 平均阅读数
        + seedTitle (String) - 公众号标题
        + wechatId (String) - 公众号id

### 初始化查询信息 [GET] /wxrank/initInfo
+ Data
    + period 时间段展示
    + startDate 起始日期
    + count 样本数
    + deadline 数据截止日期
    
+ Response 200 (application/json)

        {
          "data": {
            "weeks": [
              {
                "period": "2018-05-13 ~ 2018-05-19",
                "startDate": 20180513
              },
              {
                "period": "2018-05-06 ~ 2018-05-12",
                "startDate": 20180506
              },
              {
                "period": "2018-04-29 ~ 2018-05-05",
                "startDate": 20180429
              },
              {
                "period": "2018-04-22 ~ 2018-04-28",
                "startDate": 20180422
              }
            ],
            "months": [
              {
                "period": "2018-04-01 ~ 2018-04-30",
                "startDate": 20180401
              },
              {
                "period": "2018-03-01 ~ 2018-03-31",
                "startDate": 20180301
              },
              {
                "period": "2018-02-01 ~ 2018-02-28",
                "startDate": 20180201
              },
              {
                "period": "2018-01-01 ~ 2018-01-31",
                "startDate": 20180101
              },
              {
                "period": "2017-12-01 ~ 2017-12-31",
                "startDate": 20171201
              }
            ],
            "count": 14998,
            "deadline": "2018-05-21"
          }
        }

### 文章榜单 [GET] /topics/rank?filter[period]=1&page[number]=1&page[size]=5

+ Description
    + [MUST] 获取50条以上的数据时需要登录
+ Parameters
    + filter[period] 时间，0：一天 1：一周 2：一个月
    + filter[type] 主题类型(0：图文，1：视频，2：音频，3：音视频混合)
    + filter[original] 是否原创 0：否，1：是
    + filter[minReviews] 最低浏览量
    + filter[seedId] 公众号标识
    + filter[orderBy] 排序，默认：点击量，1：点赞量，2：发布时间
+ Response 200 (application/json)
    
       {
          "meta": {
            "totalPages": 4,
            "totalElements": 16,
            "size": 5,
            "number": 1,
            "numberOfElements": 5,
            "first": true,
            "last": false,
            "sort": null
          },
          "links": {
            "self": "/topics/rank?filter[period]=1&page[number]=1&page[size]=5",
            "first": "/topics/rank?filter[period]=1&page[number]=1&page[size]=5",
            "next": "/topics/rank?filter[period]=1&page[number]=2&page[size]=5",
            "last": "/topics/rank?filter[period]=1&page[number]=4&page[size]=5"
          },
          "data": [
            {
              "id": 8045,
              "seedId": 52,
              "type": 0,
              "title": "本周六 影音联盟2018年中国4K超高清、全景声、智能巡展--郑州站",
              "postDate": "2018-05-14T04:38:48.000+0000",
              "original": 0,
              "reviews": 2,
              "thumbsUp": 0,
              "seedTitle": "HiFi秀网"
            },
            {
              "id": 8046,
              "seedId": 52,
              "type": 0,
              "title": "注意查收 HIFI秀会员活动福利：经典音乐剧《洗衣服》",
              "postDate": "2018-05-13T21:45:05.000+0000",
              "original": 0,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "HiFi秀网"
            },
            {
              "id": 8048,
              "seedId": 52,
              "type": 1,
              "title": "中国传统乐器Top10",
              "postDate": "2018-05-14T07:03:23.000+0000",
              "original": 0,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "HiFi秀网"
            },
            {
              "id": 10537,
              "seedId": 26,
              "type": 0,
              "title": "Randon蓝盾吉他提供2018吉他中国木吉他大赛奖品",
              "postDate": "2018-05-13T16:35:02.000+0000",
              "original": 0,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "吉他中国"
            },
            {
              "id": 10538,
              "seedId": 26,
              "type": 0,
              "title": "进军国际！民族品牌音乐驿站系列琴包征服美国专业杂志",
              "postDate": "2018-05-14T07:53:36.000+0000",
              "original": 0,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "吉他中国"
            }
          ]
        } 

### 文章详情 (GET) [/topics/show/{id}] 
+ Response 200 (application/json)

        {
          "data": {
            "origin": "http://mp.weixin.qq.com/s?__biz=MjM5MzY4NTMwNA==&mid=2650593928&idx=1&sn=3312eb0f25c805ea2f35eaf9a6f678c4&chksm=be9b30df89ecb9c99109e0123a544018d12c514dbc339ce8d453cb8e578cbc39879dae39df31&scene=27#wechat_redirect&seedId=126&groupSign=1524818221537&top=1&original=100",
            "articleTopicId": 997313
          }
        }


### 公众号榜单 [GET] wxrank?filer[type]=0&filter[startDate]=20180506&sort=-starIndex,-id&page[number]=1&page[size]=50
+ Description
    + [MUST] 获取50条以上的数据时需要登录
+ Parameters
    + filter[type] 类型，0：日榜 1:周榜 2：月榜
    + filter[startDate] 开始日期，格式yyyymmdd:20180521
    + sort=-starIndex,-id
    
+ Response 200 (application/json)

       {
        "meta": {
            "totalPages": 13,
            "totalElements": 64,
            "size": 5,
            "number": 1,
            "numberOfElements": 5,
            "first": true,
            "last": false,
            "sort": [
                {
                    "direction": "DESC",
                    "property": "star_index",
                    "ignoreCase": false,
                    "nullHandling": "NATIVE",
                    "ascending": false,
                    "descending": true
                },
                {
                    "direction": "DESC",
                    "property": "id",
                    "ignoreCase": false,
                    "nullHandling": "NATIVE",
                    "ascending": false,
                    "descending": true
                }
            ]
        },
        "links": {
            "self": "/wxrank?filer[type]=0&filter[startDate]=20180506&sort=-starIndex,-id&page[number]=1&page[size]=5",
            "first": "/wxrank?filer[type]=0&filter[startDate]=20180506&sort=-starIndex,-id&page[number]=1&page[size]=5",
            "next": "/wxrank?filer[type]=0&filter[startDate]=20180506&sort=-starIndex,-id&page[number]=2&page[size]=5",
            "last": "/wxrank?filer[type]=0&filter[startDate]=20180506&sort=-starIndex,-id&page[number]=13&page[size]=5"
        },
        "data": [
            {
                "id": 1326,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-05-31 15:00:33",
                "modified": "2018-05-31 15:00:33",
                "type": 0,
                "seedId": 11,
                "startDate": 20180506,
                "endDate": 20180506,
                "postNum": 1,
                "topicNum": 8,
                "allReviews": 157145,
                "topReviews": 40293,
                "maxReviews": 40293,
                "allPraises": 129,
                "topPraises": 93,
                "maxPraises": 93,
                "starIndex": 998.24,
                "ranking": 1,
                "averageReviews": 19644,
                "seedTitle": "伽柏传媒",
                "wechatId": "jiabaichuanmei",
                "seedLogo": "http://static.budee.com/iyyren/image/201802/07/0957/304640556708020224.jpg"
            },
            {
                "id": 1328,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-05-31 15:00:33",
                "modified": "2018-05-31 15:00:33",
                "type": 1,
                "seedId": 11,
                "startDate": 20180506,
                "endDate": 20180512,
                "postNum": 7,
                "topicNum": 56,
                "allReviews": 910539,
                "topReviews": 156447,
                "maxReviews": 40293,
                "allPraises": 295,
                "topPraises": 142,
                "maxPraises": 93,
                "starIndex": 920.89,
                "ranking": 2,
                "averageReviews": 16260,
                "seedTitle": "伽柏传媒",
                "wechatId": "jiabaichuanmei",
                "seedLogo": "http://static.budee.com/iyyren/image/201802/07/0957/304640556708020224.jpg"
            },
            {
                "id": 3376,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-05-31 15:05:07",
                "modified": "2018-05-31 15:05:07",
                "type": 1,
                "seedId": 30,
                "startDate": 20180506,
                "endDate": 20180512,
                "postNum": 6,
                "topicNum": 25,
                "allReviews": 135533,
                "topReviews": 54461,
                "maxReviews": 51999,
                "allPraises": 802,
                "topPraises": 454,
                "maxPraises": 235,
                "starIndex": 777.54,
                "ranking": 3,
                "averageReviews": 5422,
                "seedTitle": "摩登天空",
                "wechatId": "modernsky19971227",
                "seedLogo": "http://static.budee.com/iyyren/image/201803/08/1024/315156776297316352.jpg"
            },
            {
                "id": 2684,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-05-31 15:03:44",
                "modified": "2018-05-31 15:03:44",
                "type": 0,
                "seedId": 25,
                "startDate": 20180506,
                "endDate": 20180506,
                "postNum": 1,
                "topicNum": 2,
                "allReviews": 9079,
                "topReviews": 7722,
                "maxReviews": 7722,
                "allPraises": 84,
                "topPraises": 73,
                "maxPraises": 73,
                "starIndex": 709.68,
                "ranking": 4,
                "averageReviews": 4540,
                "seedTitle": "吉他联盟",
                "wechatId": "guitartogether",
                "seedLogo": "http://static.budee.com/iyyren/image/201803/15/1512/317765826600124416.jpg"
            },
            {
                "id": 2686,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-05-31 15:03:44",
                "modified": "2018-05-31 15:03:44",
                "type": 1,
                "seedId": 25,
                "startDate": 20180506,
                "endDate": 20180512,
                "postNum": 7,
                "topicNum": 14,
                "allReviews": 40070,
                "topReviews": 31065,
                "maxReviews": 8143,
                "allPraises": 294,
                "topPraises": 258,
                "maxPraises": 73,
                "starIndex": 634.15,
                "ranking": 5,
                "averageReviews": 2863,
                "seedTitle": "吉他联盟",
                "wechatId": "guitartogether",
                "seedLogo": "http://static.budee.com/iyyren/image/201803/15/1512/317765826600124416.jpg"
            }
        ]
      }
