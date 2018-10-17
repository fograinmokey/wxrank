+ 2018年10月16日
    +  自定义榜单初始化
## 自定义榜单
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

### 我的榜单列表 [GET] /wxCustomRanks?page[number]=1&page[size]=10
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

### 自定义榜单列表 [GET] /wxCustomRanks/customRanks?filter[status]=1&page[number]=1&page[size]=10
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
            "totalElements": 5,
            "size": 10,
            "number": 1,
            "numberOfElements": 5,
            "first": true,
            "last": true,
            "sort": null
        },
        "links": {
            "self": "wxrank/customRank?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "first": "wxrank/customRank?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "last": "wxrank/customRank?filter[startDate]=20180805&filter[type]=0&filter[customRanksId]=1&page[number]=1&page[size]=10"
        },
        "data": [
               {
                "id": 64400,
                "postNum": 1,
                "allReviews": 15389,
                "maxReviews": 6897,
                "allPraises": 227,
                "starIndex": 698.94,
                "ranking": 0,
                "averageReviews": 2565,
                "seedTitle": "乐器演奏家"
            },
            {
                "id": 64364,
                "postNum": 1,
                "allReviews": 2016,
                "maxReviews": 2016,
                "allPraises": 9,
                "starIndex": 510.45,
                "ranking": 0,
                "averageReviews": 2016,
                "seedTitle": "音乐人网"
            },
            {
                "id": 64324,
                "postNum": 1,
                "allReviews": 4041,
                "maxReviews": 2170,
                "allPraises": 48,
                "starIndex": 506.1,
                "ranking": 0,
                "averageReviews": 809,
                "seedTitle": "影音新生活"
            },
            {
                "id": 64346,
                "postNum": 1,
                "allReviews": 2456,
                "maxReviews": 1147,
                "allPraises": 32,
                "starIndex": 444.92,
                "ranking": 0,
                "averageReviews": 614,
                "seedTitle": "音乐财经"
            },
            {
                "id": 64340,
                "postNum": 1,
                "allReviews": 958,
                "maxReviews": 958,
                "allPraises": 11,
                "starIndex": 428.03,
                "ranking": 0,
                "averageReviews": 958,
                "seedTitle": "音频圈"
            }
        ]
      }


### 删除榜单下公众号 [DELETE] /wxCustomRanks/seed/{id} 
+ Description
    + [MUST] authenticated
+ Response 204  

### 榜单下文章列表 [GET] /topics/customRankTopics?filter[customRanksId]=1&filter[period]=0
+ Parameters
    + filter[customRanksId] 自定义榜单ID
    + filter[period] 时间，0：一天 1：一周 2：一个月

+ Response 200 (application/json)

        {
        "meta": {
            "totalPages": 2,
            "totalElements": 12,
            "size": 10,
            "number": 1,
            "numberOfElements": 12,
            "first": true,
            "last": false,
            "sort": null
        },
        "links": {
            "self": "/topics/customRankTopics?filter[startDate]=2018-08-16&filter[endDate]=2018-08-17&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "first": "/topics/customRankTopics?filter[startDate]=2018-08-16&filter[endDate]=2018-08-17&filter[customRanksId]=1&page[number]=1&page[size]=10",
            "next": "/topics/customRankTopics?filter[startDate]=2018-08-16&filter[endDate]=2018-08-17&filter[customRanksId]=1&page[number]=2&page[size]=10",
            "last": "/topics/customRankTopics?filter[startDate]=2018-08-16&filter[endDate]=2018-08-17&filter[customRanksId]=1&page[number]=2&page[size]=10"
        },
        "data": [
            {
                "boost": 1,
                "title": "品味经典情歌，回忆动人的爱恋",
                "reviews": 1649,
                "thumbsUp": 23,
                "seedTitle": "影音新生活",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "经典类型片究竟如何抓住观众眼球？——探寻《巨齿鲨》和《延禧攻略》爆火的原因",
                "reviews": 838,
                "thumbsUp": 9,
                "seedTitle": "文化产业评论",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "内容产业的本质判断：信息接收的过去、现在与未来",
                "reviews": 367,
                "thumbsUp": 6,
                "seedTitle": "文化产业评论",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "最新！《2017中国文物艺术品全球拍卖统计年报》（全文）",
                "reviews": 255,
                "thumbsUp": 0,
                "seedTitle": "文化产业评论",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "设计丨新美式，大美至简的高贵气质！",
                "reviews": 242,
                "thumbsUp": 2,
                "seedTitle": "影音新生活",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "新品首发 | Denon天龙 AVR-X2500H 7.2声道4K AV接收机",
                "reviews": 169,
                "thumbsUp": 1,
                "seedTitle": "影音新生活",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "倒计时一周，飞利信（3号馆3112展位）约您来看PALM EXPO 2018",
                "reviews": 135,
                "thumbsUp": 3,
                "seedTitle": "飞利信",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "LD systems成为营造舒适餐厅氛围的关键",
                "reviews": 107,
                "thumbsUp": 0,
                "seedTitle": "亚洲专业音响",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "“沉浸式”音频已成为席卷欧洲的行业革命",
                "reviews": 104,
                "thumbsUp": 0,
                "seedTitle": "亚洲专业音响",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "推荐 | “衰减率低、可弯折、耐用度高，高品质的HDMI线”FIBBR Ultra Pro 光纤HDMI线",
                "reviews": 100,
                "thumbsUp": 1,
                "seedTitle": "影音新生活",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "热点 | 2018-2019 EISA获奖名单KEF Q系列荣获大奖",
                "reviews": 91,
                "thumbsUp": 2,
                "seedTitle": "影音新生活",
                "openUpdate": 0
            },
            {
                "boost": 1,
                "title": "雅马哈旗舰级数字混音系统RIVAGE PM10北京发布会完满结束",
                "reviews": 58,
                "thumbsUp": 0,
                "seedTitle": "亚洲专业音响",
                "openUpdate": 0
            }
        ]
      }


