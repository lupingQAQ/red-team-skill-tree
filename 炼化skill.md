<!-- redteam-reference v1 -->
# RedTeam & BlueArmy Knowledge Base (红蓝对抗知识库)

> 红蓝对抗实战参考知识库。当任务涉及渗透测试、红队评估、内网渗透、免杀、钓鱼、代码审计、后渗透横向移动等场景时，加载此skill提供专业参考。

---

## 1. 反溯源与匿名化

### 1.1 工作环境配置

**主机硬盘加密**: VeraCrypt (https://www.veracrypt.fr)

**虚拟机安全配置**:
- 删除蓝牙、NAT网卡；使用 Shadow Defender
- 渗透机与报告机分离；WPS禁止同步
- 密码管理: Mybase + KeePass

**个人信息清理**:
- 禁用个人ID/历史密码/历史账号，账号一次一弃
- 匿名邮箱: ProtonMail / Outlook
- 接码平台: sms-activate.io
- 设备购买(二手): 注意设备ID、WiFi BSSID (`netsh wlan show networks mode=bssid`)
- 手机卡: 线下购买/副卡；TG购买不绑自己手机号
- 虚拟币洗钱路径: 冷钱包→地下钱庄→U→多币种混币→U (损耗7%-10%，经洗钱公司总损耗~30%)

**反溯源分析要素**: 对手是谁(BC包网等) → 做了哪些链路 → 每跳泄露什么信息 → 谁能获取 → 时间成本 → 所需权限

### 1.2 匿名网络链路

**主机选购**: 非大陆地区(shockhosting/psychz.net/亚马逊云/CF/jtti.cc)，最好支持USDT，不同主机商分散

**链路搭建**:
- `境外流量卡 → frp → SoftEther VPN → LunaProxy(动态住宅代理)` ([SoftEtherVPN](https://github.com/SoftEtherVPN/SoftEtherVPN_Stable))
- `境外流量卡 → LunaProxy → 流量代理` ([suying999.net](https://suying999.net))
- `境内流量卡 → SoftEther VPN → 流量代理`
- VPN配置及痕迹清理

---

## 2. 信息收集

### 2.1 SGK数据来源

通信工具: BreachForums / Potato / 蝙蝠/海鸥/事密达 / TG / Signal / Discord / WhatsApp / Jabber / Session / Matrix / SimpleX

### 2.2 开源信息收集(OSINT)

**GitHub关键字搜索**: ldap(结合域名→内网资产) / login / 小业务 / 项目关联→账号 / 拼音缩写 / 子域名 / 内网域名 / com.xxx / 中文 / js|css|html特殊文件名

**GitHub人物关联**: star / fork / commit / follow

**资产平台**:
| 平台 | 特点 |
|------|------|
| SecurityTrails | 子域名、全球情报 |
| Censys | 每天扫端口，时效性强（可能不全），配合rustscan |
| FOFA / Hunter | 不允许实战虚拟机内登录 |
| Rapid7 DNS | 本地搭建ClickHouse查询 |

**其他渠道**: Gitee/看云/语雀/HackMD/石墨 | Google语法(`site:xxx.com -www -fare -css -parking`) | DuckDuckGo | HackerOne / Zeroday(hitcon.org) | Twitter/Facebook/LinkedIn(员工→初始密码规则) | 网盘(第三方) | Medium

**Bypass CDN**: 页面特征→真实IP / 历史解析→真实IP / 其他业务关联IP段→真实IP

### 2.3 供应链信息收集

供应商大会(海外企业) / 招投标 / 页面特征(js/css/html) / 接口特征 / 联系方式找源码

---

## 3. 渗透实战

### 3.1 黑盒快速打点思路

**BC站点攻击面**:
| 目标 | 攻击手法 |
|------|---------|
| 活动站 | SQL注入(sqlmap改造指定库表)、备份文件、框架漏洞(RCE/反序列化/上传/任意文件读写)、临时搭建(翻文件横向→MQ→钓鱼) |
| 客服站 | XSS→钓鱼/electron RCE、找客服系统供应商测试站/源码、扫目录、套路客服 |
| 页面关联 | JS/JS Console/静态资源/WSS(不靠谱) |
| 包网运维 | Jenkins/国产OA/MQ、测试站弱口令/GETShell→横向/挂马钓鱼/拿源码/报错调试 |
| 四方支付 | Login Proxy、找框架/资产/漏洞 |

**CP站点**: 注入(投注环节/签到/轮盘/ORDER BY)、客服站(邀请码/53/meiqia)、导航站、聊天室(XSS→WS)、图片站(找包网)、编辑器(UEditor→SSRF→内网/真实IP)、多端口高端口、宝塔/护卫神搭建靶场

**ZP站点**: 头像/语音朋友圈上传→钓鱼、裸聊同城→刷单、PHP变量覆盖、路由filter/WAF、漏洞点(配置文件硬编码→Cookie伪造、危险函数debug)

### 3.2 常见漏洞利用要点

**SQL注入**:
- 不依赖sqlmap，自写脚本
- 判断: 站库分离? 写权限? 命令执行?(Oracle 19c sys)
- 不可破解→写入后台账密/配置参数/改写密钥(Bcrypt/文件类型)
- 工具: [ghauri](https://github.com/r0oth3x49/ghauri)

**任意文件读取**: 敏感文件(.bash_history/.viminfo/源码/配置/日志/启动脚本)、列目录?跨盘符? `/proc/net/` `/proc/self/` `/proc/pid/`

**任意文件上传**: 目录返回? 跨盘符? 配合文件包含? 上传OSS?

**Docker逃逸**:
```
判断: .dockerenv | /proc/1/cgroup | mount|grep docker
特权模式: cat /proc/self/status | grep Cap → 0000003fffffffff → 挂载宿主机
Registry API未授权: https://github.com/Soufaker/docker_v2_catalog
Remote API(2375): docker -H tcp://<target>:2375 ps -a
工具: container-escape-check / CDK
```

**SSRF云元数据**:
- 阿里云: `http://100.100.100.200/latest/meta-data`
- 腾讯云: `http://metadata.tencentyun.com/latest/meta-data/`
- 华为云: [ECS用户手册](https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html)

**ThinkPHP漏洞速查**:
| 版本 | 漏洞 | 关键点 |
|------|------|--------|
| 5.0.0-5.0.23 | RCE(变量覆盖+代码执行) | `_method=__construct&filter[]=system` |
| 5.0.0-5.0.23 | 任意类调用 | `s=index/\think\app/invokefunction` |
| 6.0.1-6.0.13 | 多语言RCE | pearcmd文件包含 `lang=../../../../../../usr/local/lib/php/pearcmd` |
| 3.2.* / 5.0.0-5.0.18 | 模板变量覆盖+文件包含 | View::assign() 配合图片马/日志 |

**SSH后门**:
- tsh: 内网机器→外网连接，VPS不能断
- PAM后门: 测试好版本，保持连接
- [sshdHooker](https://github.com/9bie/sshdHooker)

**痕迹清除**: [ShadowlessFeet](https://github.com/r00tSe7en/ShadowlessFeet) | `unset HISTORY HISTFILE HISTSAVE; export HISTFILE=/dev/null; export HISTSIZE=0` | 修改文件时间

---

## 4. 代码审计

### 4.1 Java代码审计

**SQL注入(MyBatis)**: `order by ${time}` / `LIKE '%${stuName}%'` / `in (${id})` / OGNL注入(`${@java.lang.Runtime@getRuntime().exec("whoami")}`)

**反序列化**: fastjson(确定有CC链) / shiro / log4j → 根据依赖版本确定链子 → 知道原理+有POC+能改POC

**SSTI(Thymeleaf)**: SPEL表达式执行 → 前提: 表达式无过滤 + getValue/setValue + StandardEvaluationContext

**组件弱口令/未授权**: Druid(未授权+RCE) / swagger-ui / xxl-job

**过滤器缺陷**: 目录穿越→越权 / XSS / 黑白盒结合跑未授权接口

**登录绕过**: 路径穿越(`GET /api/admin/login/../../../api/userBill/export`) / secret硬编码→伪造token / 伪随机(种子相同→预测)

### 4.2 PHP代码审计

**TP3/5区别**: TP3目录大写开头 vs TP5/6小写；日志存放位置不同

**架构**: runtime(缓存+session) / application(项目源码) / thinkphp(框架) / vendor(composer库) / extend(第三方库)

**注入点**: count/max未过滤→parseKey / _parseOptions直接拼接 / parseWhereItem直接拼接(bind/between/eq表达式) / parseData未过滤(parseKey)

**文件操作**: file_get_contents→任意文件读/SSRF / curl / php://input / extends鉴权类 / is_dir/unlink→phar反序列化(CI4)

**XSS**: htmlspecialchars默认不转义单引号 / 多次编码转换

### 4.3 Java反序列化基础

**ClassLoader体系**: BootStrap(rt.jar) → ExtClassLoader → AppClassLoader(URLClassLoader)
- 双亲委派: loadClass / findClass / findLoadedClass / defineClass(传入字节码→JVM加载) / resolveClass
- BCEL ClassLoader: `com.sun.org.apache.bcel` (JDK<8u251)，通过`$$BCEL$$`编码加载字节码

**命令执行链**: TransformerChain→newTransformer/getOutputProperties→defineTransletClasses→newInstance触发static块

---

## 5. 后渗透与内网横向

### 5.1 域渗透提权

**凭证基础**: NTLM流程 → winlogon.exe接收密码 → lsass.exe比对SAM

**票据类型**: 黄金票据 / 白银票据 / 钻石票据 / 蓝宝石票据

**委派攻击**: 非约束委派 / 约束委派 / 基于资源的约束委派(RBCD)

**关键CVE速查**:
| CVE | 名称 | 核心原理 |
|-----|------|---------|
| MS14-068 | PAC伪造 | KDC对PAC签名算法无验证→伪造高权限PAC(512/520/518/519) |
| CVE-2020-1472 | Zerologon | AES-CFB8加密全零明文→1/256概率全零密文→NetrServerPasswordSet2置空密码 |
| CVE-2021-1675/34527 | PrintNightmare | RpcAddPrinterDriver无需SeLoadDriverPrivilege→SYSTEM RCE |
| CVE-2021-42287+42278 | noPac | 机器账户名不以$结尾→创建与DC同名账户→S4U2Self→高权限ST |
| CVE-2022-26923 | ADCS | DNSHostname修改→证书欺骗 |

**NTLM中继工具**: Responder / Inveigh / multirelayx.py / PrinterBug / PetitPotam / DFSCoerce / ShadowCoerce / PrivExchange / [Coercer](https://github.com/p0dalirius/Coercer)

**Azure AD**: 获取Azure AD连接同步账户 → DC Sync

### 5.2 服务器提权

**Potato系列**: SeImpersonate身份验证后模拟客户端 → COM基础(IUnknown: QueryInterface/AddRef/Release) → Rotten Potato(SSPI+CoGetInstanceFromIStorage)

**Linux提权**: 内核漏洞 / SUID / sudo配置错误 / cron任务 / 可写脚本

### 5.3 RPC横向移动

| 工具 | 方法 |
|------|------|
| wmiexec-Pro | Win32_ScheduledJob |
| NO445-lateral-movement | Win32_Process |
| WMIHACKER | WMI命令执行 |
| SCShell | ChangeServiceConfigW |
| rpc2socks | SOCKS代理 |
| TaskSchedulerMisc | MS-TSCH计划任务 |

### 5.4 凭证收集工具精选

| 工具 | 功能 |
|------|------|
| Pypykatz | Python mimikatz |
| PassTheChallenge | Credential Guard绕过 |
| Dumpert | System Calls转储(旧) |
| certsync | 证书利用 |
| PPLFault | 攻击PPL进程保护 |
| RToolZ | ProcExp152.sys驱动转储PPL Lsass |
| SharpToken | 进程Token泄露 |
| RDPCredentialStealer | Detours API Hook读RDP凭证 |
| spraycharles | 慢速密码喷射 |

---

## 6. 内网信息收集

### 6.1 主机管理工具解密

| 工具 | 解密项目 |
|------|---------|
| FinalShellGetPass | FinalShell密码 |
| ChromeKatz | Chrome凭证 |
| BrowserPivot | 浏览器影子文件 |
| LaZagne | 全平台密码恢复 |
| telegram-desktop-decrypt | TG桌面端 |
| readTdose-xiangrikui | ToDesk/向日葵 |
| keepass-password-dumper | KeePass |

### 6.2 内网第一步

**Linux getshell后**:
- 重新爬取web源码找敏感信息(secretkey/硬编码/URL)
- 找本机关键信息: hosts / history / .viminfo / SSH私钥
- PAM抓SSH密码(SO文件本地编译) / 扫内存([dismember](https://github.com/liamg/dismember))
- 找目录: `find / -writable -type d 2>/dev/null`
- 幽灵登录: `ssh -T root@192.168.1.1 /usr/bin/bash -i` (不分配伪终端无日志)

**Windows信息收集**:
- 注册表: [Nemesis](https://github.com/SpecterOps/Nemesis)
- 敏感文件: [FileSearch](https://github.com/c1y2m3/FileSearch) / [searchall](https://github.com/Naturehi666/searchall) / [FindEverything](https://github.com/AabyssZG/FindEverything)
- RDP劫持: RDPCredentialStealer / pyrdp / RdpThief

**找域**: resolv.conf(dns) / krb5.conf / smb.conf / cifs挂载 / NAS / AD验证Web服务 / VDI / WSUS / SCCM / EDR管控终端 / 网络连接(139/445/389/636)

---

## 7. 钓鱼

### 7.1 话术

| 目标 | 话术 |
|------|------|
| 赌客 | 系统故障(无法开户/充值/提现)、开启代理(无法返水)、海外赌客(无法添加银行卡) |
| 应聘 | 发送简历→约会议室→面试软件升级 |
| 合作 | 公会会长/赌客资料/四方支付/包网服务(提供案例/源码/更新) |

### 7.2 钓鱼基础设施

**域名**: [Expireddomains.com](http://www.expireddomains.com) (typo/unicode) / [ditto](https://github.com/evilsocket/ditto)

**SPF绕过**: [spf](https://github.com/SummerSec/spf) / [espoofer](https://github.com/chenjj/espoofer) / [swaks](https://github.com/jetmore/swaks) / [emkei.cz](https://emkei.cz/) / SendGrid / mailgun

**钓鱼页面**: [SiteCopy](https://github.com/Threezh1/SiteCopy) / [zphisher](https://github.com/htr-tech/zphisher) / [EvilnoVNC](https://github.com/JoelGMSec/EvilnoVNC) / evilginx

**Fake Login**: [fakelogonscreen](https://github.com/bitsadmin/fakelogonscreen) / [SharpLocker](https://github.com/Pickfordmatt/SharpLocker) / [CredsLeaker](https://github.com/Dviros/CredsLeaker)

### 7.3 马子制作

| 技术 | 说明 |
|------|------|
| WinRAR自解压/CVE-2023-38831 | [exploit](https://github.com/b1tg/CVE-2023-38831-winrar-exploit) |
| RLO文件名倒置 | `os.rename('1.exe', '1\u202egnp.exe')` |
| LNK快捷方式 | [lnkbomb](https://github.com/dievus/lnkbomb) / [Lnk-Trojan](https://github.com/Yihsiwei/Lnk-Trojan) |
| CHM | easychm + HTML HELP ActiveX执行命令 |
| ICO替换 | BeCyIconGrabber / Resource Hacker |
| PDF | [Bad-Pdf](https://github.com/deepzec/Bad-Pdf) |
| 文件捆绑 | [GoFileBinder](https://github.com/inspiringz/GoFileBinder) |

---

## 8. 远控与免杀

### 8.1 CobaltStrike

**插件开发**: [LSTAR](https://github.com/lintstar/LSTAR) / [CS-AutoPostChain](https://github.com/lintstar/CS-AutoPostChain) / [Ghosting-BOF](https://github.com/qigpig/Ghosting-BOF) / [PrivKit](https://github.com/mertdas/PrivKit) / [Chisel-Strike](https://github.com/m3rcer/Chisel-Strike)

**服务器**: 禁ping(`net.ipv4.icmp_echo_ignore_all=1`) / CDN(免费CF)

**Beacon特征修改**:
- 修改key(OriginKey→CustomizeKey)
- Profile: `strrep "beacon.x64.dll" ""` / `magic_mz_x86/x64` / `magic_pe` / `cleanup=true` / `obfuscate=true` / `userwx=false`
- SleepMask: 修改key和异或逻辑
- 替代Beacon: [geacon_plus](https://github.com/Z3ratu1/geacon_plus) / [beacon-rust](https://github.com/b1tg/cobaltstrike-beacon-rust) / [Beacon.dll](https://github.com/NoOne-hub/Beacon.dll)

### 8.2 哥斯拉去特征

- 去除MD5校验(ApplicationConfig.java) / 去HTTP头特征
- 修改key取值(后16位) → ShellEntity.getSecretKeyX + 加密类.generate
- 修改execCommand: 复制cmd到临时目录执行并删除
- 修改反射Load方法名过特征免杀
- 插件开发: 包名`shells.plugins.*` + PluginnAnnotation注解 + Plugin接口

### 8.3 流量转发工具二次开发

- 修改UA头 / 配置文件自删除(硬编码到main+XOR加密) / 远程加载配置
- TLS指纹修改(frp: pkg/util/net/tls.go) / 域前置(websocket.go+CDN HTTP回源)
- 外联小众协议(QUIC) / Protobuf插件 / 自定义加解密(ChaCha20/异或)
- 去硬编码(salt/json) / 编译混淆(UPX/garble/[go-strip](https://github.com/boy-hack/go-strip)) / DLL加载

### 8.4 EDR免杀

**白驱动致盲EDR**:
| 回调 | 作用 | 干掉方法 |
|------|------|---------|
| ObRegisterCallbacks | 进程/线程句柄操作 | CallbackList→PreOperation=0 |
| CmRegisterCallback | 注册表访问/修改 | CallbackListHead→PEX_CALLBACK_FUNCTION |
| MiniFilter | 文件创建/修改/删除 | _CALLBACK_NODE→替换为系统驱动结构地址 |
| PsSetCreate*NotifyRoutine | 进程/线程创建销毁 | EX_CALLBACK_ROUTINE_BLOCK.Function |

**工具**: [loldrivers.io](https://www.loldrivers.io/drivers/) / BYOVDKit / BYOVD / [ioctlfuzzer](https://github.com/Cr4sh/ioctlfuzzer)

**加密混淆**:
- 编码: 异或/Base64/UUID/MAC/IP/注册表键值/剪切板
- 序列化: Protobuf/Pickle
- 分离加载(文件/URL) / 动态API(LoadLibrary+GetProcAddress / TEB→PEB→kernel32 / SSN→Syscall)
- [SysWhispers3](https://github.com/klezVirus/SysWhispers3) / [HellBunny](https://github.com/voidvxwt/HellBunny)

**内存执行**:
- 申请: VirtualProtect/VirtualAlloc/HeapCreate
- 写入: RtlMoveMemory/RtlCopyMemory
- 执行回调: EnumSystemLocalesA/CreateThread/回调函数([Abusing Win Functions](http://ropgadget.com/posts/abusing_win_functions.html))

**反沙箱**: 开机时间/物理内存/CPU个数/Temp文件数/随机字符串服务器校验/USB记录/样本名称/硬盘大小/联网检测/命名管道

**注入技术**: 远程线程(CreateRemoteThread) / APC(APC+间接系统调用+模块踩踏) / DLL劫持(WinSxS/OneDrive) / 内核注入

---

## 9. 调证镜像还原(Linux)

1. **恢复镜像**: `qemu-img convert -f raw 要转换的.raw -O vmdk 生成的.vmdk`
2. **修改虚拟机配置**: 选使用现有磁盘
3. **修改密码**: 启动页面按e → 单用户模式 → `ro`后面改为`rw init=/bin/bash` → 删除cloud-init → `passwd`
4. **修改网络**: `ip a` → `dhclient eth0` → 网络选择仅主机
5. **信息收集**: 查看历史命令 / 查看服务 / 服务对应文件

---

## 10. 实战字典与工具包

**字典**: [9bie/dict](https://github.com/9bie/dict) / [SecDictionary](https://github.com/SexyBeast233/SecDictionary) / [MyDict](https://github.com/r00tSe7en/MyDict)

**快速代码审计**: [FindEverything](https://github.com/AabyssZG/FindEverything) / [CodeReviewTools](https://github.com/Ppsoft1991/CodeReviewTools) / [code-inspector](https://github.com/4ra1n/code-inspector) / [jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)

**扫描检测**: [Situational-Awareness](https://github.com/cmluZw/Situational-Awareness) / [WatchAD](https://github.com/Qianlitp/WatchAD) / [WatchAD2.0](https://github.com/Qihoo360/WatchAD2.0)

**密码解密汇总**: [passwd_decrypt_Tools](https://github.com/lemonlove7/passwd_decrypt_Tools) / [Pillager](https://github.com/qwqdanchun/Pillager) / [GoThief](https://github.com/Pizz33/GoThief)

**Java反编译**: [javadecompilers.com](http://www.javadecompilers.com/) / [jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)

**BBScan打包**: `pyinstaller.exe -F BBScan.py --clean --add-data rules;rules`
<!-- /redteam-reference -->
