
# CEX API DOCUMENT

## 获取币种汇率

> GET /Api/bitfinex_ticker

### 参数说明
无
### 返回值说明
参数名|说明
-|-|-
btc_cny|btc对cny的汇率,下同
btc_usd|
eth_cny|
eth_usd|
usd_cny|
usd_usd|


## 获取本地币数据
> POST /Index/CurrencyList.html
### 参数说明
参数名|必填|说明
-|-|-
k|否|无
### 返回值说明
参数名|说明
-|-|-
currency_id|币种ID
currency_logo|logo
currency_mark|英文名称
currency_name|中文名称
new_price|最新价格
nstatus|涨跌，1涨，2跌
quid|交易对币种
symbol|交易对英文名
tcid|计价币种ID
tmark|计价币种名称


## error code
```javascript
{
	"10036":"提币数量小于最小提币数量",
	"10037":"交易密码未设置",
	"10040":"取消提币失败",
	"10041":"提币地址不存在或者未认证",
	"":"",
}
```


## Abbreviation Glossary
Term|Definition
-|-|-
hb|	heartbeating
te|	trade executed
tu|	trade execution update

