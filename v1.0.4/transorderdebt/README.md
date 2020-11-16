transorderdebt
----------
**交易/订单/债务接口说明**

**简介**：交易/订单/债务接口说明

**HOST**: 

**联系人**:

**Version**:1.0


# **交易/订单/债务接口说明**
实现对转账交易、订单和债务关系的增加、删除和修改

#Actions:

**转账交易表**：

| 参数名称  | 类型    | 是否必填描述 | 描述     |
| --------- | ------- | ------------ | -------- |
| pkey  | uint64 | 自动创建           | 主索引，递增 |
| trans_id  | checksum256 | 是           | 二级索引，根据交易id号索引 |
| from | name | 是           | 转账的发起者   |
| to | name | 是           | 转账的接收者   |
| quantity | asset | 是           | 数量   |
| memo | string | 是           |  自定义字符串  |
| fee | asset | 是           | 费用   |
| timestamp | string | 是          | 时间戳   |

## transorderdebt::transupsert   转账信息的记录（增加或更新）
   - **trans_id**  交易id
   - **from**      转账发起者
   - **to**        转账接收者
   - **quantity**  数量
   - **memo**      自定义字符串
   - **fee**       费用   
   - **timestamp**  时间戳

## transorderdebt::transerase    转账信息的删除（根据交易id号删除）
   - **trans_id**

**订单表**：

| 参数名称  | 类型    | 是否必填描述 | 描述     |
| --------- | ------- | ------------ | -------- |
| pkey  | uint64 | 自动创建           | 主索引，递增 |
| order_id  | uint128 | 是           | 二级索引，根据订单id索引 |
| account | name | 是           | 用户账户   |
| logistics | string | 是           | 物流信息   |
| goods_info | string | 是           | 商品信息   |
| merchant | name | 是           | 商户账户   |
| timestamp | string | 是          | 时间戳   |

## transorderdebt::orderupsert   订单信息的记录（增加或更新）
   - **order_id**   订单号
   - **account**    用户账户
   - **logistics**  物流信息
   - **goods_info** 商品信息
   - **merchant**   商户账户
   - **timestamp**  时间戳

## transorderdebt::ordererase    转账信息的删除（根据交易id号删除）
   - **order_id**  订单id


**债务关系表**：

| 参数名称  | 类型    | 是否必填描述 | 描述     |
| --------- | ------- | ------------ | -------- |
| pkey  | uint64 | 自动创建           | 主索引，递增 |
| debt_id  | uint128 | 是           | 二级索引，根据债务id索引 |
| debtor | name | 是           | 债务方   |
| quantity | asset | 是           | 数量   |
| profile | map<string string> | 是           | 债务信息   |
| timestamp | string | 是          | 时间戳   |

## transorderdebt::debtupsert
   - **debt_id**   债务id
   - **debtor**    债务方
   - **quantity**  数量
   - **profile**   债务信息  
   - **timestamp**  时间戳
 
## transorderdebt::debterase    债务信息的删除（根据债务id号删除）
   - **debt_id**   债务id
   
## transorderdebt::ordererase    转账信息的删除（根据交易id号删除）
   - **order_id**  订单id


**解债关系表**：

| 参数名称  | 类型    | 是否必填描述 | 描述     |
| --------- | ------- | ------------ | -------- |
| pkey  | uint64 | 自动创建           | 主索引，递增 |
| dis_creditor  | checksum256 | 是           | 二级索引，根据债务id和债权方确定 |
| discharge_id  | uint128 | 是           | 债务id|
| debtor | name | 是           | 债务方   |
| creditor | name | 是           | 债权方   |
| quantity | asset | 是           | 数量   |
| profile | map<string string> | 是           | 债务信息   |
| timestamp | string | 是          | 时间戳   |

## transorderdebt::debtdisup
   - **discharge_id**   债务id
   - **debtor**    债务方
   - **creditor**    债权方
   - **quantity**  数量
   - **profile**   债务信息  
   - **timestamp**  时间戳
   
## transorderdebt::debtdiserase    债务信息的删除（根据债务id号和债权人删除）
   - **discharge_id**   债务id
   - **creditor**   债权方
   

  
