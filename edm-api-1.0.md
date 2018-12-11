+ 2018年12月10日
     + API初始化
     
## 邮件管理-邮箱账户
+ Data
    + id (Long) - ID
    + email (String) - email账户
    + lastName (String) - 姓氏
    + name (String)     - 名字
    + positionalTitles (String) - 职称
    + emailCompany (String) - 客户邮箱属于公司
    + mifanId (Long) - 米饭星id,默认为0
    + priority  (int) - 优先级
    + companyId  (Long) - 公司id
    + accountSource  (int) - 账号来源，(0-注册用户，1-展会用户，2-网络邮箱，3-合作伙伴)
    + retry  (int) - 重试次数
    + sendCount  (int) - 是否发送 （0-未发，1-已发）
    + disableReason (String) --禁用原因
    + enabled (int) - 是否可用
    + creator (Long)  - 创建人
    + modifier (Long) - 修改人
    + created (Date) - 创建时间
    + modified (Date) - 修改时间    

### 增加 [POST] /email
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + email (String) - email账户 必填
    + lastName (String) - 姓氏
    + name (String)     - 名字
    + positionalTitles (String) - 职称
    + emailCompany (String) - 客户邮箱属于公司
    + priority  (int) - 优先级
    + companyId  (Long) - 公司id
    + accountSource  (int) - 账号来源，(0-注册用户，1-展会用户，2-网络邮箱，3-合作伙伴)

+ Request (application/json)

       {
	    "data":{
		"email":"1112525524@qq.com",
		"companyId":"1",
		"accountSource":"1",
		"lastName":"刘",
		"name":"凯",
		"positionalTitles":"职称",
		"emailCompany":"宝迪"
	}
}
+ Response 200 


### 修改 [PATCH] /email/{id} 

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)
+ 
        {
	    "data":{
		"email":"1112525524@qq.com",
		"companyId":"1",
		"accountSource":"1",
		"lastName":"刘",
		"name":"凯1",
		"positionalTitles":"职称1",
		"emailCompany":"宝迪"
	}
}

+ Response 200  (application/json)


### 查询公司详情 [GET] /email/{id}
+ Parameters
    + id 
    
+ Request (application/json)
       
        {
        "data": {
        "id": 1,
        "enabled": 1,
        "creator": 0,
        "modifier": 0,
        "created": "2018-11-12 18:05:07",
        "modified": "2018-12-05 14:03:37",
        "email": "yangchangli0010@gmail.com",
        "sendCount": 1,
        "retry": 0,
        "lastName": "杨",
        "name": "昌立",
        "positionalTitles": "工程师",
        "emailCompany": "A公司",
        "mifanId": 0,
        "priority": 1,
        "companyId": 1,
        "accountSource": 0,
        "companyName": "mm"
    }
}

+ Response 200

### 查询邮件账户列表 [GET]  /company
    
+ Response 200 (application/json)

        {
        "meta": {
        "totalPages": 45,
        "totalElements": 447,
        "size": 10,
        "number": 1,
        "numberOfElements": 10,
        "first": true,
        "last": false,
        "sort": null
        },
        "links": {
        "self": "/email?page[number]=1&page[size]=10",
        "first": "/email?page[number]=1&page[size]=10",
        "next": "/email?page[number]=2&page[size]=10",
        "last": "/email?page[number]=45&page[size]=10"
        },
        "data": [
        {
            "id": 1,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-11-12 18:05:07",
            "modified": "2018-12-05 14:03:37",
            "email": "yangchangli0010@gmail.com",
            "sendCount": 1,
            "retry": 0,
            "lastName": "杨",
            "name": "昌立",
            "positionalTitles": "工程师",
            "emailCompany": "A公司",
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 2,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 14:23:32",
            "modified": "2018-12-05 14:03:36",
            "email": "yangchangli@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 3,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-11-13 11:41:07",
            "modified": "2018-11-28 15:58:46",
            "email": "ycl0010@sina.com",
            "sendCount": 0,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 4,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-18 16:18:43",
            "modified": "2018-12-05 14:03:36",
            "email": "1223944885@qq.com",
            "sendCount": 1,
            "retry": 0,
            "disableReason": "",
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 5,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-22 14:17:00",
            "modified": "2018-12-05 14:03:36",
            "email": "17085145710@163.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 6,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-22 14:31:00",
            "modified": "2018-12-05 14:03:41",
            "email": "yangchangli1223944885@hotmail.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 8,
            "enabled": 0,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-22 16:11:25",
            "modified": "2018-11-23 15:37:26",
            "email": "kai.liu007@qq.com",
            "sendCount": 0,
            "retry": 0,
            "disableReason": "",
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 9,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:56:18",
            "modified": "2018-12-05 14:03:47",
            "email": "zhangyongwei@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 10,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:56:59",
            "modified": "2018-12-05 14:03:52",
            "email": "cuiyan@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        },
        {
            "id": 12,
            "enabled": 1,
            "creator": 0,
            "modifier": 0,
            "created": "2018-10-23 13:58:42",
            "modified": "2018-12-05 14:03:57",
            "email": "guoliangwei@mifanxing.com",
            "sendCount": 1,
            "retry": 0,
            "mifanId": 0,
            "priority": 1,
            "companyId": 1,
            "accountSource": 0,
            "companyName": "mm"
        }
    ]
}



### 删除 [DELETE] /email/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 200





+ 2018年12月10日
     + API初始化
     
## 邮件管理 -公司
+ Data
    + id (Long) - ID
    + companyName (String) - 公司名字
    + companyDesc (String) - 公司描述
    + enabled (int) - 是否可用
    + created (Date) - 创建时间
    + modified (Date) - 修改时间    

### 增加 [POST] /company
+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)

    {
	    "data":{
		    "companyName":"MIDIFAN",
		    "companyDesc":"一个关于音频设备的网站"
	    }
    }
