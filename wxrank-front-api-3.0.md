## 自定义榜单
+ 2018年10月16日
    +  自定义榜单初始化

+ 2018年10月23日
    +  添加我的榜单中榜单已选公众号列表 

+ Data
    + CustomRanks - 自定义榜单表
        + id (Long) - ID
        + title (String) - 榜单名称
        + seedNum (int) - 公众号数量
        + description (String) - 描述
        + reviews (int) - 阅读数
        + status (int) - 公开状态 0:不公开(默认) 1:公开
        + enabled (int) - 使能 0禁止 1启用
        + creator (Long) - 创建人
        + modifier (Long) - 修改人
        + created (date) - 创建时间
        + modified (date) - 修改时间
    + CustomRankSeeds - 自定义榜单公众号表
        + id (Long) - ID
        + customRanksId (Long) - 自定义榜单id
        + seedId (Long) - 公众号id
        + enabled (int) - 使能 0禁止 1启用
        + creator (Long) - 创建人
        + modifier (Long) - 修改人
        + created (date) - 创建时间
        + modified (date) - 修改时间 

### 增加 [POST] /wxCustomRanks
+ Description
    + [MUST] authenticated
+ Request (application/json)
    
      {
    	 "data":{
    		"title":"竞争对手",
    		"description":"发生法律描述"
    	  }
      }

+ Response (application/json)
    
      {
         "data": {
            "id": 2,
            "type": "wxCustomRanks"
         }
      }

### 修改[PUTCH] /wxCustomRanks/{id}
+ Description
    + [MUST] authenticated
+ Request (application/json)
    
      {
    	  "data":{
    		"title":"竞争对手1",
    		"description":"竞争对手1描述"
    	  }
      }

+ Response 200

### 我的榜单列表 [GET] /wxCustomRanks/mineRanks?page[number]=1&page[size]=10
+ Description
    + [MUST] authenticated
+ Request (application/json)
    
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
            "self": "/wxCustomRanks?page[number]=1&page[size]=10",
            "first": "/wxCustomRanks?page[number]=1&page[size]=10",
            "last": "/wxCustomRanks?page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 1,
                "enabled": 0,
                "creator": 0,
                "modifier": 0,
                "modified": "2018-10-15 11:13:35",
                "title": "发生的",
                "seedNum": 5,
                "description": "",
                "reviews": 0,
                "status": 0
            },
            {
                "id": 2,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-10-15 10:43:58",
                "modified": "2018-10-15 11:12:55",
                "title": "竞争对手1",
                "seedNum": 0,
                "description": "竞争对手1描述",
                "reviews": 0,
                "status": 0
            },
            {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-10-15 10:45:54",
                "modified": "2018-10-15 10:45:54",
                "title": "竞争对手2",
                "seedNum": 0,
                "description": "发包人挺好认同的方法描述",
                "reviews": 0,
                "status": 0
            }
        ]
      }

### 我的榜单中榜单已选公众号列表 [GET] /wxCustomRanks/mineRanksSeeds/{customRankId}
+ Description
    + [MUST] authenticated
+ Parameters
    + customRankId 我的榜单榜单ID
+ Request (application/json)

      {
        "data": [
            {
                "id": 76,
                "seedId": 73,
                "seedTitle": "米饭星",
                "wechatId": "mifanxing1"
            },
            {
                "id": 77,
                "seedId": 90,
                "seedTitle": "音频帮丨大事件",
                "wechatId": "audiooh"
            },
            {
                "id": 78,
                "seedId": 95,
                "seedTitle": "音频帮",
                "wechatId": "yinpinbang"
            },
            {
                "id": 79,
                "seedId": 46,
                "seedTitle": "太平宝迪",
                "wechatId": "gh_6ba060361838"
            },
            {
                "id": 81,
                "seedId": 420,
                "seedTitle": "太平宝迪售后服务",
                "wechatId": "Budee-Service"
            }
        ]
      }


### 自定义榜单列表 [GET] /wxCustomRanks?filter[status]=1&page[number]=1&page[size]=10
+ Parameters
    + filter[status] 公开状态 0:不公开 1:公开

+ Request (application/json)
    
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
            "self": "wxCustomRanks/customRanks?filter[status]=1&page[number]=1&page[size]=10",
            "first": "wxCustomRanks/customRanks?filter[status]=1&page[number]=1&page[size]=10",
            "last": "wxCustomRanks/customRanks?filter[status]=1&page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 2,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-10-15 10:43:58",
                "modified": "2018-10-17 11:23:00",
                "title": "竞争对手1",
                "seedNum": 8,
                "description": "竞争对手1描述",
                "reviews": 2,
                "status": 1
            },
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "title": "冰点百分百",
                "seedNum": 0,
                "description": "刚好能够放你那描述",
                "reviews": 0,
                "status": 1
            }
        ]
      }

### 删除 [DELETE] /wxCustomRanks/{id}
+ Description
    + [MUST] authenticated
+ Parameters
    + 删除榜单的同时也将榜单中的所有公众号删除 
+ Response 204

