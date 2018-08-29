## 微信榜单
+ 2018年5月21日
    + API初始化
+ 2018年5月25日
    + 添加展示详情接口
+ 2018年8月8日
    + 更新公众号榜单，添加分类和地区排行
    + 更新文章榜单，添加分类和地区排行

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

### 文章榜单 [GET] /topics/rank?filter[period]=1&filter[regionId]=11&filter[categoryId]=10&page[number]=1&page[size]=5

+ Description
    + [MUST] 获取50条以上的数据时需要登录
    + [MUST] 用户登录后只能获取100条数据
+ Parameters
    + filter[period] 时间，0：一天 1：一周 2：一个月
    + filter[type] 主题类型(0：图文，1：视频，2：音频，3：音视频混合)
    + filter[original] 是否原创 0：否，1：是
    + filter[minReviews] 最低浏览量
    + filter[seedId] 公众号标识
    + filter[orderBy] 排序，默认：点击量，1：点赞量，2：发布时间
    + filter[regionId] 地区标识
    + filter[categoryId]=1 分类标识
+ Response 200 (application/json)
    
       {
        "meta": {
            "totalPages": 1,
            "totalElements": 3,
            "size": 20,
            "number": 1,
            "numberOfElements": 3,
            "first": true,
            "last": true,
            "sort": null
        },
        "links": {
            "self": "/topics/rank?filter[period]=2&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20",
            "first": "/topics/rank?filter[period]=2&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20",
            "last": "/topics/rank?filter[period]=2&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20"
        },
        "data": [
            {
                "id": 16363,
                "seedId": 43,
                "type": 0,
                "title": "被前员工指控涉嫌窃密并索赔1.05亿美元 华为回应称毫无依据",
                "postDate": "2018-07-16T04:15:00.000+0000",
                "original": 1,
                "reviews": 1,
                "thumbsUp": 0,
                "seedTitle": "声学在线",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1507/317764521857007616.jpg",
                "openUpdate": 0,
                "attachments": [
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130267.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130268.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130269.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130270.jpg"
                    }
                ]
            },
            {
                "id": 16364,
                "seedId": 43,
                "type": 0,
                "title": "Google play下载量是App Store2.4倍，收入却只有1/2，这是为什么？",
                "postDate": "2018-07-17T04:26:29.000+0000",
                "original": 1,
                "reviews": 1,
                "thumbsUp": 0,
                "seedTitle": "声学在线",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1507/317764521857007616.jpg",
                "openUpdate": 0,
                "attachments": [
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130267.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130272.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130273.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130274.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130275.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130276.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130277.jpg"
                    }
                ]
            },
            {
                "id": 16365,
                "seedId": 43,
                "type": 0,
                "title": "暴雨来得让人措不及防，别怕！人工智能预测在路上",
                "postDate": "2018-07-16T04:15:00.000+0000",
                "original": 1,
                "reviews": 1,
                "thumbsUp": 0,
                "seedTitle": "声学在线",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1507/317764521857007616.jpg",
                "openUpdate": 0,
                "attachments": [
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130278.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130279.jpg"
                    },
                    {
                        "filename": "//static.mifanxing.com/wx/image/252/1/130280.jpg"
                    }
                ]
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


### 公众号榜单 [GET] wxrank?filter[startDate]=20180625&filter[type]=0&filter[regionId]=11&filter[categoryId]=10&page[number]=1&page[size]=50
+ Description
    + [MUST] 获取50条以上的数据时需要登录
    + [MUST] 用户登录后只能获取100条数据
+ Parameters
    + filter[type] 类型，0：日榜 1:周榜 2：月榜
    + filter[startDate] 开始日期，格式yyyymmdd:20180521
    + filter[categoryId] 分类标识
    + filter[tagsId] 地区标识
    
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 1,
            "totalElements": 2,
            "size": 20,
            "number": 1,
            "numberOfElements": 2,
            "first": true,
            "last": true,
            "sort": [
              {
                "direction": "DESC",
                "property": "rank.star_index",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "descending": true,
                "ascending": false
              },
              {
                "direction": "DESC",
                "property": "rank.id",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "descending": true,
                "ascending": false
              }
            ]
          },
          "links": {
            "self": "/wxrank?filter[startDate]=20180625&filter[type]=0&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20",
            "first": "/wxrank?filter[startDate]=20180625&filter[type]=0&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20",
            "last": "/wxrank?filter[startDate]=20180625&filter[type]=0&filter[categoryId]=10&filter[regionId]=11&page[number]=1&page[size]=20"
          },
          "data": [
            {
              "seedId": 4,
              "postNum": 1,
              "topicNum": 1,
              "allReviews": 1667,
              "topReviews": 1667,
              "maxReviews": 1667,
              "allPraises": 11,
              "starIndex": 491.81,
              "ranking": 1,
              "averageReviews": 1667,
              "seedTitle": "拨片破坏狂吉他电吉他教学",
              "wechatId": "licklibrary",
              "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1556/302556684851757056.jpg"
            },
            {
              "seedId": 1,
              "postNum": 1,
              "topicNum": 1,
              "allReviews": 151,
              "topReviews": 151,
              "maxReviews": 151,
              "allPraises": 3,
              "starIndex": 229,
              "ranking": 2,
              "averageReviews": 151,
              "seedTitle": "AKAI雅佳乐园",
              "wechatId": "AKAIPro",
              "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1554/302556114032148480.jpg"
            }
          ]
        }
