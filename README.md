# copilot-This-is-not-your-fault-it-s-my-problem
 copilot遇到——这不是你的错，而是我的问题



如果你正在使用clash或其类似代理工具作为代理，那么这是代理规则问题，具体为你的订阅地址自动设置了microsoft.com相关网址不走代理，导致全局代理才能强制开启代理，详细参考如下链接 https://www.cootechs.com/1504.html 。
具体方法是，左侧点击“Settings”，右侧点击“Parsers”的“Edit”。

```yaml
> parsers: # array
   - url: 你的订阅地址（不加引号）
     yaml:
       prepend-rules:
         - DOMAIN-SUFFIX,https://copilot.microsoft.com, TaiShan Net（此处替换为你的地址名称）

   - url: 你的订阅地址（不加引号）
     yaml:
       prepend-rules:
         - DOMAIN-SUFFIX,microsoft.com, TaiShan Net（此处替换为你的地址名称）

```

第一条规则的目的是保证直连,https://copilot.microsoft.com网址，第二条规则目的是覆盖你的订阅地址原有规则（原有规则：microsoft.com相关网址不走代理）