### 增加自定义榜单下公众号 [POST] /wxCustomRanks/seeds
+ Description
    + [MUST] authenticated
+ Request (application/json)
    
      {
        "data":{
        	"customRanksId":1,
        	"seedIds":[1,2,3,4,5]
        }
      }

+ Response (application/json)

      {
       "data": 5
      }

### 榜单下公众号列表 [GET] /wxrank/customRankSeeds?filter[customRanksId]=1&filter[type]=0&filter[startDate]=20180805

+ Parameters
    + filter[customRanksId] 自定义榜单ID
    + filter[type] 类型，0：日榜 1:周榜 2：月榜
    +  filter[startDate] 开始日期，格式yyyymmdd:20180805

+ Response 200 (application/json)
    
      {
        "meta": {
            "totalPages": 1,
            "totalElements": 6,
            "size": 10,
            "number": 1,
            "numberOfElements": 6,
            "first": true,
            "last": true,
            "sort": null
        },
        "links": {
            "self": "wxrank/customRankSeeds?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "first": "wxrank/customRankSeeds?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "last": "wxrank/customRankSeeds?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 64400,
                "seedId": 75,
                "postNum": 1,
                "topicNum": 6,
                "allReviews": 64385,
                "maxReviews": 24609,
                "allPraises": 815,
                "starIndex": 944.37,
                "ranking": 0,
                "averageReviews": 10731,
                "seedTitle": "乐器演奏家",
                "wechatId": "yqyanzoujia",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201807/20/1000/363710671256436736.jpg"
            },
            {
                "id": 64364,
                "seedId": 69,
                "postNum": 1,
                "topicNum": 1,
                "allReviews": 3449,
                "maxReviews": 3449,
                "allPraises": 9,
                "starIndex": 577.73,
                "ranking": 0,
                "averageReviews": 3449,
                "seedTitle": "音乐人网",
                "wechatId": "YYRW365",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1447/317759625313271808.jpg"
            },
            {
                "id": 64324,
                "seedId": 63,
                "postNum": 1,
                "topicNum": 5,
                "allReviews": 6821,
                "maxReviews": 2969,
                "allPraises": 69,
                "starIndex": 568.64,
                "ranking": 0,
                "averageReviews": 1365,
                "seedTitle": "影音新生活",
                "wechatId": "Cloud9AV",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg"
            },
            {
                "id": 64346,
                "seedId": 67,
                "postNum": 1,
                "topicNum": 4,
                "allReviews": 4440,
                "maxReviews": 1570,
                "allPraises": 67,
                "starIndex": 518.75,
                "ranking": 0,
                "averageReviews": 1110,
                "seedTitle": "音乐财经",
                "wechatId": "musicbusiness",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201808/02/1111/368439525627805696.jpg"
            },
            {
                "id": 65058,
                "seedId": 8,
                "postNum": 1,
                "topicNum": 1,
                "allReviews": 1638,
                "maxReviews": 1638,
                "allPraises": 6,
                "starIndex": 477.23,
                "ranking": 0,
                "averageReviews": 1638,
                "seedTitle": "Eplay吉他",
                "wechatId": "eplayguitar",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/03/1621/303287728718626816.jpg"
            },
            {
                "id": 64340,
                "seedId": 66,
                "postNum": 1,
                "topicNum": 1,
                "allReviews": 1314,
                "maxReviews": 1314,
                "allPraises": 15,
                "starIndex": 470.18,
                "ranking": 0,
                "averageReviews": 1314,
                "seedTitle": "音频圈",
                "wechatId": "AllAudio2017",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1449/317760005560483840.jpg"
            }
        ]
      }


### 删除榜单下公众号 [DELETE] /wxCustomRanks/seeds?customRanksId=1&seedId=66 
+ Description
    + [MUST] authenticated
+ Parameters
    + customRanksId 榜单ID
    + seedId 公众号ID
+ Response 200
    + 删除条数：1

### 榜单下文章列表 [GET] /topics/customRankTopics?filter[customRanksId]=1&filter[period]=0
+ Parameters
    + filter[customRanksId] 自定义榜单ID
    + filter[period] 时间，0：一天 1：一周 2：一个月

