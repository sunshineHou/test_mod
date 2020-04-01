## todolist项目接口文档


### 项目组新增
```
  @api {post} /todolist/v1/team/add.json	项目组新增
  @apiPermission template-manage
  @apiParam {String} access_id 				子账号ID
  @apiParam {String} algorithm="sha256"    	签名算法
  @apiParam {String} secret_type="forever" 	签名密钥类型
  @apiParam {String} sign					签名内容
  @apiParam {String} project_team			项目组
  @apiParam {int}    cloud_id				服务器编号
  @apiSuccessExample Success-Response:
  HTTP/1.1 200 OK
	{
		"code": 0,
		"result": "success",
		"error": "",
		"trace": {
			"Trace": "ab5fda4f632b7c15",
			"Span": "3c9033b3d62c4564"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 103,
		"result": {},
		"error": "cloud_id已被占用 ",
		"trace": {
			"Trace": "fa329b71eb72b5a6",
			"Span": "4f9cc3b529e461b7"
		}
	}
```
### 项目组查询
```
  @api {post} /todolist/v1/team/query.json	项目组查询
  @apiPermission template-manage
  @apiParam {String} access_id 				子账号ID
  @apiParam {String} algorithm="sha256"    	签名算法
  @apiParam {String} secret_type="forever" 	签名密钥类型
  @apiParam {String} sign					签名内容
  @apiParam {String} project_team(可选)		项目组
  @apiParam {int}    cloud_id(可选)			服务器编号
  @apiParam {int} 	 limit(可选)				显示的数量
  @apiParam {int} 	 skip(可选)				跳过的数量
  @apiSuccessExample Success-Response:
  HTTP/1.1 200 OK
	{
		"code": 0,
		"result": [
			{
				"ProjectTeam": "大棋牌",
				"CloudId": 1
			},
			{
				"ProjectTeam": "捕鱼",
				"CloudId": 3
			}
		],
		"error": "",
		"trace": {
			"Trace": "d5d6b9151350cfbc",
			"Span": "a36e2991ff199c1e"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
```

### 任务新增
```
  @api {post} /todolist/v1/task/add.json	任务新增
  @apiPermission template-manage
  @apiParam {String} access_id 				子账号ID
  @apiParam {String} algorithm="sha256"    	签名算法
  @apiParam {String} secret_type="forever" 	签名密钥类型
  @apiParam {String} sign					签名内容
  @apiParam {String} project_team			项目组
  @apiParam {String} task_theme				任务主题
  @apiParam {String} task_manager			任务负责人
  @apiParam {String} jira_url				jira链接
  @apiParam {int} 	 cloud_id
  @apiParam {int} 	 app_id
  @apiParam {int} 	 game_id
  @apiParam {String} client_id				应用Id
  @apiParam {String} template_name			模板名称
  @apiParam {String} task_details			任务详情		# eg：{"上线配置检查":[{"mode为1":true},{"egg版本":true}],"支付限额检查":[{"配置信息同步项目组":true}]}
  @apiParam {String} note					备注
  @apiParam {String} modified_by			修改人
  @apiSuccessExample Success-Response:
  HTTP/1.1 200 OK
	{
		"code": 0,
		"result": "success",
		"error": "",
		"trace": {
			"Trace": "ab5fda4f632b7c15",
			"Span": "3c9033b3d62c4564"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
```
 
