# RestaurantWechatApp DatabaseDesign

#### 1.用户

表名称：user | 表类型：约束表 | 含义：用户表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 用户ID | user_id | String |  |  | False |  | "user/12345" |
| 用户名 | username | String |  |  | True |  |  |
| 用户类别 | user_type_fid | String |  |  | False |  | "userType/12345" |
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
| 管理员类别 | admin_type_fid | String |  |  | False |  | "adminType/12345" |
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

#### 6.权限

表名称：right | 表类型：约束表 | 含义：权限表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 权限ID | right_id | String |  |  | False |  | "right/12345" |
| 权限名称 | right_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 7.商户

表名称：merchant | 表类型：约束表 | 含义：商户表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 商户ID | merchant_id | String |  |  | False |  | "merchant/12345" |
| 商户名称 | merchant_name | String |  |  | False |  |  |
| 商户类别 | merchant_type_fid | String |  |  | False |  |  |
| 法人姓名 | legal_person_name | String |  |  | False |  | "张三" |
| 法人身份证 | legal_person_id_card | String |  |  | False |  |  |
| 营业执照社会统一识别号 | business_license_number | String |  |  | False |  |  |
| 营业执照图 | business_license_img | String |  |  | False |  |  |
| 注册时间 | sign_up_date | String |  |  | False |  |  |
| 商品集 | merchandises | array[merchandise_fid] |  |  | True |  |  |
| 商品类别集 | couponTypes | array[coupon_type_fid] |  |  | True |  |  |
| 优惠券集 | coupons | array[coupon_fid] |  |  | True |  |  |
| 优惠券类别集 | couponTypes | array[coupon_type_fid] |  |  | True |  |  |
| 订单集 | orders | array[order_fid] |  |  | True |  |  |
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
| 商品类别 | merchandise_type_fid | String |  |  | False |  |  |
| 商品价格 | merchandise_price | Number |  |  | False |  |  |
| 商品图片集 | merchandise_imgs | array[String] |  |  | False |  |  |
| 商品视频集 | merchandise_videos | array[String] |  |  | False |  |  |
| 商品详情 | merchandise_detail | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 10.商品类别

表名称：merchandiseType | 表类型：约束表 | 含义：商品类别表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | merchandise_type_id | String |  |  | False |  | "merchandiseType/12345" |
| 类型名称 | merchandise_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 11.优惠券

表名称：coupon | 表类型：约束表 | 含义：优惠券表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 优惠券ID | coupon_id | String |  |  | False |  | "coupon/12345" |
| 优惠券名称 | coupon_name | String |  |  | False |  |  |
| 优惠券类别 | coupon_type_fid | String |  |  | False |  | "couponType/12345" |
| 多个使用标志 | several_use_flag | Boolean |  |  | False |  |  |
| 可使用商品集 | merchandises | array[merchandise_fid] |  |  | True |  |  |
| 到期时间 | coupon_expired_date | String |  |  | True |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 12.优惠券类别

表名称：couponType | 表类型：约束表 | 含义：优惠券类别表

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
| 订单类别 | order_type_fid | String |  |  | False |  |  |
| 消费时间 | used_date | String |  |  | False |  |  |
| 商品集 | merchandises | array[merchandise_fid] |  |  | False |  |  |
| 优惠券集 | coupons | array[coupon_fid] |  |  | True |  |  |
| 应付款 | original_money |  |  |  | False |  |  |
| 实收款 | paid_money |  |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |

#### 14.订单类别

表名称：orderType | 表类型：约束表 | 含义：订单类别表

| 字段含义 | 字段名称 | 字段类型 | 长度 | 默认值 | 允许空 | 备注 | 举例 |
| :--: | :----: | :---: | :--: | :----: | :---: | :--: | :----: |
| 类型ID | order_type_id | String |  |  | False |  | "orderType/12345" |
| 类型名称 | order_type_name | String |  |  | False |  |  |
| 删除标志 | delete_flag | Boolean |  |  | True |  |  |