+ Response 200 (application/json)

        {
        "meta": {
            "totalPages": 1,
            "totalElements": 9,
            "size": 10,
            "number": 1,
            "numberOfElements": 9,
            "first": true,
            "last": true,
            "sort": null
        },
        "links": {
            "self": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "first": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "last": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=1&page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 82449,
                "boost": 1,
                "seedId": 63,
                "title": "“温暖心灵的天籁之音”聆听小野丽莎9首浪漫温情的爵士",
                "reviews": 2209,
                "thumbsUp": 25,
                "seedTitle": "影音新生活",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg",
                "openUpdate": 0
            },
            {
                "id": 82458,
                "boost": 1,
                "seedId": 67,
                "title": "未来五年，中国音乐产业将呈现什么状态？",
                "reviews": 2047,
                "thumbsUp": 18,
                "seedTitle": "音乐财经",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201808/02/1111/368439525627805696.jpg",
                "openUpdate": 0
            },
            {
                "id": 82457,
                "boost": 1,
                "seedId": 67,
                "title": "30强高校战队出炉，酷狗校际音超联赛尽显校园音乐魅力",
                "reviews": 1148,
                "thumbsUp": 6,
                "seedTitle": "音乐财经",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201808/02/1111/368439525627805696.jpg",
                "openUpdate": 0
            },
            {
                "id": 82455,
                "boost": 1,
                "seedId": 67,
                "title": "飞儿乐团主唱Faye被踢，牛姐演唱会曝音响事故？ | 音乐鲜活事儿",
                "reviews": 511,
                "thumbsUp": 6,
                "seedTitle": "音乐财经",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201808/02/1111/368439525627805696.jpg",
                "openUpdate": 0
            },
            {
                "id": 82456,
                "boost": 1,
                "seedId": 67,
                "title": "屡见不鲜的“音乐节骗局”",
                "reviews": 427,
                "thumbsUp": 6,
                "seedTitle": "音乐财经",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201808/02/1111/368439525627805696.jpg",
                "openUpdate": 0
            },
            {
                "id": 82451,
                "boost": 1,
                "seedId": 63,
                "title": "新品 | 业界一致推崇，Absolute845 25周年纪念版：意大利优力声 Unison Research",
                "reviews": 233,
                "thumbsUp": 1,
                "seedTitle": "影音新生活",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg",
                "openUpdate": 0
            },
            {
                "id": 82450,
                "boost": 1,
                "seedId": 63,
                "title": "设计丨好看到爆的北欧风，看完瞬间想拆了自己房子！",
                "reviews": 174,
                "thumbsUp": 0,
                "seedTitle": "影音新生活",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg",
                "openUpdate": 0
            },
            {
                "id": 82452,
                "boost": 1,
                "seedId": 63,
                "title": "有奖活动 | 天猫10周年“遇 • 见新声”定义心中最美的声音！",
                "reviews": 69,
                "thumbsUp": 0,
                "seedTitle": "影音新生活",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg",
                "openUpdate": 0
            },
            {
                "id": 82448,
                "boost": 1,
                "seedId": 63,
                "title": "招募 | 服务影音行业的顶级标准课程：2018 PVA Video Calibration Training视频培训课程",
                "reviews": 49,
                "thumbsUp": 0,
                "seedTitle": "影音新生活",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1452/317760864881098752.jpg",
                "openUpdate": 0
            }
        ]
      }

### 获取重复的文章 [GET] /topics/getRepeatTopics/{topicId}?page[number]=1&page[size]=3

+ Description
    + 点击详情时ID取articleTopicId
    + 如果articleTopicId=0，则详情需要跳转到from.origin
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 2,
            "totalElements": 5,
            "size": 3,
            "number": 1,
            "numberOfElements": 3,
            "first": true,
            "last": false,
            "sort": null
          },
          "links": {
            "self": "/topics/getRepeatTopics?page[number]=1&page[size]=3",
            "first": "/topics/getRepeatTopics?page[number]=1&page[size]=3",
            "next": "/topics/getRepeatTopics?page[number]=2&page[size]=3",
            "last": "/topics/getRepeatTopics?page[number]=2&page[size]=3"
          },
          "data": [
            {
              "id": 17852,
              "enabled": 1,
              "created": "2018-05-31 12:48:34",
              "modified": "2018-11-05 18:27:13",
              "boost": 1,
              "articleTopicId": 1203441,
              "seedId": 51,
              "type": 0,
              "title": "科普 | 听现场真的会提高自己对音响表现的认知么？",
              "postDate": "2018-04-03T07:15:00.000+0000",
              "original": 0,
              "isRepeat": 1,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "演艺科技传媒",
              "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1504/317763845617762304.jpg",
              "openUpdate": 0
            },
            {
              "id": 29630,
              "enabled": 1,
              "created": "2018-06-01 14:44:42",
              "modified": "2018-11-05 18:27:13",
              "boost": 1,
              "articleTopicId": 1146658,
              "seedId": 52,
              "type": 0,
              "title": "听现场与音响耳机聆听",
              "postDate": "2018-04-10T04:54:50.000+0000",
              "original": 0,
              "isRepeat": 1,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "HiFi秀",
              "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1442/317758375146438656.jpg",
              "openUpdate": 0
            },
            {
              "id": 28787,
              "enabled": 1,
              "created": "2018-06-01 14:20:51",
              "modified": "2018-11-05 18:27:13",
              "boost": 1,
              "articleTopicId": 1165925,
              "seedId": 42,
              "type": 0,
              "title": "听现场与音响耳机聆听",
              "postDate": "2018-04-24T00:36:31.000+0000",
              "original": 0,
              "isRepeat": 1,
              "reviews": 0,
              "thumbsUp": 0,
              "seedTitle": "声学楼电声技术网络交流平台",
              "seedLogo": "//static.mifanxing.com/iyyren/image/201803/15/1507/317764646700466176.jpg",
              "openUpdate": 0
            }
          ]
        }
