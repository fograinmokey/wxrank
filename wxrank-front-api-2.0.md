+ 2018年7月2日
     + API初始化

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
### 查询公众号详情[GET]/wxSeeds/{id}
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
            "logo": "http://static.budee.com/iyyren/image/201802/01/1554/302556114032148480.jpg",
            "regionId": 11,
            "categoryId": 9,
            "info": {
                "maxStarIndex": 257.97,
                "maxRanking": null,
                "allReviewsUp": 150,
                "rankingUp": 0,
                "allPraisesUp": 5,
                "averageReviewsUp": -17,
                "topReviewsUp": 150,
                "starIndexUp": -68.80000000000001
            },
            "ranks": [
                {
                    "id": 8289,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:21",
                    "modified": "2018-05-31 14:58:21",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180513,
                    "endDate": 20170930,
                    "postNum": 2,
                    "topicNum": 2,
                    "allReviews": 334,
                    "topReviews": 334,
                    "maxReviews": 194,
                    "allPraises": 5,
                    "topPraises": 5,
                    "maxPraises": 5,
                    "starIndex": 128.1,
                    "ranking": 0,
                    "averageReviews": 167
                },
                {
                    "id": 25,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:26",
                    "modified": "2018-05-31 14:58:26",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180420,
                    "endDate": 20180420,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 184,
                    "topReviews": 184,
                    "maxReviews": 184,
                    "allPraises": 0,
                    "topPraises": 0,
                    "maxPraises": 0,
                    "starIndex": 196.9,
                    "ranking": 0,
                    "averageReviews": 184
                },
                {
                    "id": 24,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:26",
                    "modified": "2018-05-31 14:58:26",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180418,
                    "endDate": 20180418,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 236,
                    "topReviews": 236,
                    "maxReviews": 236,
                    "allPraises": 1,
                    "topPraises": 1,
                    "maxPraises": 1,
                    "starIndex": 250.75,
                    "ranking": 0,
                    "averageReviews": 236
                },
                {
                    "id": 21,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:25",
                    "modified": "2018-05-31 14:58:25",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180308,
                    "endDate": 20180308,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 205,
                    "topReviews": 205,
                    "maxReviews": 205,
                    "allPraises": 2,
                    "topPraises": 2,
                    "maxPraises": 2,
                    "starIndex": 248.54,
                    "ranking": 0,
                    "averageReviews": 205
                },
                {
                    "id": 18,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:24",
                    "modified": "2018-05-31 14:58:24",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180116,
                    "endDate": 20180116,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 163,
                    "topReviews": 163,
                    "maxReviews": 163,
                    "allPraises": 3,
                    "topPraises": 3,
                    "maxPraises": 3,
                    "starIndex": 235.22,
                    "ranking": 0,
                    "averageReviews": 163
                },
                {
                    "id": 16,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:24",
                    "modified": "2018-05-31 14:58:24",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20180115,
                    "endDate": 20180115,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 88,
                    "topReviews": 88,
                    "maxReviews": 88,
                    "allPraises": 0,
                    "topPraises": 0,
                    "maxPraises": 0,
                    "starIndex": 145.57,
                    "ranking": 0,
                    "averageReviews": 88
                },
                {
                    "id": 13,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-05-31 14:58:23",
                    "modified": "2018-05-31 14:58:23",
                    "type": 0,
                    "seedId": 1,
                    "startDate": 20171225,
                    "endDate": 20171225,
                    "postNum": 1,
                    "topicNum": 1,
                    "allReviews": 229,
                    "topReviews": 229,
                    "maxReviews": 229,
                    "allPraises": 2,
                    "topPraises": 2,
                    "maxPraises": 2,
                    "starIndex": 257.97,
                    "ranking": 0,
                    "averageReviews": 229
                }
            ],
            "categories": {
                "id": 9,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-07-31 16:43:10",
                "modified": "2018-07-31 16:43:10",
                "title": "测试类"
            },
            "regions": {
                "id": 11,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-06-08 13:49:23",
                "modified": "2018-06-08 13:49:23",
                "parentId": 5,
                "title": "保定市",
                "leaf": 1,
                "quotes": 0,
                "displayOrder": 0,
                "parent": {
                    "id": 5,
                    "enabled": 1,
                    "creator": 0,
                    "modifier": 0,
                    "created": "2018-06-08 13:49:23",
                    "modified": "2018-06-08 13:49:23",
                    "parentId": 0,
                    "title": "河北省",
                    "leaf": 0,
                    "quotes": 3,
                    "displayOrder": 0
                }
            },
            "tags": [
                "体育",
                "健康"
            ]
        }
      }
