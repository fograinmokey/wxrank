+ 2018年9月11日
    + 弃用分类管理初始化
    + 榜单文章快速移除
+ 2018年11月9日
    + 添加重复文章列表
+ 2018年11月30日
    +  词典管理初始化
    +  词典分类初始化
## 词典管理
+ Data
    + NlpUserDic 词典表
        + id (Long) - ID
        + categoryId (Long) - 分类
        + logo - 词条logo
        + word (String) - 词
        + language (int) -  0:中文; 1:英文
        + description (String) - 描述
        + wordTranslation (String) - 单词翻译
        + descriptionTranslation (String) - 描述翻译
        + frequency (int) - 词频
        + isShow (int) - 0:不展示;  1:展示; 有些词只用于分词词典，不需要展示
        + version (Long) - 版本
        + enabled (int) - 使能 0禁止 1启用
        + creator (Long) - 创建人
        + modifier (Long) - 修改人
        + created (date) - 创建时间
        + modified (date) - 修改时间 
    + DicSynonym 同义词表
        + id (Long) - ID
        + dicId (Long) - 词id
        + synonym (String) - 同义词
        + version (Long) - 版本

### 增加 [POST] /nlpUserDic
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Request (application/json)
    
      {
    	"data":{
    		"categoryId":1,
              "logo": "//static.mifanxing.com/iyyren/image/201806/06/1638/347865732702420992.jpg",
    		"word":"爱维德",
    		"language":0,
    		"description":"寓意着无论什么时候都赋予您新鲜的感觉”。AVID品牌永远是生动的、有活力的品牌，是充满生命力的活泼向导的品牌，雅妃德使用天然的材料而研发的具有差异化的机能性化妆品，可赋予肌肤纯净而健康的肤质。",
    		"wordTranslation":"AVID",
    		"descriptionTranslation":"It means to give you fresh feeling whenever it comes to you. AVID brand is always a lively and dynamic brand, and a brand full of vitality and lively guide. The functional cosmetics developed by AVID using natural materials can give skin pure and healthy skin.",
    		"frequency":"888",
    		"isShow":"1",
    		"version":"1",
    		"synonyms":[
          			"AVID官网",
          			"韩国雅妃德",
          			"雅妃德"
          	]
    	  }
      }

+ Response (application/json)
    
      {
        "data": {
            "id": 19,
            "type": "nlpUserDic"
        }
      }

### 修改[PUTCH] /nlpUserDic/{id}
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Request (application/json)
    
      {
    	"data":{
    		"categoryId":1,
              "logo": "//static.mifanxing.com/iyyren/image/201806/06/1638/347865732702420992.jpg",
    		"word":"爱维德1",
    		"language":0,
    		"description":"寓意着无论什么时候都赋予您新鲜的感觉”。AVID品牌永远是生动的、有活力的品牌，是充满生命力的活泼向导的品牌，雅妃德使用天然的材料而研发的具有差异化的机能性化妆品，可赋予肌肤纯净而健康的肤质。",
    		"wordTranslation":"AVID",
    		"descriptionTranslation":"It means to give you fresh feeling whenever it comes to you. AVID brand is always a lively and dynamic brand, and a brand full of vitality and lively guide. The functional cosmetics developed by AVID using natural materials can give skin pure and healthy skin.",
    		"frequency":"888",
    		"isShow":"1",
    		"version":"1",
    		"synonyms":[
          			"AVID官网",
          			"韩国雅妃德",
          			"雅妃德1"
          	]
    	  }
      }

+ Response 200

### 词典详情 (GET) /nlpUserDic{id}
+ Response 200 (application/json)

      {
        "data": {
            "id": 19,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-11-30 17:20:22",
            "modified": "2018-11-30 17:45:08",
            "categoryId": 1,
            "logo": "//static.mifanxing.com/iyyren/image/201806/06/1638/347865732702420992.jpg",
            "word": "爱维德",
            "language": 0,
            "description": "寓意着无论什么时候都赋予您新鲜的感觉”。AVID品牌永远是生动的、有活力的品牌，是充满生命力的活泼向导的品牌，雅妃德使用天然的材料而研发的具有差异化的机能性化妆品，可赋予肌肤纯净而健康的肤质。",
            "wordTranslation": "AVID",
            "descriptionTranslation": "It means to give you fresh feeling whenever it comes to you. AVID brand is always a lively and dynamic brand, and a brand full of vitality and lively guide. The functional cosmetics developed by AVID using natural materials can give skin pure and healthy skin.",
            "frequency": 888,
            "isShow": 1,
            "version": 1,
            "nlpDicCategories": {
                "id": 1,
                "title": "品牌"
            },
            "synonyms": [
                "AVID官网",
                "雅妃德1",
                "韩国雅妃德"
            ]
        }
      }

