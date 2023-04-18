# 一、 说明
## 1. geosite.dat
① 在 [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 的基础上进行修改，请酌情使用，每天早上 3 点（北京时间）自动构建    
② 将 `geosite:category-ads-all` 源修改为 [blackmatrix7/ios_rule_script/Advertising](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Advertising)  
③ 将 `geosite:category-public-tracker` 源修改为 [blackmatrix7/ios_rule_script/PrivateTracker](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/PrivateTracker)  
④ 将 `geosite:speedtest` 源修改为 [blackmatrix7/ios_rule_script/Speedtest](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Speedtest) 和 [IPv6 测试网站](https://github.com/DustinWin/clash-geosite/blob/master/Rule-Files/network.txt)组合   
⑤ 将 `geosite:geolocation-!cn` 源修改为 [blackmatrix7/ios_rule_script/Proxy](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Proxy)，并新增 `DOMAIN-SUFFIX,googleapis.cn`，防止出现 [Google Play Store](https://play.google.com/store) 无法下载或升级应用的问题  
⑥ 将 `geosite:cn` 源修改为 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)  
⑦ 删除“Windows 操作系统相关的系统升级和隐私跟踪域名”，包括 `geosite:win-spy`、`geosite:win-update` 和 `geosite:win-extra`
## 2. geoip.dat 和 Country.mmdb
① 在 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 的基础上进行修改  
② 只保留 `geoip:cn`、`geoip:private` 和 `geoip:telegram` 部分，刚好对应我所建 [Clash 规则模板](https://github.com/DustinWin/Router-Plugins/tree/main/Rule-Templates)中 rules 里的 3 项
# 二、 下载
## 1. geosite.dat
① GitHub 源：https://github.com/DustinWin/clash-geosite/releases/download/latest/geosite.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geosite@release/geosite.dat
## 2. geoip.dat
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
## 3. Country.mmdb
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
# 三、 导入
## 1. 导入 ShellClash
```
curl -o $clashdir/GeoSite.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geosite@release/geosite.dat
curl -o $clashdir/GeoIP.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
curl -o $clashdir/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
```
## 2. 导入 Clash Verge（Windows 端）
```
curl -o %USERPROFILE%\.config\clash-verge\geosite.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geosite@release/geosite.dat
curl -o %USERPROFILE%\.config\clash-verge\geoip.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
curl -o %USERPROFILE%\.config\clash-verge\Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
copy /y "%USERPROFILE%\.config\clash-verge\geosite.dat" "%PROGRAMFILES%\Clash Verge\resources"
copy /y "%USERPROFILE%\.config\clash-verge\geoip.dat" "%PROGRAMFILES%\Clash Verge\resources"
copy /y "%USERPROFILE%\.config\clash-verge\Country.mmdb" "%PROGRAMFILES%\Clash Verge\resources"
```
