### ans api

### asn单主列表

> type: json

> api: 127.0.0.1:3000/asn/

> ?pageno=1&pagesize=10&flag=A

> 数据格式

```
{
  'data':{
      "rows": [
          {
              "_id": "5731d78863af95c80a34144f",
              "asn_id": "ASN0009",
              "supplier": "ldl",
              "asn_statu": "A",
              "asn_create_date": "2016-05-10T12:43:52.007Z"
          },
          {
              "_id": "5731d78863af95c80a34144c",
              "asn_id": "ASN0008",
              "supplier": "ldl",
              "asn_statu": "A",
              "asn_create_date": "2016-05-10T12:43:52.005Z"
          }
      ],
      "total": 30
  },'status':{'code':0,'msg':'success'}
}
```

### asn detail

> type: json

> api: 127.0.0.1:3000/asn/detail/:asn_id

> asn_id = asn001

> 数据格式

```
{
    "_id": "5731d78863af95c80a34144f",
    "asn_detail": [
        {
            "pro_name": "枇杷露1",
            "pro_spec": "0.2g",
            "pro_origin": "石家庄",
            "pro_pack_size": "100",
            "pro_birth_date": "2016-05-10T12:43:52.007Z",
            "pro_dead_date": "2016-05-10T12:43:52.007Z",
            "qty": 100,
            "_id": "5731d78863af95c80a341451"
        },
        {
            "pro_name": "枇杷露2",
            "pro_spec": "0.2g",
            "pro_origin": "石家庄",
            "pro_pack_size": "100",
            "pro_birth_date": "2016-05-10T12:43:52.007Z",
            "pro_dead_date": "2016-05-10T12:43:52.007Z",
            "qty": 100,
            "_id": "5731d78863af95c80a341450"
        }
    ]
}
```