### 词典列表 [GET] /nlpUserDic?page[number]=1&page[size]=10
+ Parameters
     + id 
     + word
        + 查询示例：filter[word:like]=%25米饭星%25 （'%25'为'%'的转义）
     + filter[categoryId] 词典分类id
     + sort -modified (从新到旧) | modified(从旧到新) 
     + isShow  0:不展示，1:展示； 有些词只用于分词词典，不需要展示
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
            "self": "/nlpUserDic?page[number]=1&page[size]=10",
            "first": "/nlpUserDic?page[number]=1&page[size]=10",
            "last": "/nlpUserDic?page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-29 11:21:22",
                "modified": "2018-11-29 11:21:22",
                "categoryId": 7,
                "logo": "//static.mifanxing.com/iyyren/image/201806/06/1638/347865732702420992.jpg",
                "word": "米饭星",
                "language": 0,
                "description": "米饭星向您提供国内最大的音频产品数据中心，共有来自15+行业网站的30W+的音频设备供您检索。您可以查分类、查品牌、查价格、看图片、一站式，随时随地、每时每刻的检索您需要的音乐设备！",
                "wordTranslation": "mifanxing",
                "descriptionTranslation": "Rice star provides you with the largest audio product data center in China, with 30W+ audio equipment from 15+ industry websites for your retrieval.You can check the classification, check the brand, check the price, see pictures, one-stop, anytime, anywhere, all the time to search your need music equipment!",
                "frequency": 111,
                "isShow": 1,
                "version": 1,
                "nlpDicCategories": {
                    "id": 7,
                    "title": "音乐类..."
                }
            },
            {
                "id": 19,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-30 17:20:22",
                "modified": "2018-11-30 17:22:35",
                "categoryId": 1,
                "word": "爱维德1",
                "language": 0,
                "description": "寓意着无论什么时候都赋予您新鲜的感觉”。AVID品牌永远是生动的、有活力的品牌，是充满生命力的活泼向导的品牌，雅妃德使用天然的材料而研发的具有差异化的机能性化妆品，可赋予肌肤纯净而健康的肤质。",
                "wordTranslation": "AVID",
                "descriptionTranslation": "It means to give you fresh feeling whenever it comes to you. AVID brand is always a lively and dynamic brand, and a brand full of vitality and lively guide. The functional cosmetics developed by AVID using natural materials can give skin pure and healthy skin.",
                "frequency": 888,
                "isShow": 1,
                "version": 1,
                "nlpDicCategories": {
                    "id": 1,
                    "title": "品牌"
                }
            }
        ]
      }
    
### 删除 [DELETE] /nlpUserDic/{id}

+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Response 204    
## 词典分类管理
+ Data
    + id (Long) - ID
    + title (String) - 分类名称
    + enabled (int) - 0禁用 1启用
    + creator (Long) - 创建人
    + modifier (Long) - 修改人
    + created (date) - 创建时间
    + modified (date) - 修改时间

### 增加 [POST] /nlpDicCategories
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
    
+ Request (application/json) 

      {
    	  "data":{
    		"title":"品牌"
    	  } 
      }

Response (application/json)

    {
        "data": {
            "id": 1,
            "type": "nlpDicCategories"
        }
    }

### 修改 [PATCH] /nlpDicCategories/{id}

+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN

+ Request (application/json)
    
      {
        	"data":{
        		"title":"音乐类..."
        	}
      } 

+ Response 200

### 列表[GET] /nlpDicCategories
+ Parameters
  + id 
  + title
     + 查询示例：filter[title]=%25品牌%25 （'%25'为'%'的转义） 
  + sort -modified(从新到旧) | modified(从旧到新)
+ Request (application/json)
       
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
            "self": "/nlpDicCategories?page[number]=1&page[size]=10",
            "first": "/nlpDicCategories?page[number]=1&page[size]=10",
            "last": "/nlpDicCategories?page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:31:04",
                "modified": "2018-11-27 16:31:04",
                "title": "品牌"
            },
            {
                "id": 2,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:31:35",
                "modified": "2018-11-27 16:31:35",
                "title": "厂家"
            },
            {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:31:43",
                "modified": "2018-11-27 16:31:43",
                "title": "经销商"
            },
            {
                "id": 4,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:31:55",
                "modified": "2018-11-27 16:31:55",
                "title": "设备名"
            },
            {
                "id": 5,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:32:02",
                "modified": "2018-11-27 16:32:02",
                "title": "音频物理量"
            },
            {
                "id": 6,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-11-27 16:32:09",
                "modified": "2018-11-27 16:32:09",
                "title": "人名"
            }
        ]
      }
       

