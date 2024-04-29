# TVBox 电视频道菜单自定义与直播源接口自动校验与更新

自定义频道菜单，根据模板文件的直播源接口，自动获取并更新最新的直播源接口，校验并生成可用的频道接口文件

[English](./README-EN.md) | 中文

## 特点

- 自定义模板，生成您想要的频道分类与频道顺序
- 接口验效，过滤无效接口
- 按响应时间、分辨率综合权衡排序
- 定时执行，北京时间每日 8:00 执行更新一次
- 工作流更新频道数量上限 200 个，本地运行无限制
- 可设置重点关注频道，单独配置获取分页的数量
- 分页结果获取（可配置页数、接口数量）
- 保证更新时效性，配置获取最近时间范围内更新的接口
- 可过滤 ipv4、ipv6 接口
- 黑名单功能：接口域名与关键字
- 自定义接口获取源

## 配置

| 配置项                 | 默认值                                                                                                                      | 描述                                                               |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| source_file            | "demo.txt"                                                                                                                  | 模板文件名称                                                       |
| final_file             | "result.txt"                                                                                                                | 生成文件名称                                                       |
| favorite_list          | ["广东珠江","CCTV-1","CCTV-5","CCTV-5+","CCTV-13","广东体育","广东卫视","大湾区卫视","浙江卫视","湖南卫视","翡翠台"]        | 关注频道名称列表（仅用于与常规频道区分，自定义获取分页数量）       |
| favorite_page_num      | 5                                                                                                                           | 关注频道获取分页数量                                               |
| default_page_num       | 3                                                                                                                           | 常规频道获取分页数量                                               |
| urls_limit             | 10                                                                                                                          | 单个频道接口数量                                                   |
| response_time_weight   | 0.5                                                                                                                         | 响应时间权重值（所有权重值总和应为 1）                             |
| resolution_weight      | 0.5                                                                                                                         | 分辨率权重值 （所有权重值总和应为 1）                              |
| recent_days            | 30                                                                                                                          | 获取最近时间范围内更新的接口（单位天），适当减小可避免出现匹配问题 |
| ipv_type               | "ipv4"                                                                                                                      | 生成结果中接口的类型，可选值："ipv4"、"ipv6"、"all"                |
| domain_blacklist       | ["epg.pw"]                                                                                                                  | 接口域名黑名单，用于过滤低质量含广告类域名的接口                   |
| url_keywords_blacklist | []                                                                                                                          | 接口关键字黑名单，用于过滤含特定字符的接口                         |
| extend_base_urls       | ["https://m3u.ibert.me/txt/fmml_dv6.txt",<br>"https://m3u.ibert.me/txt/o_cn.txt",<br>"https://m3u.ibert.me/txt/j_iptv.txt"] | 接口获取源，目前仅兼容特定内容格式与部分频道名称的模糊匹配         |

## 快速上手

有关详细教程，请查看[快速上手](./docs/tutorial.md)

如果您不想折腾，刚好我的配置符合您的需求，可以使用以下链接：

- 接口源：https://mirror.ghproxy.com/raw.githubusercontent.com/Guovin/TV/gd/result.txt
- 数据源：https://mirror.ghproxy.com/raw.githubusercontent.com/Guovin/TV/gd/source.json

## 更新日志

[更新日志](./CHANGELOG.md)

## 免责声明

本项目是为了提供编程学习和研究的资源。项目中收集的数据来源于网络，开发者不对数据的准确性、完整性或可靠性做任何保证。

开发者不对任何可能因使用这些代码或数据而产生的任何直接或间接损失负责。使用者应自行判断其使用的合法性和风险。

本项目的代码和数据仅供学习和研究使用，不得用于任何商业用途。任何人或组织在使用时，应遵守相关法律法规，尊重并保护开发者的权益。

如果您使用了本项目的代码或数据，即表示您已了解并同意此免责声明。如果您不同意此免责声明，您应立即停止使用本项目的代码和数据。

此外，本项目的代码和数据可能会不定期进行更新，但不保证更新的及时性和准确性，也不保证代码的稳定性和功能性。

在任何情况下，因使用或无法使用本项目的代码或数据所产生的任何损害或其他责任，开发者和任何贡献者都不承担任何责任。

使用本项目的代码或数据即表示您已经了解并接受这些条款。

## GitHub 使用条款

在 Fork 或使用本项目时，您必须遵守[GitHub 使用条款](https://docs.github.com/cn/github/site-policy/github-terms-of-service)。这包括但不限于禁止上传违规内容，包括侵犯版权、非法、恶意或违反条款中的内容。任何违反这些规定的行为都可能导致您的账户被封禁。在使用本项目时，请确保您的行为符合这些规定。

如果您不同意遵守这些条款，您应立即停止使用本项目的代码和数据。

使用本项目的代码或数据即表示您已经了解并接受这些条款。

## 许可证

[MIT](./LICENSE) License &copy; 2024-PRESENT [Govin](https://github.com/guovin)
