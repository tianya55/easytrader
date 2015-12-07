# easytrader

* 进行简单的 web 股票交易
* **目前还很不完善,仅供测试**

### 支持券商

* 佣金宝

### requirements
> Python 3.4+
 
> pip install -r requirements.txt

### 用法

#### 引入:

```python
from easytrader import YJBTrader
```

#### 设置账户:

```python
user = YJBTrader()
user.token = 'ABC...CBA'
```

[如何获取 token](http://www.jisilu.cn/question/42707)

#### 获取资金状况:

```python
user.balance
```

**return**
```python
{
   'asset_balance': '资产总值',
   'current_balance': '当前余额',
   'enable_balance': '可用金额',
   'market_value': '证券市值',
   'money_type': '币种',
   'pre_interest': '预计利息'
}

```

#### 获取持仓:

```python
user.position
```

**return**
```python
[{'cost_price': '摊薄成本价',
   'current_amount': '当前数量',
   'enable_amount': '可卖数量',
   'income_balance': '摊薄浮动盈亏',
   'keep_cost_price': '保本价',
   'last_price': '最新价',
   'market_value': '证券市值',
   'position_str': '定位串',
   'stock_code': '证券代码',
   'stock_name': '证券名称'}]

```

#### 获取今日委托单
```python
user.entrust
```

**return** 

```python
[{'business_amount': '成交数量',
  'business_price': '成交价格',
  'entrust_amount': '委托数量',
  'entrust_bs': '买卖方向',
  'entrust_no': '委托编号',
  'entrust_price': '委托价格',
  'entrust_status': '委托状态',  # 废单 / 已报
  'report_time': '申报时间',
  'stock_code': '证券代码',
  'stock_name': '证券名称'}]

```


#### 买入:

```python
user.buy('162411', price=0.55, amount=100)
```

**return** 

```python
[{'entrust_no': '委托编号',
  'init_date': '发生日期',
  'batch_no': '委托批号',
  'report_no': '申报号',
  'seat_no': '席位编号',
  'entrust_time': '委托时间',
  'entrust_price': '委托价格',
  'entrust_amount': '委托数量',
  'stock_code': '证券代码',
  'entrust_bs': '买卖方向',
  'entrust_type': '委托类别',
  'entrust_status': '委托状态',
  'fund_account': '资金帐号',
  'error_no': '错误号',
  'error_info': '错误原因'}]
```

#### 卖出:

```python
user.sell('162411', price=0.55, amount=100)
```

#### 其他
其他可参考下面链接

[佣金宝](http://www.jisilu.cn/question/42707)