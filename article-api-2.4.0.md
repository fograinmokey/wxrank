+ 2018年9月11日
    + 弃用分类管理初始化
    + 榜单文章快速移除

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
