# 未提到的选项可保持默认

## Sparkle 设置：

“虚拟网卡”内开启 ``严格路由`` | “DNS劫持” 填写 ``any:53,tcp://any:53``

“订阅与代理组设置”内关闭 ``接管DNS设置`` 与 ``接管域名嗅探设置``

“内核设置”的“高级设置”内开启 ``存储选择节点``、``存储FakeIP``、``使用RTT延迟测试``、``TCP并发``

## Sub-Store 设置
1.在“订阅管理”里添加机场的订阅链接，添加名称（例Sub1）。

2.在“文件管理”界面添加“Mihomo 配置”：

类型选“Mihomo配置” | 来源选“单条订阅” | 订阅名称选刚刚创建的“Sub1”订阅

在下方分别添加：

  链接①:``https://raw.githubusercontent.com/mihomo-party-org/override-hub/refs/heads/main/yaml/ACL4SSR_Online_Full_WithIcon.yaml``

  链接②:``https://raw.githubusercontent.com/Kwensiu/ProxyRule/refs/heads/main/Lastest.yaml``
  
  脚本
  ```
const prependRule = [
    "PROCESS-NAME,pwsh.exe,节点选择",
    "PROCESS-NAME,flix.exe,全球直连",
    "PROCESS-NAME,MuMuVMMHeadless.exe,全球直连",
    "PROCESS-NAME,完美世界竞技平台.exe,全球直连",
    "PROCESS-NAME,cs2.exe,全球直连",
    "PROCESS-NAME,Steam++.Accelerator.exe,全球直连"
    ];
function main(config) {
    let oldrules = config["rules"];
    config["rules"] = prependRule.concat(oldrules);
    return config;
    }
```
