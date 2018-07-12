# Facebook投放自动化需求文档1.0
## 1.项目概述
### 1.0 需求背景

### 1.1 功能
### 1.1.1 批量上传功能
#### 功能背景
投放中最为繁琐且重复的部分就是新主题上线时的广告创建，一个新主题的上传，会有数百个类似的广告需要创建、上传素材，而这些广告往往只有一两个字段是需要更改的，所以希望能做一个入口通过API批量创建广告。

#### 创建需求字段
| 创建层级 | 所需字段 | 含义 |字段来源 |
| ---- | ---- | ---- | ---- | 
| 广告系列（Campaign) | name | 广告系列名称 | 关联应用名称+创建目的（运营填写） |
| | objective | 营销目标 | 默认为：应用安装量 |
| | status | 广告系列状态 | 批量上传时为Pause，上传完成应用后Active |
| 广告组（Adset)| AdSet.Field.name | 广告组名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写) |
| | AdSet.Field.campaign_id | 广告系列编号 | 自动连线，创建广告系列时获取 |
| | AdSet.Field.daily_budget | 单日预算 | 运营填写 |
| | AdSet.Field.billing_event | 计费方式 | 默认为：impression |
| | AdSet.Field.optimization_goal | 优化目标 | 默认为：应用安装量 |
| | AdSet.Field.bid_amount | 出价 | 运营填写 |
| | AdSet.Field.start_time | 开始时间 | 自动取上传当天的日期 |
| | AdSet.Field | 结束时间 | 默认为：长期 |
| | AdSet.Field.pacing_type | 加速状态 | 运营填写 |
| | AdSet.Field.targeting:rule | 目标受众中的自定义受众 | 默认为：除了安装关联应用的受众 |
| | AdSet.Field.targeting:genders | 目标受众中的性别 | 运营填写 |
| | AdSet.Field.targeting:countries | 目标受众中的国家 | 运营填写（可多选） |
| | AdSet.Field.targeting:age_min | 目标受众中的年龄（最小年龄） | 运营填写 |
| | AdSet.Field.targeting:age_max | 目标受众中的年龄（最大年龄） | 运营填写 |
| 广告（Ad)| name | 广告名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写)+广告创意（素材）编号 |
| | adset_id | 广告组编号 | 自动连线，创建广告组时获取 | 
| | creative | 广告创意（素材）| 运营上传 |
| 广告创意（Adcreative) | creative | 广告创意（素材）| 运营批量上传后在平台上选取 |
| | creative | 素材 - 标题 | 运营填写 |
| | creative | 素材 - 文本 | 运营填写 |
| | creative | 素材 - 图片 | 运营上传 |
| | creative | 素材 - 视频 | 运营上传 |


#### 运营需要上传的字段
| 创建层级 | 所需字段 | 含义 |字段来源 |
| ---- | ---- | ---- | ---- | 
| 广告系列（Campaign) | name | 广告系列名称 | 关联应用名称+创建目的（运营填写） |
| 广告组（Adset)| AdSet.Field.name | 广告组名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写) |
| | AdSet.Field.daily_budget | 单日预算 | 运营填写 |
| | AdSet.Field.bid_amount | 出价 | 运营填写 |
| | AdSet.Field.pacing_type | 加速状态 | 运营填写 |
| | AdSet.Field.targeting:genders | 目标受众中的性别 | 运营填写 |
| | AdSet.Field.targeting:countries | 目标受众中的国家 | 运营填写（可多选） |
| | AdSet.Field.targeting:age_min | 目标受众中的年龄（最小年龄） | 运营填写 |
| | AdSet.Field.targeting:age_max | 目标受众中的年龄（最大年龄） | 运营填写 |
| 广告（Ad)| name | 广告名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写)+广告创意（素材）编号 |
| 广告创意（Adcreative) | creative | 广告创意（素材）| 运营批量上传后在平台上选取 |
| | creative | 素材 - 标题 | 运营填写 |
| | creative | 素材 - 文本 | 运营填写 |
| | creative | 素材 - 图片 | 运营上传 |
| | creative | 素材 - 视频 | 运营上传 |

#### 审核信息
| 创建层级 | 所需字段 | 含义 |字段来源 |
| ---- | ---- | ---- | ---- | 


#### 原型图

### 1.1.2 数据查看功能
#### 功能背景
1、因为Facebook政策限制，一个账号下的投放应用是有限的，所以创建了很多账号。同一个应用，可能投放的数据分布在各个账号中，查看数据的时候十分不方便，需要有一个统一的数据查看平台。
2、基于之后的投放自动化的需求，需要将数据拉取下来之后根据算法计算评分，然后根据评分做出出价、预算等变动。所以需要一个数据查看平台。










