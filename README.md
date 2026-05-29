# 广告拦截规则集 1hbr9w

[中文版] 持续更新的广告/追踪/恶意域名规则集，适配 AdGuard / Clash / dnsmasq / Pi-hole。

## 规则来源

本规则集整合了多个高质量过滤列表：
- EasyList（含中文补充）
- AdGuard DNS Filter
- 国内去广告规则
- 恶意软件域名黑名单

## 文件说明

| 文件 | 用途 | 适用平台 |
|------|------|---------|
| ad-domain.yaml | DNS 劫持规则 | Clash / SmartDNS |
| malware.yaml | 恶意软件域名 | 所有平台 |

## 在 Clash 中使用

rules:
  - RULE-SET,https://raw.githubusercontent.com/flclash-us/adblock-rules-1hbr9w/main/rules/ad-domain.yaml,REJECT
  - RULE-SET,https://raw.githubusercontent.com/flclash-us/adblock-rules-1hbr9w/main/rules/malware.yaml,REJECT
  - GEOIP,CN,DIRECT
  - MATCH,DIRECT

## 在 AdGuard Home 中使用

设置 > DNS 封锁清单 > 添加自定义规则：
https://raw.githubusercontent.com/flclash-us/adblock-rules-1hbr9w/main/rules/ad-domain.yaml

## 常见问题

Q: 广告仍然显示？A: 某些广告通过 JavaScript 注入，需要浏览器级广告插件（如 uBlock Origin）。
Q: 如何添加白名单？A: 在规则文件顶部添加：@@||example.com^

## 许可证

MIT License

推荐工具

- [Clash for Windows](https://clashforwindows.site/) - Windows 最流行的 Clash 图形化客户端
- [ClashMI](https://clashmi.site/) - 轻量级 Clash 客户端，支持多平台
- [FlClash](https://flclash.us/) - 现代代理工具，支持多种协议