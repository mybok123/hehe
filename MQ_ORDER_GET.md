## 与订单系统通过MQ交互

### mq队列 格式

```
{
  data: {
    {
      user_id: value,     //用户id
      order_id: value,    //订单id
      order_type: value,  //订单类型
      order_cost: value,  //订单总费用
      order_date: value   //订单生成日期
      order_detail: [
        {
          order_detail_name: value,
          order_detail_cost: value
        }
      ],order_info: {
        //一坨
      }
    }
  }
}
```