### 删除 [DELETE] /nlpDicCategories/{id}

+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Response 204  
### 获取重复的文章 [GET] /topics/{id}/repeats?page[number]=1&page[size]=3&sort=-created

+ Description
    + 当点击这篇文章查看详情时，首先应该判断字段'wx'，当wx=null或者wx=0时，文章的id直接取字段'id'，当wx=1时，文章id应取字段'articleTopicId'，如果articleTopicId=null或者articleTopicId=0则说明这篇文章在数据库中没有保存内容，因此只能去取外部连接from.origin进行跳转。
    
+ Response 200 (application/json)

        {
          "meta": {
            "totalPages": 15,
            "totalElements": 43,
            "size": 3,
            "number": 1,
            "numberOfElements": 3,
            "first": true,
            "last": false,
            "sort": null
          },
          "links": {
            "self": "/topics/search?sort=-created&page[number]=1&page[size]=3",
            "first": "/topics/search?sort=-created&page[number]=1&page[size]=3",
            "next": "/topics/search?sort=-created&page[number]=2&page[size]=3",
            "last": "/topics/search?sort=-created&page[number]=15&page[size]=3"
          },
          "data": [
            {
              "id": "wx59585",
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
              "created": "2018-09-12 20:35:47",
              "modified": "2018-11-08 12:17:23",
              "wx": 1,
              "wxTopicId": 59585,
              "articleTopicId": 1391980,
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
                "image": "//static.mifanxing.com/iyyren/image/201808/23/1510/376109814771761152.jpg",
                "fetchReviews": 1921,
                "reviews": 1921,
                "wxSeedId": 180,
                "seedId": 331,
                "origin": "http://mp.weixin.qq.com/s?__biz=MzA4OTE2NDEwOQ==&mid=2649669314&idx=1&sn=b24233f5c9e9296f2be0c78345c01925&chksm=88050ee0bf7287f6b78961f66292e300263b17ea5c6e3124a29490d5eb2ae9a7ba0f3588254e&scene=27#wechat_redirect&seedId=180&groupSign=1536737351654&top=1&original=100",
                "host": "null://null",
                "rating": null,
                "source": "架子鼓",
                "fetchThumbsUp": 4,
                "channelId": 324
              },
              "wxCategoryId": 24,
              "post": {
                "postType": 1,
                "postTypeValue": "爬取",
                "title": "【架子鼓学习】每个学习架子鼓的人都应该知道的事",
                "description": ".有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，...",
                "tags": [
                  "孩子",
                  "家长",
                  "爵士鼓",
                  "架子鼓",
                  "学习",
                  "过程",
                  "老师",
                  "需要",
                  "乐器",
                  "小朋友"
                ]
              },
              "document": {
                "postDate": "2018-09-12",
                "author": "架子鼓",
                "documentType": 0,
                "original": 0
              },
              "similarities": []
            },
            {
              "id": "wx54529",
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
              "created": "2018-09-01 06:55:48",
              "modified": "2018-11-08 12:08:29",
              "wx": 1,
              "wxTopicId": 54529,
              "articleTopicId": 1374017,
              "reviews": 0,
              "replies": 0,
              "thumbsUp": 0,
              "thumbsDown": 0,
              "thumbs": 0,
              "liked": 0,
              "favorite": 0,
              "brand": null,
              "rotations": null,
              "images": [
                {
                  "filename": "//static.mifanxing.com/wx/image/183/6/440238.jpg"
                },
                {
                  "filename": "//static.mifanxing.com/wx/image/183/6/440239.jpg"
                },
                {
                  "filename": "//static.mifanxing.com/wx/image/183/6/440240.jpg"
                },
                {
                  "filename": "//static.mifanxing.com/wx/image/183/6/440241.jpg"
                }
              ],
              "coverImages": null,
              "from": {
                "image": "//static.mifanxing.com/iyyren/image/201808/23/1510/376109814771761152.jpg",
                "fetchReviews": 1472,
                "reviews": 1472,
                "wxSeedId": 180,
                "seedId": 331,
                "origin": "http://mp.weixin.qq.com/s?__biz=MzA4OTE2NDEwOQ==&mid=2649669266&idx=1&sn=fe3771c74ca2b46cec9007cd210a6b05&chksm=88050eb0bf7287a69bf37111453cbffcc5cd3c6ebf2d24be2ea8a3e2cdaf337a7ab22a874e65&scene=27#wechat_redirect&seedId=180&groupSign=1535783935636&top=1&original=100",
                "host": "null://null",
                "rating": null,
                "source": "架子鼓",
                "fetchThumbsUp": 3,
                "channelId": 324
              },
              "wxCategoryId": 24,
              "post": {
                "postType": 1,
                "postTypeValue": "爬取",
                "title": "孩子学爵士鼓，家长要了解这些～",
                "description": ".有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，...",
                "tags": [
                  "孩子",
                  "家长",
                  "爵士鼓",
                  "学习",
                  "老师",
                  "小朋友",
                  "架子鼓",
                  "练习",
                  "耳朵",
                  "增强"
                ]
              },
              "document": {
                "postDate": "2018-09-01",
                "author": "架子鼓",
                "documentType": 0,
                "original": 0
              },
              "similarities": []
            },
            {
              "id": "wx67308",
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
              "created": "2018-07-18 12:49:57",
              "modified": "2018-11-08 12:27:13",
              "wx": 1,
              "wxTopicId": 67308,
              "articleTopicId": 1404964,
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
                "image": "//static.mifanxing.com/iyyren/image/201808/23/1510/376109814771761152.jpg",
                "fetchReviews": 3154,
                "reviews": 3154,
                "wxSeedId": 180,
                "seedId": 331,
                "origin": "http://mp.weixin.qq.com/s?__biz=MzA4OTE2NDEwOQ==&amp;mid=2649669014&amp;idx=1&amp;sn=5c52b5b7e437ae647dd98b503d6ac633&amp;chksm=88050db4bf7284a2ed775e168b7b5ce29caab2bc728a39e35678f189a360e53492bb14f82b6e&amp;scene=27#wechat_redirect&seedId=180&groupSign=1537120010615&top=1&original=100",
                "host": "null://null",
                "rating": null,
                "source": "架子鼓",
                "fetchThumbsUp": 11,
                "channelId": 324
              },
              "wxCategoryId": 24,
              "post": {
                "postType": 1,
                "postTypeValue": "爬取",
                "title": "相当全的爵士鼓知识，值得收藏！",
                "description": ".有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，最后成了对不起 有多少句对不起，最后都是没关系 有多少句没关系，最后说了谢谢你有多少句我爱你，...",
                "tags": [
                  "孩子",
                  "家长",
                  "爵士鼓",
                  "学习",
                  "架子鼓",
                  "乐器",
                  "过程",
                  "老师",
                  "小朋友",
                  "节奏"
                ]
              },
              "document": {
                "postDate": "2018-07-18",
                "author": "架子鼓",
                "documentType": 0,
                "original": 0
              },
              "similarities": []
            }
          ]
        }

