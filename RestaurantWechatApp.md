# RestaurantWechatApp DatabaseDesign

#### 1.用户

表名称：user | 表类型：约束表 | 含义：用户表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 用户ID | user_id | String |  |  | False |  | "user/12345" |
| 用户名 | username | String |  |  | True |  |  |
| 用户类型 | user_type_fid | String |  |  | False |  | "userType/12345" |
| 密码 | password | String |  |  | True | Hash(sha256) |  |
| 姓名 | name | String |  |  | True |  | "张三" |
| 微信uid | wx_uid | String |  |  | False |  |  |
| 电话号码 | phone_number | String |  |  | True |  |  |
| 邮箱 | email | String |  |  | True |  |  |
| 注册时间 | sign_up_date | String |  |  | False |  |  |
| 角色 | roles | array[role_fid] |  |  | True |  |  |
| 订单集 | orders | array[order_fid] |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 2.用户类型

表名称：userType | 表类型：约束表 | 含义：用户类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | user_type_id | String |  |  | False |  | "userType/12345" |
| 类型名称 | user_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 3.管理员

表名称：admin | 表类型：约束表 | 含义：管理员表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 管理员ID | admin_id | String |  |  | False |  | "admin/12345" |
| 管理员类型 | admin_type_fid | String |  |  | False |  | "adminType/12345" |
| 用户名 | username | String |  |  | False |  |  |
| 密码 | password | String |  |  | False | Hash(sha256) |  |
| 姓名 | name | String |  |  | True |  | "张三" |
| 身份证号码 | id_card | String |  |  | True |  |  |
| 微信uid | wx_uid | String |  |  | True |  |  |
| 电话号码 | phone_number | String |  |  | True |  |  |
| 邮箱 | email | String |  |  | True |  |  |
| 注册时间 | sign_up_date | String |  |  | False |  |  |
| 角色 | roles | array[role_fid] |  |  | True |  |  |
| 商户集 | merchants | array[merchant_fid] |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 4.管理员类型

表名称：adminType | 表类型：约束表 | 含义：管理员类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | admin_type_id | String |  |  | False |  | "adminType/12345" |
| 类型名称 | admin_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 5.角色

表名称：role | 表类型：约束表 | 含义：角色表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 角色ID | role_id | String |  |  | False |  | "role/12345" |
| 权限集 | rights | array[right_fid] |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 6.功能

表名称：function | 表类型：约束表 | 含义：功能表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 功能ID | function_id | String |  |  | False |  | "function/12345" |
| 父功能ID | father_function_fid | String |  |  | False |  | "function/12347" |
| 功能名称 | function_name | String |  |  | False |  |  |
| 功能url | function_url | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 7.商户

表名称：merchant | 表类型：约束表 | 含义：商户表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 商户ID | merchant_id | String |  |  | False |  | "merchant/12345" |
| 商户名称 | merchant_name | String |  |  | False |  |  |
| 商户类型 | merchant_type_fid | String |  |  | False |  |  |
| 法人姓名 | legal_person_name | String |  |  | False |  | "张三" |
| 法人身份证 | legal_person_id_card | String |  |  | False |  |  |
| 营业执照社会统一识别号 | business_license_number | String |  |  | False |  |  |
| 营业执照图 | business_license_img | String |  |  | False |  |  |
| 电话号码 | phone_number | String |  |  | True |  |  |
| 注册时间 | sign_up_date | String |  |  | False |  |  |
| 打烊标志 | snoring_flag | Boolean |  |  | False |  |  |
| 开始营业时间 | open_time | String |  |  | False |  |  |
| 结束营业时间 | close_time | String |  |  | False |  |  |
| 商品集 | merchandises | array[merchandise_fid] |  |  | True |  |  |
| 商品类型集 | couponTypes | array[coupon_type_fid] |  |  | True |  |  |
| 优惠券集 | coupons | array[coupon_fid] |  |  | True |  |  |
| 优惠券类型集 | couponTypes | array[coupon_type_fid] |  |  | True |  |  |
| 订单集 | orders | array[order_fid] |  |  | True |  |  |
| 席位集 | seats | array[seat_fid] |  |  | True |  |  |
| 广告集 | adts | array[ad_fid] |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 8.商户类型

表名称：merchantType | 表类型：约束表 | 含义：商户类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | merchant_type_id | String |  |  | False |  | "merchantType/12345" |
| 类型名称 | merchant_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 9.商品

表名称：merchandise | 表类型：约束表 | 含义：商品表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 商品ID | merchandise_id | String |  |  | False |  | "merchandise/12345" |
| 商品名称 | merchandise_name | String |  |  | False |  |  |
| 商品类型 | merchandise_type_fid | String |  |  | False |  |  |
| 商品销售量 | merchandise_sale_volume | Number |  |  | False |  |  |
| 商品现价 | merchandise_now_price | Number |  |  | False |  |  |
| 商品原价 | merchandise_old_price | Number |  |  | False |  |  |
| 商品类型内顺序号 | merchandise_sequence_number | Number |  |  | False |  |  |
| 包装费用 | package_fee | Number |  |  | False |  |  |
| 商品缩略图 | merchandise_min_img | array[String] |  |  | False |  |  |
| 商品图片集 | merchandise_imgs | array[String] |  |  | False |  |  |
| 商品视频集 | merchandise_videos | array[String] |  |  | False |  |  |
| 商品详情 | merchandise_detail | String |  |  | False |  |  |
| 上架标志 | shelf_flag | Boolean |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 10.商品类型