### 任务更新
```
  @api {post} /todolist/v1/task/change.json	任务更新
  @apiPermission template-manage
  @apiParam {String} access_id 				子账号ID
  @apiParam {String} algorithm="sha256"    	签名算法
  @apiParam {String} secret_type="forever" 	签名密钥类型
  @apiParam {String} sign					签名内容
  @apiParam {String} project_team			项目组
  @apiParam {String} task_theme				任务主题
  @apiParam {String} task_manager			任务负责人
  @apiParam {String} jira_url				jira链接
  @apiParam {int} 	 cloud_id
  @apiParam {int} 	 app_id
  @apiParam {int} 	 game_id
  @apiParam {String} client_id				应用Id
  @apiParam {String} template_name			模板名称
  @apiParam {String} task_details			任务详情		# eg：{"上线配置检查":[{"mode为1":true},{"egg版本":true}],"支付限额检查":[{"配置信息同步项目组":true}]}
  @apiParam {String} note(可选)				备注
  @apiParam {int} 	 task_number			任务编号
  @apiParam {String} task_status			任务状态
  @apiParam {String} modified_by			修改人
  @apiSuccessExample Success-Response:
  HTTP/1.1 200 OK
	{
		"code": 0,
		"result": "success",
		"error": "",
		"trace": {
			"Trace": "ab5fda4f632b7c15",
			"Span": "3c9033b3d62c4564"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 416,
		"result": {},
		"error": "request modified_by is missing ",
		"trace": {
			"Trace": "3f4011722047219e",
			"Span": "be2a9aa9c68c441a"
		}
	}
```
 
### 任务查询
```
  	@api {post} /todolist/v1/task/query.json	任务查询
	@apiPermission template-manage
	@apiParam {String} access_id 					子账号ID
	@apiParam {String} algorithm="sha256"    		签名算法
	@apiParam {String} secret_type="forever" 		签名密钥类型
	@apiParam {String} sign							签名内容
	@apiParam {int}    limit(可选)					显示的数量
	@apiParam {int}    skip(可选)					跳过的数量
	@apiParam {int}    task_number(可选)				任务编号
	@apiParam {String} task_theme(可选)				任务主题
	@apiParam {String} project_team(可选)			项目组
	@apiParam {String} create_time(可选)				创建时间
  	@apiSuccessExample Success-Response:
  	HTTP/1.1 200 OK
	{
		"code": 0,
		"result": [
			{
				"TaskNumber": 6,
				"ProjectTeam": "捕鱼",
				"TaskTheme": "捕鱼上线检查",
				"TaskManager": "王新宇",
				"JiraUrl": "https://org.modao.cc/app/cd611e581b62c2255de04760325ba31be5602438?simulator_type=device&sticky#screen=sk7u70f6njnpmxm",
				"CloudId": 3,
				"AppId": 10063,
				"GameId": 100631,
				"CreateTime": "2020-03-31 18:17:26",
				"ClientId": "Android_3.8_tyGuest,tyAccount.alipay.0-hall28.official.bydzz.json",
				"TemplateName": "捕鱼上线流程list",
				"TaskStatus": "开发中",
				"TaskDetails": {
					"上线配置检查": [
						{
							"mode为1": true
						},
						{
							"egg版本": true
						}
					],
					"支付限额检查": [
						{
							"配置信息同步项目组": true
						}
					]
				},
				"Note": ""
			}
		],
		"error": "",
		"trace": {
			"Trace": "da12dcad20d225cf",
			"Span": "0ee0c81adffb6268"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
```

### 任务更新记录查询

