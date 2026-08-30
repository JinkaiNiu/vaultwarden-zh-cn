# Vaultwarden 中文翻译模板

## 项目说明

这是一个专门用于 Vaultwarden 的中文翻译模板项目，为用户提供最新的中文本地化支持。

## 项目特点

- **精简结构**：删除了其他代码文件，仅保留中文翻译模板文件
- **即用型**：可以直接下载使用，无需额外配置
- **持续更新**：使用最新版本进行更新，保持与官方版本同步
- **最新翻译**：最近一次翻译日期为 2026年8月30日

## 翻译内容

### 管理面板模板
- `admin/base.hbs` - 基础布局模板
- `admin/diagnostics.hbs` - 诊断页面（包含最新的"无效的功能标志"章节）
- `admin/login.hbs` - 登录页面
- `admin/organizations.hbs` - 组织管理页面
- `admin/settings.hbs` - 设置页面
- `admin/users.hbs` - 用户管理页面

### 邮件模板
- 63个邮件模板文件，包含所有邮件通知的中文翻译

### 其他模板
- `404.hbs` - 404错误页面
- `scss/` - 样式文件

## 使用方法

1. 下载本仓库中的中文翻译模板文件
2. 按照 Vaultwarden 的本地化配置要求进行部署
3. 重启 Vaultwarden 服务以应用新的中文翻译

## 文件结构

```
templates/
├── 404.hbs
├── admin/
│   ├── base.hbs
│   ├── diagnostics.hbs
│   ├── login.hbs
│   ├── organizations.hbs
│   ├── settings.hbs
│   └── users.hbs
├── email/
│   ├── (63个邮件模板文件)
│   └── ...
└── scss/
    ├── user.vaultwarden.scss.hbs
    └── vaultwarden.scss.hbs
```

## 最近更新

### 2026年8月30日
- 添加"无效的功能标志"诊断章节到 `admin/diagnostics.hbs`
- 同步上游最新模板结构
- 更新CSS类名（`container-xxl` → `container-xl`）

### 2026年2月24日
- 初始中文翻译版本
- 翻译所有管理面板模板
- 翻译所有邮件模板

## 维护说明

本翻译模板会定期更新以适配 Vaultwarden 的新版本，确保用户能够获得完整的中文界面体验。

## 相关链接

- [Vaultwarden 官方仓库](https://github.com/dani-garcia/vaultwarden)
- [Vaultwarden Wiki](https://github.com/dani-garcia/vaultwarden/wiki)