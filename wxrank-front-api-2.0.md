+ 2018年7月2日
     + API初始化

## 微信榜单订阅号
### 查询公众号详情[GET]/wxSeeds/{id}
+ Parameters
    + id  
+ Description
    + ranking 
        + 当ranking为null时没有排名,当ranking为0时同样没有排名,即ranking不能为空且不为0.
    
+ Response 200 (Application/json)

         {
            "data": {
                "id": 12,
                "title": "古典音乐",
                "wechatId": "",
                "regionId": 0,
                "categoryId": 0,
                "info": {
                    "maxStarIndex": 165.58,
                    "maxRanking": 20,
                    "allReviewsUp": 0,
                    "rankingUp": 0,
                    "allPraisesUp": 0,
                    "averageReviewsUp": 0,
                    "topReviewsUp": 0,
                    "starIndexUp": 0
                },
                "ranks": [
                    {
                        "id": 1829,
                        "enabled": 1,
                        "creator": 0,
                        "modifier": 0,
                        "created": "2018-05-31 15:00:59",
                        "modified": "2018-05-31 15:00:59",
                        "type": 0,
                        "seedId": 12,
                        "startDate": 20180522,
                        "endDate": 20180522,
                        "postNum": 1,
                        "topicNum": 3,
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
                    .
                    .
                    .
                    ,
                    {
                        "id": 1794,
                        "enabled": 1,
                        "creator": 0,
                        "modifier": 0,
                        "created": "2018-05-31 15:00:58",
                        "modified": "2018-05-31 15:00:58",
                        "type": 0,
                        "seedId": 12,
                        "startDate": 20180423,
                        "endDate": 20180423,
                        "postNum": 1,
                        "topicNum": 3,
                        "allReviews": 0,
                        "topReviews": 0,
                        "maxReviews": 0,
                        "allPraises": 0,
                        "topPraises": 0,
                        "maxPraises": 0,
                        "starIndex": 0,
                        "ranking": 0,
                        "averageReviews": 0
                    }
                ]
            }
        }
