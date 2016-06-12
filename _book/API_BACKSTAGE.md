## 小斑马账单api -> 管理后台md

### 查询订单列表 （分页）

> 接口 http://127.0.0.1:3000/v1/bill/get_bill_list?limit=2&offset=0

> 分页参数

```
  ?limit=value&offset=value
```

> 查询参数 （为空时，查询所有{data: {}}）

```
  {
    data: {
      user_id: value,         //用户id (可选)
      order_id: value,        //订单id （可选)
      order_type: value,      //订单类型: 1 入库单/ 2 出库单/ 3 撤单 / 4 其他 (可选)
      order_statu: value      //订单状态: 1 未支付 / 3 已支付 (可选)
      begin_time: value       //起始时间(可选) 
      end_time: value         //截止时间(可选)
    }
  }
```

> return 

```
{
  "data": {
    "total": 1,
    "rows": [
      {
        "_id": "574d25d720556af30a55e2ab",
        "created_minute": "35",
        "created_hour": "16",
        "created_day": "27",
        "created_month": "05",
        "created_year": "2016",
        "created_at_ms": "1464338143560",
        "user_id": 13581935031,
        "order_id": "order0012",
        "order_type": 2,
        "order_cost": 99.99,
        "order_year": "2016",
        "order_month": "05",
        "order_day": "27",
        "order_hour": "10",
        "order_minute": "34",
        "order_second": "33",
        "is_deleted": false,
        "updated_at": "2016-05-27T08:35:43.553Z",
        "created_at": "2016-05-27T08:35:43.552Z",
        "order_pay_time": "2016-05-27T08:35:43.462Z",
        "order_statu": 1,
        "__v": 0
      }
    ]
  },
  "status": {
    "code": 0,
    "msg": "request success!"
  }
}
```

> error

```
  {
    "data": null
    ,"status": {
      "code": 10000,
      "msg": "参数错误"
    }
  }
```

### 根据订单号，查询账单明细

> 接口 127.0.0.1:3000/v1/bill/get_bill_detail/:value

> 举例：127.0.0.1:3000/v1/bill/get_bill_detail/order0001

> return 

```
{
  "data": [
    {
      "_id": "574d3d2c20556af30a55e2ac",
      "created_minute": "35",
      "created_hour": "16",
      "created_day": "27",
      "created_month": "05",
      "created_year": "2016",
      "created_at_ms": "1464338143560",
      "user_id": 13581935031,
      "order_id": "order0001",
      "order_type": 2,
      "order_detail_name": "出库包材费用",
      "order_detail_cost": 15.5,
      "order_statu": 1,
      "order_year": "2016",
      "order_month": "05",
      "order_day": "27",
      "order_hour": "10",
      "order_minute": "34",
      "order_second": "33",
      "is_deleted": false,
      "updated_at": "2016-05-27T08:35:43.553Z",
      "created_at": "2016-05-27T08:35:43.552Z",
      "order_pay_time": "2016-05-27T08:35:43.462Z",
      "__v": 0
    }
  ],
  "status": {
    "code": 0,
    "msg": "request success!"
  }
}
```

> error

```
  {
    "data": null
    ,"status": {
      "code": 10000,
      "msg": "参数错误"
    }
  }
```