```
  	@api {post} /todolist/v1/task/note/query.json	任务更新记录查询
	@apiPermission template-manage
	@apiParam {String} access_id 					子账号ID
	@apiParam {String} algorithm="sha256"    		签名算法
	@apiParam {String} secret_type="forever" 		签名密钥类型
	@apiParam {String} sign							签名内容
	@apiParam {int} limit(可选)						显示的数量
	@apiParam {int} skip(可选)						跳过的数量
	@apiParam {int} task_number(可选)				任务编号
	@apiParam {String} task_theme(可选)				任务主题
	@apiParam {String} project_team(可选)			项目组
	@apiParam {String} create_time(可选)				创建时间
  	@apiSuccessExample Success-Response:
  	HTTP/1.1 200 OK
	{
		"code": 0,
		"result": [
			{
				"TaskNumber": 1,
				"ProjectTeam": "捕鱼",
				"TaskTheme": "捕鱼上线检查",
				"TaskManager": "王新宇",
				"JiraUrl": "https://org.modao.cc/app/cd611e581b62c2255de04760325ba31be5602438?simulator_type=device&sticky#screen=sk7u70f6njnpmxm",
				"CloudId": 3,
				"AppId": 10063,
				"GameId": 100631,
				"CreateTime": "2020-04-01 17:45:03",
				"ClientId": "Android_3.8_tyGuest,tyAccount.alipay.0-hall28.official.bydzz.json",
				"TemplateName": "捕鱼上线流程list",
				"TaskStatus": "开发中",
				"TaskDetails": {
					"上线配置检查": [
						{
							"mode为1": true
						},
						{
							"egg版本": true
						}
					],
					"支付限额检查": [
						{
							"配置信息同步项目组": true
						}
					]
				},
				"Note": "",					# 备注
				"ModifiedBy": ""			# 修改人
			}
		],
		"error": "",
		"trace": {
			"Trace": "0d4b109501d4a1f3",
			"Span": "d51d04b5c1c763b9"
		}
	}
  @apiErrorExample {json} Error-Response:
  HTTP/1.1 200 OK
	{
		"code": 511,
		"result": {},
		"error": "signature check failed 4005 ",
		"trace": {
			"Trace": "68dbcdc57bb12ed0",
			"Span": "531368f80167ec70"
		}
	}
```

### 模板新增

```
	@api {post} /todolist/v1/template/add.json	模板新增
	@apiPermission template-manage
	@apiParam {String} access_id 			子账号ID
	@apiParam {String} algorithm="sha256"    签名算法
	@apiParam {String} secret_type="forever" 签名密钥类型
	@apiParam {String} sign					签名内容
	@apiParam {String} template_name			模板名称
	@apiParam {String} task_list				任务清单		# eg：{"上线配置检查":["mode为1","egg版本"],"支付限额检查":["配置信息同步项目组"]}
	@apiSuccessExample Success-Response:
	HTTP/1.1 200 OK
	{
	"code": 0,
	"result": "success",
	"error": "",
	"trace": {
	"Trace": "67d3d290788cb2db",
	"Span": "f3507ed858c8be94"
	}
	}
	@apiErrorExample {json} Error-Response:
	HTTP/1.1 200 OK
	{
	"code":201
	"error": "UserNotFound"
	}
```
 
### 模板查询
 
```
	@api {post} /todolist/v1/template/query.json	模板查询
	@apiPermission template-manage
	@apiParam {String} access_id 					子账号ID
	@apiParam {String} algorithm="sha256"    		签名算法
	@apiParam {String} secret_type="forever" 		签名密钥类型
	@apiParam {String} sign							签名内容
	@apiParam {int} limit(可选)						显示的数量
	@apiParam {int} skip(可选)						跳过的数量
	@apiParam {String} template_name(可选)			模板名称
	@apiParam {String} template_number(可选)			任务编号
	@apiSuccessExample Success-Response:
        HTTP/1.1 200 OK
		{
			"code": 0,
			"result": [
				{
					"TemplateNumber": "ty_nhE30g3X2z",
					"TemplateName": "上线流程list",
					"TaskList": {
						"上线配置检查": [
							"mode为1",
							"egg版本"
						],
						"支付限额检查": [
							"配置信息同步项目组"
						]
					}
				},
				{
					"TemplateNumber": "ty_o3YtLbMeU5",
					"TemplateName": "捕鱼上线流程list",
					"TaskList": {
						"上线配置检查": [
							"mode为1",
							"egg版本"
						],
						"支付限额检查": [
							"配置信息同步项目组"
						]
					}
				}
			],
			"error": "",
			"trace": {
				"Trace": "8c066365ac2f9563",
				"Span": "095004b91100f242"
			}
		}
	@apiErrorExample {json} Error-Response:
		HTTP/1.1 200 OK
		{
			"code": 511,
			"result": {},
			"error": "signature check failed 4005 ",
			"trace": {
				"Trace": "9b62ee57a905804d",
				"Span": "64b2d00881fae62a"
			}
		}
```