---
layout: security.hbs
title: 安全
---

# 安全

## 向 Node.js 报告问题缺陷

通过 [HackerOne](https://hackerone.com/nodejs) 报告 Node.js 中的安全漏洞。

你的报告将在 24 小时内得到确认，并且你将会在 48 小时内收到一封更为详细的回复，告知接下来处理你
的提交的一些步骤。

在对您的报告进行初步答复后，安全小组将努力让您了解正在进行的修复状况和全面公告的进展情况。他们
可能会从你那儿了解更多有关于这个安全问题的信息以及建议等。这些更新至少将每五天发送一次；实际上
可能每隔 24—48 小时就会发送。

### Node.js 缺陷赏金计划

Node.js 项目参与了一个为安全研究员和负责任的公众披露者的官方的缺陷赏金计划。

此计划通过 HackerOne 平台 [https://hackerone.com/nodejs](https://hackerone.com/nodejs) 进行
管理并提供更多细节信息。

## 向第三方模块汇报缺陷问题

你应该向第三方模块相关负责维护人直接汇报此类安全问题，并通过 [Node 生态安全团队](https://hackerone.com/nodejs-ecosystem)进行组织协调。

有关于此计划的详情部分可以在 [安全工作组](https://github.com/nodejs/security-wg/blob/master/processes/third_party_vuln_process.md) 寻找到。

感谢你为提升 Node.js 及其生态系统的安全作出贡献。我们非常感激并认可你的努力以及负责任的公开信息。

## 披露政策

以下是 Node.js 中的披露政策：

- 我们首先接收安全报告，并将其分配给主要相关处理人员。此人将协调修复和发布过程、确认问题以及所有受影响版本的列表，审核代码以查找潜在的类似问题，并且为所有仍在维护中的版本准备了修复程序，并确保这些修复程序不会提交到公共存储库而是在本地保存，并等待发布。

- 为此漏洞选择了建议禁运日期，并且为此漏洞提出 CVE® （常见漏洞暴露）请求。

- 在禁运日期时，Node.js 安全邮件列表以公告副本形式发出，并且这些更改将被推送到公共存储库，并将新生成部署到 nodejs.org。在通知邮件列表的 6 小时内，将在 Node.js 博客上发布相关咨询副本。

- 通常禁运日期将在 CVE 发布之时起，在 72 小时内设置。但是这可能会因安全缺陷的严重程度或应用修复程序的困难程度而有所不同。

- 这个过程可能需要一些时间，特别是当需要与其他项目的维护人员进行协调时。但是将尽一切努力尽可能及时地处理 缺陷漏洞。但是我们仍必须遵循上面的发布过程，以确保以一致的方式处理泄漏。


## 收到安全更新

安全通告将通过以下方式发布：

- [https://groups.google.com/group/nodejs-sec](https://groups.google.com/group/nodejs-sec)
- [https://nodejs.org/en/blog](https://nodejs.org/en/blog)

## 对于此政策的评论与建议

如果你对于如何提高优化此流程有独特建议，请通过发送一个 [请求](https://github.com/nodejs/nodejs.org)
或是 [创建新提议](https://github.com/nodejs/security-wg/issues/new) 来与我们讨论。
