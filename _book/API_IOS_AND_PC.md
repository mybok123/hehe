# 小斑马支付系统api-> iso&pc 

### 统计最近两个月的未支付费用
> 接口 http://127.0.0.1/billapi/v1/ios/get_last_two_month_to_be_pay

> 参数 /?token=value

> return 

```
  { 
    data: [
      {
        year: value,             //年
        month: value,            //月
        cost_to_be_pay: value，  //待支付费用
      }
    ]  
  }
```

### 按月统计各费用状态的费用
> 接口 http://127.0.0.1/billapi/v1/ios/statistic_cost_by_pay_statu

> 参数 /?token=value&year=value&month=value

> return 

```
  { 
    cost_all：value,          //总费用
    cost_to_be_pay：value,    //待支付
    cost_already_pay：value   //已支付
  }
```

### 按月统计各支出分类费用 
> 接口  http://127.0.0.1/billapi/v1/ios/statistic_cost_by_pay_type

> 参数 /?token=value&year=value&month=value

> return

```
  {
    cost_stockin: value,   //入库费用 
    cost_stockout: value,  //出库费用
    cost_cancel: value,    //取消订单费用
    cost_other：value      //其他费用
  }
```

### 按月统计各费用状态的订单数
> 接口 http://127.0.0.1/billapi/v1/ios/statistic_order_count_by_pay_statu

> 参数 /?token=value&year=value&month=value

> return 

```
  { 
    order_count_all：value,          //总订单数
    order_count_to_be_pay：value,    //待支付
    order_count_already_pay：value   //已支付
  }
```

### 按月统计各支出分类订单数
> 接口  http://127.0.0.1/billapi/v1/ios/statistic_order_count_by_pay_type

> 参数 /?token=value&year=value&month=value

> return

```
  {
    order_count_stockin: value,   //入库订单数
    order_count_stockout: value,  //出库订单数
    order_count_cancel: value,    //取消订单数
    order_count_other：value      //其他
  }
```

### 按月获取账单列表 (分页)
> 接口  http://127.0.0.1/billapi/v1/ios/get_bill_list

> 参数 /?token=value&year=value&month=value&limit=value&offset=value

> return

```
  {
    order_list: [
      {
        order_id: value,    //订单id
        order_type: value,  //订单类型
        order_statu: value, //订单支付状态
        order_cost: value,  //订单费用
        order_date: value   //订单生成日期   
      }
    ]
  }
```

### 获取账单详情 
> 接口 http://127.0.0.1/billapi/v1/ios/api_get_bill_detail

> 参数 /?token=value&order_id=value

> return 

```
  {
    order_id: value,    //订单号
    cost_details: [        //费用
      {
        cost_detail_name: value， //费用明细名       
        cost: value          //费用
      }
    ],order_info: {
      ...
    }
  }
```

### 询问支付

> 接口 http://127.0.0.1/billapi/v1/ios/ask_pay

> 参数 /?token=value

> return

```
  {
    statu：0 //如果返回不为0，不能付款
  }
```

### 确认支付 

> 接口 http://127.0.0.1/billapi/v1/ios/confirm_pay

> 参数 /?token=value

> return

```  
  {
    statu：0 //如果返回不为0，做退款
  }
```