表名称：merchandiseType | 表类型：约束表 | 含义：商品类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | merchandise_type_id | String |  |  | False |  | "merchandiseType/12345" |
| 类型名称 | merchandise_type_name | String |  |  | False |  |  |
| 类型图标 | merchandise_type_icon | String |  |  | False |  |  |
| 类型顺序号 | merchandise_type_sequence_number | Number |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 11.优惠券

表名称：coupon | 表类型：约束表 | 含义：优惠券表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 优惠券ID | coupon_id | String |  |  | False |  | "coupon/12345" |
| 优惠券名称 | coupon_name | String |  |  | False |  |  |
| 优惠券类型 | coupon_type_fid | String |  |  | False |  | "couponType/12345" |
| 多个使用标志 | several_use_flag | Boolean |  |  | False |  |  |
| 可使用商品集 | merchandises | array[merchandise_fid] |  |  | True |  |  |
| 到期时间 | coupon_expired_date | String |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 12.优惠券类型

表名称：couponType | 表类型：约束表 | 含义：优惠券类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | coupon_type_id | String |  |  | False |  | "商户/12345" |
| 类型名称 | coupon_type_name | String |  |  | False |  |  |
| 优惠券计算公式 | coupon_type_formula | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 13.订单

表名称：order | 表类型：约束表 | 含义：订单表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 订单ID | order_id | String |  |  | False |  | "order/12345" |
| 订单类型 | order_type_fid | String |  |  | False |  |  |
| 订单状态 | order_status_fid | String |  |  | False |  |  |
| 消费时间 | used_date | String |  |  | False |  |  |
| 商品集 | merchandises | array[merchandise_fid] |  |  | False |  |  |
| 优惠券集 | coupons | array[coupon_fid] |  |  | True |  |  |
| 应付款 | original_money |  |  |  | False |  |  |
| 实收款 | paid_money |  |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 13.1.订单状态

表名称：orderStatus | 表类型：约束表 | 含义：订单状态表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 订单状态ID | order_status_id | String |  |  | False |  | "orderStatus/12345" |
| 订单状态名称 | order_status_name | String |  |  | False |  |  |
| 订单状态编码 | order_status_code | String |  |  | False |  | "0(等待支付),1(待接单),2(已过期),3(待收货),4(已完成)" |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 14.订单类型

表名称：orderType | 表类型：约束表 | 含义：订单类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | order_type_id | String |  |  | False |  | "orderType/12345" |
| 类型名称 | order_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 15.席位

表名称：seat | 表类型：约束表 | 含义：席位表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 席位ID | seat_id | String |  |  | False |  | "seat/12345" |
| 席位号码 | seat_number | String |  |  | False |  |  |
| 席位类型 | seat_type_fid | String |  |  | False |  |  |
| 席位人数 | seat_people_num | Number |  |  | False |  |  |
| 席位二维码url | seat_qrcode_url | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 16.席位类型

表名称：seatType | 表类型：约束表 | 含义：席位类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | seat_type_id | String |  |  | False |  | "seatType/12345" |
| 类型名称 | seat_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 17.广告

表名称：ad | 表类型：约束表 | 含义：广告表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 广告ID | ad_id | String |  |  | False |  | "ad/12345" |
| 广告名称 | ad_name | String |  |  | False |  |  |
| 广告类型 | ad_type | String |  |  | False |  |  |
| 广告url | ad_url | String |  |  | False |  |  |
| 图片url | ad_imag_url | String |  |  | False |  |  |
| 视频url | ad_video_url | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 18.广告类型(位置)

表名称：adType | 表类型：约束表 | 含义：广告类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | ad_type_id | String |  |  | False |  | "seatType/12345" |
| 类型名称 | ad_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 17. 图标

表名称：icon | 表类型：约束表 | 含义：图标表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 图标ID | icon_id | String |  |  | False |  | "icon/12345" |
| 图标名称 | icon_name | String |  |  | False |  |  |
| 图标类型 | icon_type | String |  |  | False |  |  |
| 图标url | icon_url | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 18.图标类型

表名称：iconType | 表类型：约束表 | 含义：图标类型表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | icon_type_id | String |  |  | False |  | "iconType/12345" |
| 类型名称 | icon_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 17. 主题

表名称：theme | 表类型：约束表 | 含义：主题表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 主题ID | theme_id | String |  |  | False |  | "icon/12345" |
| 主题名称 | theme_name | String |  |  | False |  |  |
| 主题描述 | theme_desc | String |  |  | False |  |  |
| 主题样式表 | theme_style_sheet | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |