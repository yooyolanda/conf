# conf
注：订阅配置的所有格式都要用英文字符。
订阅示范：  
```python
{
  info: ["karsms@icloud.com", "15574989048"]  
  sub: {
    "BTC": [100, [31511.0], True, False],
    "OCEAN": [1.22, [1.2], False, False],
    "PEPE": [200, [0.00000830], False, False]
  }
}
```

info代表你的个人信息，分别是邮箱和电话，会发送以下内容：  
  * 订阅币种3分钟线振幅1.2% 或者 15分线振幅3% 以上  
  * 所有币种里价格达到日线均线附近3%的提示，并且4小时线连续3个出现MACD柱上涨，代表有明显上升趋势  
  * 到达订阅币种的监控价格附近提示  
  * 特定币种里插针到预定价格的提示（见 binance_trend.py文件里的配置）  

sub的每行代表一个币种的订阅，比如  
"BTC": [100, [31511.0, 66688.9], True, False],  
代表BTC，在价格100买入，想要监控的价格列表是[31511.0, 66688.9]，也就是会在这俩价格附近3%发送邮件提示，后面两个暂时不用，都写False  
