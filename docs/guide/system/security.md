# 安全设置
## 1 功能简述
!!! tip ""
    - 点击页面左侧的`安全设置`按钮，进入安全设置页面。
    - 安全设置页面主要配置 JumpServer 安全相关信息，编辑 MFA 设置以及密码等校验规则。

## 2 基本安全设置
!!! tip ""
    - JumpServer 基本安全设置如下图：
![security01](../../img/security01.png)

!!! tip ""
    - 详细参数说明：

!!! tip ""

    | 参数     | 说明                  |
    | ------- | --------------------- |
    | 作业中心 | 是否允许用户使用 Ansible 执行批量命令。 |
    | 终端注册 | 是否允许其他外部的组件注册到本地的 Core 组件上。 |
    | 连接最大空闲时间 | 资产在空闲时间达到此配置时会自动断开。 |
    | 开启水印 | 会话和录像会包含访问资产的堡垒机用户水印信息，RDP 客户端方式的连接不支持水印。 |
    | 会话分享 | 开启后允许用户以 URL 形式分享已连接的资产会话给他人，方便协同工作。 |

## 3 认证安全设置
!!! tip ""
    - JumpServer 认证安全设置如下图：
![security02](../../img/security02.png)

!!! tip ""
    - 详细参数说明：

!!! tip ""

    | 参数     | 说明                  |
    | ------- | --------------------- |
    | 全局启用MFA认证 | 可以设置禁用 MFA，或所有用户启用 MFA、或仅管理员启用。 |
    | 第三方登录用户进行MFA认证 | 支持 OIDC、CAS、SAML2 认证方式的用户进行 MFA 认证。 |
    | 启用登录附加码 | 密码和附加码一并发送给第三方认证系统进行校验, 如：有的第三方认证系统，需要密码+6位数字完成认证。 |
    | 用户密码过期时间 | 用户每隔多少天需要强制更新密码，单位：天。 <br> 如果用户在此期间没有更新密码，用户密码将过期失效； <br> 密码过期提醒邮件将在密码过期前5天内由系统（每天）自动发送给用户。 |
    | MFA校验有效期 | 查看账号密码校验 MFA 时的 MFA 有效期。 |
    | 异地登录保护 | 根据登录 IP 判断是否属常用登录城市，如果不是，会发送异地登录提醒邮件到用户邮箱。 |
    | 登录限制 | 用户登录策略的相关配置，见下文。 |
    | 密码强弱规则 | 密码强弱规则的相关配置，见下文。 |

## 4 登录限制
!!! tip ""
    - 登录限制是对用户登录堡垒机的一系列设置。
    - JumpServer 登录限制设置如下图：
![security03](../../img/security03.png)

!!! tip ""
    - 详细参数说明：

!!! tip ""

    | 参数     | 说明                  |
    | ------- | --------------------- |
    | 限制用户登录失败次数 | 用户输错密码最多登录失败次数，之后将会被锁定一段时间。 |
    | 禁止用户登录时间间隔 | 用户锁定的时间。 |
    | 限制 IP 登录失败次数 | 某 IP 最多登录失败次数，之后将会被禁止登录一段时间。 |
    | 禁止 IP 登录时间间隔 | IP 锁定的时间。 |
    | IP 登录白名单 | 允许登录堡垒机的 IP。 |
    | IP 登录黑名单 | 不允许登录堡垒机的 IP。 |
    | 仅一台设备登录 | 仅允许用户在一台设备上登录，下个设备登录，上一个登录被顶掉。 |
    | 仅已存在用户登录 | 仅允许存在于 JumpServer 用户列表中的用户登录。 |
    | 仅从用户来源登录 | 仅允许用户从用户列表中列出的来源处登录。 |

## 5 密码强弱规则
!!! tip ""
    - 密码强弱规则是关于登录堡垒机密码的规则设置。
    - JumpServer 密码强弱规则设置如下图：
![security04](../../img/security04.png)

!!! tip ""
    - 详细参数说明：

!!! tip ""

    | 参数     | 说明                  |
    | ------- | --------------------- |
    | 密码最小长度 | 设置用户密码支持的最小长度。 |
    | 管理员密码最小长度 | 设置管理员密码支持的最小长度。 |
    | 必须包含大写字符 | 密码中必须包含大写字符。 |
    | 必须包含小写字符 | 密码中必须包含小写字符。 |
    | 必须包含数字 | 密码中必须包含数字字符。 |
    | 必须包含特殊字符 | 密码中必须包含特殊字符，如#$@%等。 |
    | 不能设置近几次密码 | 用户重置密码时，不能为该用户前几次使用过的密码。 |