+ Response 200 

### 修改 [PATCH] /company/{id} 

+ Description
  + [MUST] authenticated
  + [MUST] ROLE_ADMIN

+ Parameters
    + companyName 必填  
    + companyDesc 

+ Request (application/json)
+ 

         {
        "data" : {
              "id":8,
    		  "companyName" : "MIDIFAN11",
    		  "companyDesc" : "一个关于音频设备的网站"
    	  }
    }

+ Response 200 


### 查询公司详情 [GET] /company/{id}
+ Parameters
    + id 
    
+ Request (application/json)
       
         {
        "data": {
        "id": 11,
        "enabled": 1,
        "created": "2018-12-11 14:59:07",
        "modified": "2018-12-11 15:23:27",
        "companyName": "mm",
        "companyDesc": "一个关于音频设备的网站",
    }
}

+ Response 200

### 查询公司列表 [GET]  /company
    
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
        "self": "/company?page[number]=1&page[size]=10",
        "first": "/company?page[number]=1&page[size]=10",
        "last": "/company?page[number]=1&page[size]=10"
        },
        "data": [
        {
            "id": 2,
            "enabled": 1,
            "created": "2018-11-27 10:40:56",
            "modified": "2018-11-27 10:40:59",
            "companyName": "太平宝迪"
        },
        {
            "id": 11,
            "enabled": 1,
            "created": "2018-12-11 14:59:07",
            "modified": "2018-12-11 15:23:27",
            "companyName": "mm",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 14,
            "enabled": 1,
            "created": "2018-12-11 14:59:27",
            "modified": "2018-12-11 14:59:27",
            "companyName": "MI33DIFAN33111",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 17,
            "enabled": 1,
            "created": "2018-12-11 15:03:02",
            "modified": "2018-12-11 15:03:02",
            "companyName": "dfdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 18,
            "enabled": 1,
            "created": "2018-12-11 15:04:52",
            "modified": "2018-12-11 15:04:52",
            "companyName": "1dfdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 19,
            "enabled": 1,
            "created": "2018-12-11 15:07:40",
            "modified": "2018-12-11 15:07:40",
            "companyName": "1d23fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 20,
            "enabled": 1,
            "created": "2018-12-11 15:11:19",
            "modified": "2018-12-11 15:11:19",
            "companyName": "133d23fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 23,
            "enabled": 1,
            "created": "2018-12-11 15:16:33",
            "modified": "2018-12-11 15:16:33",
            "companyName": "333133d2333223fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        },
        {
            "id": 25,
            "enabled": 1,
            "created": "2018-12-11 15:20:04",
            "modified": "2018-12-11 15:20:04",
            "companyName": "A333133d23222233223fdfdf",
            "companyDesc": "一个关于音频设备的网站"
        }
    ]
}



### 删除 [DELETE] /company/{id}
+ Description
  + [MUST]  Authenticated
  + [MUST] ROLE_ADMIN 
+  Response 200


