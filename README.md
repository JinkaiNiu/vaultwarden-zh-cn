![Vaultwarden Logo](./resources/vaultwarden-logo-auto.svg)

Bitwarden 客户端 API 的替代服务器实现，使用 Rust 编写，并与 [官方 Bitwarden 客户端](https://bitwarden.com/download/) 兼容 [[免责声明](#免责声明)]，非常适合自托管部署，在自托管部署中，运行官方的资源密集型服务可能不太理想。

---

[![GitHub Release](https://img.shields.io/github/release/dani-garcia/vaultwarden.svg?style=for-the-badge&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/releases/latest)
[![ghcr.io Pulls](https://img.shields.io/badge/dynamic/json?style=for-the-badge&logo=github&logoColor=fff&color=005AA4&url=https%3A%2F%2Fipitio.github.io%2Fbackage%2Fdani-garcia%2Fvaultwarden%2Fvaultwarden.json&query=%24.downloads&label=ghcr.io%20pulls&cacheSeconds=14400)](https://github.com/dani-garcia/vaultwarden/pkgs/container/vaultwarden)
[![Docker Pulls](https://img.shields.io/docker/pulls/vaultwarden/server.svg?style=for-the-badge&logo=docker&logoColor=fff&color=005AA4&label=docker.io%20pulls)](https://hub.docker.com/r/vaultwarden/server)
[![Quay.io](https://img.shields.io/badge/quay.io-download-005AA4?style=for-the-badge&logo=redhat&cacheSeconds=14400)](https://quay.io/repository/vaultwarden/server) <br>
[![Contributors](https://img.shields.io/github/contributors-anon/dani-garcia/vaultwarden.svg?style=flat-square&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)
[![Forks](https://img.shields.io/github/forks/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4)](https://github.com/dani-garcia/vaultwarden/network/members)
[![Stars](https://img.shields.io/github/stars/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4)](https://github.com/dani-garcia/vaultwarden/stargazers)
[![Issues Open](https://img.shields.io/github/issues/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/issues)
[![Issues Closed](https://img.shields.io/github/issues-closed/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/issues?q=is%3Aissue+is%3Aclosed)
[![AGPL-3.0 Licensed](https://img.shields.io/github/license/dani-garcia/vaultwarden.svg?style=flat-square&logo=vaultwarden&color=944000&cacheSeconds=14400)](https://github.com/dani-garcia/vaultwarden/blob/main/LICENSE.txt) <br>
[![Dependency Status](https://img.shields.io/badge/dynamic/xml?url=https%3A%2F%2Fdeps.rs%2Frepo%2Fgithub%2Fdani-garcia%2Fvaultwarden%2Fstatus.svg&query=%2F*%5Blocal-name()%3D'svg'%5D%2F*%5Blocal-name()%3D'g'%5D%5B2%5D%2F*%5Blocal-name()%3D'text'%5D%5B4%5D&style=flat-square&logo=rust&label=dependencies&color=005AA4)](https://deps.rs/repo/github/dani-garcia/vaultwarden)
[![GHA Release](https://img.shields.io/github/actions/workflow/status/dani-garcia/vaultwarden/release.yml?style=flat-square&logo=github&logoColor=fff&label=Release%20Workflow)](https://github.com/dani-garcia/vaultwarden/actions/workflows/release.yml)
[![GHA Build](https://img.shields.io/github/actions/workflow/status/dani-garcia/vaultwarden/build.yml?style=flat-square&logo=github&logoColor=fff&label=Build%20Workflow)](https://github.com/dani-garcia/vaultwarden/actions/workflows/build.yml) <br>
[![Matrix Chat](https://img.shields.io/matrix/vaultwarden:matrix.org.svg?style=flat-square&logo=matrix&logoColor=fff&color=953B00&cacheSeconds=14400)](https://matrix.to/#/#vaultwarden:matrix.org)
[![GitHub Discussions](https://img.shields.io/github/discussions/dani-garcia/vaultwarden?style=flat-square&logo=github&logoColor=fff&color=953B00&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/discussions)
[![Discourse Discussions](https://img.shields.io/discourse/topics?server=https%3A%2F%2Fvaultwarden.discourse.group%2F&style=flat-square&logo=discourse&color=953B00)](https://vaultwarden.discourse.group/)

> [!IMPORTANT]
> **当使用此服务器时，请直接向我们报告任何错误或建议（请参阅 [联系方式](#联系方式)），无论您使用的是什么客户端（移动端、桌面端、浏览器端...）。请勿使用官方 Bitwarden 支持渠道。**

<br>

## 功能特性

提供了一个几乎完整的 Bitwarden 客户端 API 实现，包括：

 * [个人保管库](https://bitwarden.com/help/managing-items/)
 * [发送](https://bitwarden.com/help/about-send/)
 * [附件](https://bitwarden.com/help/attachments/)
 * [网站图标](https://bitwarden.com/help/website-icons/)
 * [个人 API 密钥](https://bitwarden.com/help/personal-api-key/)
 * [组织](https://bitwarden.com/help/getting-started-organizations/)
   - [集合](https://bitwarden.com/help/about-collections/),
     [密码共享](https://bitwarden.com/help/sharing/),
     [成员角色](https://bitwarden.com/help/user-types-access-control/),
     [群组](https://bitwarden.com/help/about-groups/),
     [事件日志](https://bitwarden.com/help/event-logs/),
     [管理员密码重置](https://bitwarden.com/help/admin-reset/),
     [目录连接器](https://bitwarden.com/help/directory-sync/),
     [策略](https://bitwarden.com/help/policies/)
 * [多因素/双因素认证](https://bitwarden.com/help/bitwarden-field-guide-two-step-login/)
   - [认证器](https://bitwarden.com/help/setup-two-step-login-authenticator/),
     [电子邮件](https://bitwarden.com/help/setup-two-step-login-email/),
     [FIDO2 WebAuthn](https://bitwarden.com/help/setup-two-step-login-fido/),
     [YubiKey](https://bitwarden.com/help/setup-two-step-login-yubikey/),
     [Duo](https://bitwarden.com/help/setup-two-step-login-duo/)
 * [紧急访问](https://bitwarden.com/help/emergency-access/)
 * [Vaultwarden 管理后端](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-admin-page)
 * [修改后的 Web Vault 客户端](https://github.com/dani-garcia/bw_web_builds)（捆绑在我们的容器中）

<br>

## 使用方法

> [!IMPORTANT]
> 大多数现代 Web 浏览器不允许在不安全的环境中使用 Web Crypto API。 在这种情况下，您可能会收到类似 `Cannot read property 'importKey'` 的错误。 要解决此问题，您需要通过 HTTPS 或 localhost 访问 Web Vault。
>
> 这可以在 [Vaultwarden 中直接配置](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS)，或者使用第三方反向代理（[一些示例](https://github.com/dani-garcia/vaultwarden/wiki/Proxy-examples)）。
>
> 如果您有可用的域名，则可以使用 [Let's Encrypt](https://letsencrypt.org/) 获取 HTTPS 证书，也可以使用 [mkcert](https://github.com/FiloSottile/mkcert) 等实用程序生成自签名证书。 一些代理会自动执行此步骤，例如 Caddy 或 Traefik（请参阅上面链接的示例）。

> [!TIP]
> **有关如何安装、使用和配置 Vaultwarden 的更详细示例，您可以查看我们的 [Wiki](https://github.com/dani-garcia/vaultwarden/wiki)。**

使用 Vaultwarden 的主要方式是通过我们的容器镜像，这些镜像发布到 [ghcr.io](https://github.com/dani-garcia/vaultwarden/pkgs/container/vaultwarden)、[docker.io](https://hub.docker.com/r/vaultwarden/server) 和 [quay.io](https://quay.io/repository/vaultwarden/server)。

还有一些 [社区驱动的软件包](https://github.com/dani-garcia/vaultwarden/wiki/Third-party-packages) 可以使用，但这些软件包可能会落后于最新版本，或者在 Vaultwarden 的配置方式上有所不同，如我们的 [Wiki](https://github.com/dani-garcia/vaultwarden/wiki) 中所述。

### Docker/Podman CLI

拉取容器镜像并从主机挂载卷以进行持久存储。<br>
如果您喜欢使用 podman，可以用 `podman` 替换 `docker`。

```shell
docker pull vaultwarden/server:latest
docker run --detach --name vaultwarden \
  --env DOMAIN="https://vw.domain.tld" \
  --volume /vw-data/:/data/ \
  --restart unless-stopped \
  --publish 80:80 \
  vaultwarden/server:latest
```

这将保留 `/vw-data/` 下的任何持久数据，您可以根据需要调整路径。

### Docker Compose

要使用 Docker Compose，您需要创建一个 `compose.yaml` 文件，该文件将保存运行 Vaultwarden 容器的配置。

```yaml
services:
  vaultwarden:
    image: vaultwarden/server:latest
    container_name: vaultwarden
    restart: unless-stopped
    environment:
      DOMAIN: "https://vw.domain.tld"
    volumes:
      - ./vw-data/:/data/
    ports:
      - 80:80
```

<br>

## 联系方式

有疑问、建议或需要帮助？ 加入我们在 [Matrix](https://matrix.to/#/#vaultwarden:matrix.org)、[GitHub Discussions](https://github.com/dani-garcia/vaultwarden/discussions) 或 [Discourse 论坛](https://vaultwarden.discourse.group/) 上的社区。

遇到错误或崩溃？ 请搜索我们的问题跟踪器和讨论，看看是否已经有人报告了。 如果没有，请[发起新的讨论](https://github.com/dani-garcia/vaultwarden/discussions) 或[创建新的问题](https://github.com/dani-garcia/vaultwarden/issues)。 确保您使用的是最新版本的 Vaultwarden，并且没有类似的未解决或已关闭的问题！

<br>

## 贡献者

感谢您对项目的贡献！

[![Contributors Count](https://img.shields.io/github/contributors-anon/dani-garcia/vaultwarden?style=for-the-badge&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)<br>
[![Contributors Avatars](https://contributors-img.web.app/image?repo=dani-garcia/vaultwarden)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)

<br>

## 免责声明

**此项目与 [Bitwarden](https://bitwarden.com/) 或 Bitwarden, Inc. 无关。**

但是，Vaultwarden 的一位活跃维护者受雇于 Bitwarden，并被允许在自己的时间为该项目做出贡献。 这些贡献独立于 Bitwarden，并由其他维护者审查。

维护人员共同努力，为项目设定方向，专注于为自托管社区（包括个人、家庭和小型组织）提供服务，同时确保项目的可持续性。

**请注意：** 对于因使用 Vaultwarden 而可能发生的任何数据丢失，我们概不负责。 这包括密码、附件和应用程序处理的其他信息。 我们强烈建议定期备份您的文件和数据库。 但是，如果您遇到数据丢失，我们鼓励您立即与我们联系。

<br>

## Bitwarden_RS

该项目以前称为 Bitwarden_RS，现已更名，以便与官方 Bitwarden 服务器分开，以避免混淆和商标/品牌问题。<br>
请参阅 [#1642 - v1.21.0 版本和项目重命名为 Vaultwarden](https://github.com/dani-garcia/vaultwarden/discussions/1642) 以获取更多说明。
