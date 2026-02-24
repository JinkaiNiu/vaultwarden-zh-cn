# Vaultwarden 中文翻译工作总结

## 翻译完成日期
2026年2月24日

## 翻译范围

本次翻译涵盖所有模板文件中的文案部分，包括：

### 1. 管理页面模板 (7个文件)
- ✅ 404.hbs - 404页面错误提示
- ✅ admin/base.hbs - 管理后台基础布局（菜单、主题切换等）
- ✅ admin/login.hbs - 管理员登录页面
- ✅ admin/diagnostics.hbs - 诊断信息页面
- ✅ admin/settings.hbs - 设置页面
- ✅ admin/users.hbs - 用户管理页面
- ✅ admin/organizations.hbs - 组织管理页面

### 2. 电子邮件文本模板 (37个文件)
所有 .hbs 格式的电子邮件模板已翻译：
- ✅ welcome.hbs - 欢迎邮件
- ✅ welcome_must_verify.hbs - 欢迎邮件（需要验证）
- ✅ register_verify_email.hbs - 注册验证邮件
- ✅ verify_email.hbs - 邮箱验证邮件
- ✅ change_email*.hbs - 邮箱变更邮件（3个变种）
- ✅ delete_account.hbs - 删除账户邮件
- ✅ twofactor_email.hbs - 两步验证邮件
- ✅ new_device_logged_in.hbs - 新设备登录通知
- ✅ protected_action.hbs - 受保护操作验证邮件
- ✅ send_org_invite.hbs - 组织邀请邮件
- ✅ invite_accepted.hbs - 邀请已接受通知
- ✅ invite_confirmed.hbs - 邀请已确认通知
- ✅ incomplete_2fa_login.hbs - 未完成的两步登录提醒
- ✅ admin_reset_password.hbs - 管理员重置密码通知
- ✅ pw_hint_none.hbs - 无密码提示通知
- ✅ pw_hint_some.hbs - 密码提示通知
- ✅ send_emergency_access_invite.hbs - 紧急访问邀请
- ✅ emergency_access_invite_accepted.hbs - 紧急访问邀请已接受
- ✅ emergency_access_invite_confirmed.hbs - 紧急访问联系人已确认
- ✅ emergency_access_recovery_initiated.hbs - 紧急访问请求已启动
- ✅ emergency_access_recovery_approved.hbs - 紧急访问请求已批准
- ✅ emergency_access_recovery_rejected.hbs - 紧急访问请求已拒绝
- ✅ emergency_access_recovery_reminder.hbs - 紧急访问请求待处理提醒
- ✅ emergency_access_recovery_timed_out.hbs - 紧急访问请求已授予
- ✅ send_2fa_removed_from_org.hbs - 由于缺少2FA被从组织中移除
- ✅ send_single_org_removed_from_org.hbs - 由于多组织政策被移除
- ✅ smtp_test.hbs - SMTP 测试邮件
- ✅ sso_change_email.hbs - SSO 邮箱变更通知

### 3. HTML 电子邮件模板 (30个文件)
所有 .html.hbs 格式的电子邮件模板已进行翻译：
- HTML 标记和结构保持不变
- 所有文本内容翻译为中文简体
- 动态变量（如 {{url}}, {{token}}, {{email}} 等）保持原样

### 4. SCSS 模板 (2个文件)
- scss/user.vaultwarden.scss.hbs - 用户样式
- scss/vaultwarden.scss.hbs - 主样式
(注：这些文件主要包含CSS，无需翻译)

## 翻译原则

1. **逻辑不变** - 所有翻译严格按照原英文意思进行，不改变任何逻辑或功能
2. **格式保留** - 所有 HTML 标记、Handlebars 变量、CSS 样式等完全保留
3. **专业用语** - 使用规范的中文简体术语
4. **一致性** - 相同概念在所有文件中使用一致的翻译

## 主要翻译术语对照表

| 英文 | 中文 |
|------|------|
| Account | 账户 |
| User | 用户 |
| Organization | 组织 |
| Two-Factor / 2FA | 两步验证 |
| Web Vault | 网页保险库 |
| Settings | 设置 |
| Authentication | 身份验证/身份认证 |
| Admin | 管理员 |
| Diagnostics | 诊断 |
| Emergency Access | 紧急访问 |
| Master Password | 主密码 |

## 文件统计

- 管理页面模板：7 个文件
- 电子邮件文本模板：37 个文件
- 电子邮件 HTML 模板：30 个文件
- 样式文件：2 个文件
- **总计：76 个文件**

## 翻译质量保证

所有翻译文件已验证：
- ✓ 没有改变代码逻辑
- ✓ 所有模板变量和标记完整保留
- ✓ 中文文案准确、专业
- ✓ HTML 结构完整
- ✓ Handlebars 语法正确

## 部署说明

将翻译后的文件复制到 Vaultwarden 的 templates 目录即可使用，无需额外配置。
