# apple-spider
A BASH Script checks availability of Apple devices.

这里简单写一下 readme, 请各位自行理解。`apsp` 代码仅供技术研究和学习使用，本人不提供技术支持，亦不对使用本代码造成的结果负责。

## 安装
1. `curl -fsSLOJ https://raw.githubusercontent.com/janlay/apple-spider/master/apsp`
2. `chmod +x apsp`

## 说明
目前仅可查询IP属地附近的Apple Store

## 依赖
- macOS: `brew install jq`
- Ubuntu: `apt install jq`

## 用法

查询店名包括「西湖」或「万象城」的店
`STORES='西湖|万象城' apsp MTQA3CH/A MTQ63CH/A`

查询1-2周可送货的型号
`WEEKS=1-2 apsp MTQA3CH/A MTQ63CH/A`

使用自定义的telegram脚本发送通知
`NOTIFICATION_TOOL=telegram STORES='西湖|万象城' apsp MTQA3CH/A MTQ63CH/A`

语音播报查询结果（仅macOS）
`NOTIFICATION_TOOL=say STORES='西湖|万象城' apsp MTQA3CH/A MTQ63CH/A`

在后台查询，日志写入 `~/apsp.log`
`NOTIFICATION_TOOL=telegram STORES='西湖|万象城' nohup apsp MTQA3CH/A MTQ63CH/A &>~/apsp.log &`

确认可以正常查询后，即可放心在后台查询
`NOTIFICATION_TOOL=telegram STORES='西湖|万象城' nohup apsp MTQA3CH/A MTQ63CH/A &>/dev/null &`

## LICENSE
[GPLv3](https://github.com/janlay/apple-spider/blob/master/README.md)

