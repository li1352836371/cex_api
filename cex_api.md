<style>
blockquote{font-size:16px;}
</style>
# CEX API
> URL http://api.cex.com/api/v1/
> URL http://api.cex.plus/api/v1/

## 行情 API

### 交易对列表
> GET symbolList.do

### 返回值说明
参数名|说明
-|-|-
date|返回数据时服务器时间
symbol|交易对集合

### 全量行情
> GET tickerall
### 返回值说明
参数名|说明
-|-|-
date|返回数据时服务器时间
high|最高价
last| 最新成交价
low| 最低价
vol| 成交量(最近的24小时)

### 单个交易对行情
> GET ticker.do
### 参数说明
参数名|必填|说明
-|-|-
symbol|是|交易对，例：ltc_btc
### 返回值说明
参数名|说明
-|-|-
date|返回数据时服务器时间
high|最高价
last| 最新成交价
low| 最低价
vol| 成交量(最近的24小时)

### CEX市场深度
> GET depth.do
### 参数说明
参数名|必填|说明
-|-|-
symbol|是|交易对，例：ltc_btc
### 返回值说明
参数名|说明
-|-|-
asks | 卖盘,[price(成交价), amount(成交量)], 按price升序
bids | 买盘,[price(成交价), amount(成交量)], 按price降序

### 交易信息
> GET trade.do
### 参数说明
参数名|必填|说明
-|-|-
symbol|是|交易对，例：ltc_btc
### 返回值说明
参数名|说明
-|-|-
timestamp|交易时间
price| 交易价格
amount| 交易数量
type| buy/sell

### k线信息
> GET kline.do
### 参数说明
参数名|必填|说明
-|-|-
symbol|是|交易对，例：ltc_btc
type|是|类型，例：1m,5m,1h,1d,1w
size|否|数量，默认150

### 返回值说明
参数名|说明
-|-|-
amount|交易量
open| 开盘价
close| 收盘价
high| 最高价
low| 最低价
time| 时间


### 错误码说明
参数名|说明
-|-|-
1001|服务器繁忙
1002|交易对错误
1003|无数据
1004|k线类型错误