## 弃用分类管理
+ Data
    + id (Long) - ID
    + title (String) - 分类名称
    + enabled (int) - 0禁用 1启用
    + creator (Long) - 创建人
    + modifier (Long) - 修改人
    + created (date) - 创建时间
    + modified (date) - 修改时间

### 增加 [POST] /abandonCategories
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
    
+ Request (application/json) 

      {
    	  "data":{
    		"title":"广告类"
    	  } 
      }

Response (application/json)

    {
        "data": {
            "id": 1,
            "type": "abandonCategories"
        }
    }

### 修改 [PATCH] /abandonCategories/{id}

+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN

+ Request (application/json)
    
      {
        	"data":{
        		"title":"其它xx类"
        	}
      } 

+ Response 200

### 列表[GET] /abandonCategories

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
            "self": "/abandonCategories?page[number]=1&page[size]=10",
            "first": "/abandonCategories?page[number]=1&page[size]=10",
            "last": "/abandonCategories?page[number]=1&page[size]=10"
        },
        "data": [
            {
                "id": 1,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-09-11 10:02:03",
                "modified": "2018-09-11 10:02:03",
                "title": "广告类"
            },
            {
                "id": 2,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-09-11 10:02:27",
                "modified": "2018-09-11 10:02:27",
                "title": "生活类"
            },
            {
                "id": 3,
                "enabled": 1,
                "creator": 0,
                "modifier": 0,
                "created": "2018-09-11 10:02:33",
                "modified": "2018-09-11 11:49:45",
                "title": "其它xx类"
            }
        ]
      }

### 删除 [DELETE] /abandonCategories/{id}

+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Response 204



## 榜单文章快速移除

### 删除 [POST] /topicsAbandon
+ Description
    + [MUST] authenticated
    + [MUST] ROLE_ADMIN
+ Parameters
+ Request (application/json)
     
        {
    	  "data":{
    		 "topicId":"997315",
    		 "categoryId":"2"
    	}
}
+ Response  (application/json)

        {
          "data": {
              "id": 17,
              "type": "topicsAbandon"
            }
        }
