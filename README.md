## 概述 Overview 

本目录包含构建和更新 [Sui 文档](https://docs.sui.io) 所需的资源。目录分为 `content` 和 `site` 两部分。要在本地运行 docs.sui.io 网站，请在终端或控制台中打开 `site` 目录。使用包管理器安装所需模块：

This directory contains the assets required to build and update the [Sui documentation](https://docs.sui.io). The directory is split between `content` and `site`. To run the docs.sui.io site locally, open the `site` directory in a terminal or console. Use a package manager to install the required modules:

```shell
pnpm install
```

然后在同一目录下构建站点：

In the same directory, the site should be built locally:

```shell
pnpm build
```

对于新克隆的仓库，这一步是必需的，因为它会下载 OpenRPC 规范文件，这些文件是部署网站所必需的。

This is necessary in the first instance with a freshly cloned repo as it will [download the OpenRPC specifications](/docs/site/src/utils/getopenrpcspecs.js) which are required to deploy the site.

接下来，使用以下命令在 localhost:3000 部署站点的开发预览版

Next, use the following command to deploy a development preview of the site to `localhost:3000`:

```shell
pnpm start
```
> 如果您在本地运行站点时收到提示缺少 open-rpc 规范文件的错误，请先运行 pnpm build。这将准备必要文件并解决该问题。

> If you're running the site locally and getting an error saying that you don't have `open-rpc` specs, run `pnpm build` first. It will prepare the files and fix the issue.

部署后会监视 `content` 目录（以及站点源文件）的更新，并根据您保存的更改实时更新界面。

The deployment watches for updates to files in the `content` directory (and site source files), updating the UI to match any saves you make. 

完成更改后，您应该再次运行 `pnpm build`。这将构建静态站点并将文件放置在 `site\build` 目录中。在提交更改以供审查之前，这一步很重要，因为构建过程会检查错误（如无效的内部链接），并在控制台显示错误原因。开发预览版会忽略此类错误以提供更灵活的开发环境。

Once you've finished making changes, you should again run `pnpm build`. This builds the static site and places the files in `site\build`. This is important to run before submitting your changes for review, because a build will fail on errors like bad internal links, displaying the cause of the error to the console. The development preview ignores such errors to provide a more agile environment.

Sui Foundation 无法为本地构建文档站点提供技术支持。如果遇到问题，请参考 [Docusaurus](https://docusaurus.io/) 文档。

Sui Foundation is not able to provide support for building the documentation site locally. If you run into trouble, consult the [Docusaurus](https://docusaurus.io/) documentation.

## 拉取请求 Pull requests

Sui 使用 Vercel 托管其文档站点。Vercel 会为提交到 Sui 仓库的每个拉取请求构建文档预览。您可以在 PR 评论区找到来自 Vercel 机器人的预览链接。点击 **sui-core** 项目的 **Visit Preview** 链接可以验证您的更改是否达到预期效果。

Sui uses Vercel to host its documentation site. Vercel builds a preview of the documentation for every pull request submitted to the Sui repo. You can find a link to this preview in the PR comment section from the Vercel bot. Click the **Visit Preview** link for the **sui-core** project to verify your changes behave as you expect.

如果您想在更改准备就绪前查看 Vercel 预览，可以将您的 PR 标记为草稿。

If you'd like to view the Vercel preview before your changes are ready for review, then [mark your PR as a draft](https://github.blog/2019-02-14-introducing-draft-pull-requests/).

## 贡献指南 Contributing

Sui 属于社区。为所有人的利益做出贡献。

Sui is for the community. Contribute for the benefit of all.

- 文档贡献指南 [Docs contributing guidelines](https://docs.sui.io/references/contribute/contribution-process)

- 仓库贡献指南 [Repo contributing guidelines](https://docs.sui.io/contribute-to-sui-repos)

- 风格指南 [Style guide](https://docs.sui.io/style-guide)

- 本地化 [Localization](https://docs.sui.io/localize-sui-docs)

- 行为准则 [Code of conduct](https://docs.sui.io/contribute/code-of-conduct)

## 许可证 License

Sui 文档在 [CC BY 4.0 许可证](../LICENSE-docs) 下分发。

The Sui Documentation is distributed under the [CC BY 4.0 license](../LICENSE-docs).
