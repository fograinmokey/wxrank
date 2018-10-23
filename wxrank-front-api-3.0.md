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
            "totalElements": 11,
            "size": 25,
            "number": 1,
            "numberOfElements": 11,
            "first": true,
            "last": true,
            "sort": null
        },
        "links": {
            "self": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=42&page[number]=1&page[size]=25",
            "first": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=42&page[number]=1&page[size]=25",
            "last": "/topics/customRankTopics?filter[period]=1&filter[customRanksId]=42&page[number]=1&page[size]=25"
        },
        "data": [
            {
                "id": 77907,
                "boost": 1,
                "title": "“好se之徒·为声而生”1500多名色粉相约SE音乐节！",
                "reviews": 2199,
                "thumbsUp": 31,
                "seedTitle": "CA001",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/02/1803/302951018814128128.jpg",
                "openUpdate": 0
            },
            {
                "id": 77860,
                "boost": 1,
                "title": "老鹰乐队-加州旅馆 全曲中文讲解和示范丨主讲人Danny Gill丨提供下载地址",
                "reviews": 2176,
                "thumbsUp": 19,
                "seedTitle": "拨片破坏狂吉他电吉他教学",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1556/302556684851757056.jpg",
                "openUpdate": 0
            },
            {
                "id": 78290,
                "boost": 1,
                "title": "迈克尔杰克逊Beat It，Solo段落详细讲解和示范丨视频，附下载",
                "reviews": 1479,
                "thumbsUp": 7,
                "seedTitle": "拨片破坏狂吉他电吉他教学",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1556/302556684851757056.jpg",
                "openUpdate": 0
            },
            {
                "id": 77913,
                "boost": 1,
                "title": "Shot to Thrill-AC/DC 华彩段讲解-节奏/Solo/Breakdown",
                "reviews": 1268,
                "thumbsUp": 9,
                "seedTitle": "拨片破坏狂吉他电吉他教学",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1556/302556684851757056.jpg",
                "openUpdate": 0
            },
            {
                "id": 78034,
                "boost": 1,
                "title": "看不见的“声音”威胁，这种现象音响人都遇到过！",
                "reviews": 620,
                "thumbsUp": 3,
                "seedTitle": "艾维音响网",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1553/302555982347780096.jpg",
                "openUpdate": 0
            },
            {
                "id": 78027,
                "boost": 1,
                "title": "奥运之城—青岛再次扬帆逐梦 ---开幕式谱写省运之最",
                "reviews": 362,
                "thumbsUp": 7,
                "seedTitle": "CA001",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/02/1803/302951018814128128.jpg",
                "openUpdate": 0
            },
            {
                "id": 78297,
                "boost": 1,
                "title": "2018上海乐展：丹拿 LYD 的“表哥”要来?",
                "reviews": 323,
                "thumbsUp": 10,
                "seedTitle": "叉烧网",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/02/1804/302951169758740480.jpg",
                "openUpdate": 0
            },
            {
                "id": 78044,
                "boost": 1,
                "title": "第37期录音混音班开始报名！目前只有4个名额哦。",
                "reviews": 271,
                "thumbsUp": 1,
                "seedTitle": "Allanwang Studio",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1552/302555646887346176.jpg",
                "openUpdate": 0
            },
            {
                "id": 78026,
                "boost": 1,
                "title": "与梦想同行 ESS声动2018阿拉善Dreamland电音节",
                "reviews": 209,
                "thumbsUp": 4,
                "seedTitle": "CA001",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/02/1803/302951018814128128.jpg",
                "openUpdate": 0
            },
            {
                "id": 78035,
                "boost": 1,
                "title": "新品发布| 全静音自动LED灯具，和“噪音”说拜拜！",
                "reviews": 141,
                "thumbsUp": 3,
                "seedTitle": "艾维音响网",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1553/302555982347780096.jpg",
                "openUpdate": 0
            },
            {
                "id": 78036,
                "boost": 1,
                "title": "现场直击| 全球3900家厂商争奇斗艳",
                "reviews": 131,
                "thumbsUp": 3,
                "seedTitle": "艾维音响网",
                "seedLogo": "//static.mifanxing.com/iyyren/image/201802/01/1553/302555982347780096.jpg",
                "openUpdate": 0
            }
        ]
      }


