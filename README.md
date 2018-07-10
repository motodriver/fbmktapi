# Facebook投放自动化需求文档1.0
## 1.项目概述
### 1.0 需求背景
Facebook广告管理平台批量创建、查看数据、修改数据等功能较为繁琐，希望将一部分繁琐的流程自动化

### 1.1 功能
### 1.1.1 批量上传功能
#### 功能背景
在新主题上传，创建广告时，需要做许多重复的操作，其中有很多字段是重复、有规律的，所以需要一个批量创建广告的入口，避免重复操作，提高效率。

#### 创建需求字段
| 创建层级 | 所需字段 | 含义 |字段来源 |
| ---- | ---- | ---- | ---- | 
| 广告系列（Campaign) | name | 广告系列名称 | 关联应用名称+创建目的（运营填写） |
| | objective | 营销目标 | 默认为：应用安装量 |
| | status | 广告系列状态 | 批量上传时为Pause，上传完成应用后Active |
| 广告组（Adset)| AdSet.Field.name | 广告组名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写) |
| | AdSet.Field.campaign_id | 广告系列编号 | 自动连线，创建广告系列时获取 |
| | AdSet.Field.daily_budget | 单日预算 | 运营填写 |
| | AdSet.Field.billing_event | 计费方式 | 默认为：应用安装量 |
| | AdSet.Field.optimization_goal | 优化目标 | 默认为：应用安装量 |
| | AdSet.Field.bid_amount | 出价 | 运营填写 |
| | AdSet.Field.start_time | 开始时间 | 自动取上传当天的日期 |
| | AdSet.Field | 结束时间 | 默认为：长期 |
| | AdSet.Field.targeting:rule | 目标受众中的自定义受众 | 默认为：除了安装关联应用的受众 |
| | AdSet.Field.targeting:genders | 目标受众中的性别 | 运营填写 |
| | AdSet.Field.targeting:countries | 目标受众中的国家 | 运营填写（可多选） |
| | AdSet.Field.targeting:age_min | 目标受众中的年龄（最小年龄） | 运营填写 |
| | AdSet.Field.targeting:age_max | 目标受众中的年龄（最大年龄） | 运营填写 |
| 广告（Ad)| name | 广告名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写)+广告创意（素材）编号 |
| | adset_id | 广告组编号 | 自动连线，创建广告组时获取 | 
| | creative | 广告创意（素材）| 运营上传 |
| 广告创意（Adcreative) | creative | 广告创意（素材）| 运营批量上传，上传后在平台上选取 |

#### 运营需要上传的字段
| 创建层级 | 所需字段 | 含义 |字段来源 |
| ---- | ---- | ---- | ---- | 
| 广告系列（Campaign) | name | 广告系列名称 | 关联应用名称+创建目的（运营填写） |
| 广告组（Adset)| AdSet.Field.name | 广告组名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写) |
| | AdSet.Field.daily_budget | 单日预算 | 运营填写 |
| | AdSet.Field.bid_amount | 出价 | 运营填写 |
| | AdSet.Field.targeting:genders | 目标受众中的性别 | 运营填写 |
| | AdSet.Field.targeting:countries | 目标受众中的国家 | 运营填写（可多选） |
| | AdSet.Field.targeting:age_min | 目标受众中的年龄（最小年龄） | 运营填写 |
| | AdSet.Field.targeting:age_max | 目标受众中的年龄（最大年龄） | 运营填写 |
| 广告（Ad)| name | 广告名称 | 应用名称+创建目的（运营填写）+目标受众（运营填写)+广告创意（素材）编号 |
| | creative | 广告创意（素材）| 运营上传 |

#### 原型图











