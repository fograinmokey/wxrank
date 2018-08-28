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
### 列表 (客户端) [GET] wxTags?sort=-quotes
    
+ Parameters
     + quotes 公众号引用次数/公众号的个数
     + sort -quotes(引用次数由多到少) 
+ Request (application/json)

        {
            "meta": {
                "totalPages": 1,
                "totalElements": 7,
                "size": 10,
                "number": 1,
                "numberOfElements": 7,
                "first": true,
                "last": true,
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
                "self": "/wxTags?sort=-quotes&filter[quotes:gt]=0&page[number]=1&page[size]=10",
                "first": "/wxTags?sort=-quotes&filter[quotes:gt]=0&page[number]=1&page[size]=10",
                "last": "/wxTags?sort=-quotes&filter[quotes:gt]=0&page[number]=1&page[size]=10"
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
                    "displayOrder": 0
                },
                {
                    "id": 49,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-22 17:44:21",
                    "modified": "2018-08-22 17:44:21",
                    "title": "娱乐",
                    "quotes": 9,
                    "displayOrder": 0
                },
                {
                    "id": 76,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-22 17:51:42",
                    "modified": "2018-08-22 17:51:42",
                    "title": "新鲜",
                    "quotes": 6,
                    "displayOrder": 0
                },
                {
                    "id": 39,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-09 14:15:03",
                    "modified": "2018-08-09 14:15:03",
                    "title": "生活",
                    "quotes": 4,
                    "displayOrder": 0
                },
                {
                    "id": 18,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-03 09:08:03",
                    "modified": "2018-08-03 09:08:03",
                    "title": "体育",
                    "quotes": 3,
                    "displayOrder": 0
                },
                {
                    "id": 15,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-03 18:59:19",
                    "modified": "2018-08-03 18:59:19",
                    "title": "音乐",
                    "quotes": 1,
                    "displayOrder": 0
                },
                {
                    "id": 95,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-08-23 17:44:30",
                    "modified": "2018-08-23 17:44:30",
                    "title": "青春",
                    "quotes": 1,
                    "displayOrder": 0
                }
            ]
        }

      
