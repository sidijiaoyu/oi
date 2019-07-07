首先，十分感谢你花时间来给 OI Wiki 开一个 Pull Request，下面是一些你可能需要知道的信息：

- 请在 commit 的时候写比较有意义的 commit message
- 请给 PR 起比较有意义的标题。       
- 关于同一类尚未合并的 PR 修改请直接在对应的 fork / 分支中进行，除非已有的内容已被合并需要修改，否则**不要多开 PR** 。
- 请在 PR 之前检查一下您的 PR 是否存在以下常见问题：（确认无问题后请将选项打钩 / 填为 `[x]`）
   * [ ] 您的 MD 代码的书写格式，包括但不限于 **中文与英文之间、中文与阿拉伯数字、中文与 LaTeX 公式之间要有一个半角空格**，特别地，在中文全角符号与英文、阿拉伯数字、LaTeX 公式之间，**不需要**半角空格。（这个可以使用自动化工具辅助，比如 https://github.com/baurine/vscode-pangu)  
   * [ ] 请务必确保您的文档中引用的**外链**图片已经全部转存到了**本库内**对应的`images`文件夹中（防止触发某些网站的防盗链），并已全部处理成了`MD文档名称+编号`的形式（可参考已有文档中图片的处理方式）  
   * [ ] 请确保您的文档中的引用链接的稳定性，**不推荐**引用**自建**服务（如OJ）中的资源（如题目）
   * [ ] 对于 LaTeX 公式，请注意常见的问题，**一定要使用** `$\log$`、`$\min$`、`$\max$`、`$\gcd$` 等，而非 `$log$`、`$min$`、`$max$`、`$gcd$`。对于最小公倍数，请使用 `$\operatorname{lcm}$` 而非 `$lcm$`，省略号请使用 `$\cdots$`，叉乘请使用 `$\times$`，点乘请使用 `$\cdot$`。
   * [ ] 所有公式中的希腊字母等特殊符号，请不要使用输入法的插入特殊符号功能，而应该使用对应的 LaTeX 公式符号。如 phi 大多数情况下应该使用 `$\varphi$` 而不是 `$\phi$`。
   * [ ] 行间公式前后各要有一行空行。
   * [ ] 对于目录中存在公式的情况，请使用 HTML 代码而非直接插入公式以避免双倍公式的问题，请参考[避免 ToC 中双倍公式的写法](https://oi-wiki.org/intro/faq/#_13))。
   * [ ] NOI 系列赛英文名称请使用全大写，如 NOIP，其他比赛请与官方英文名称保持一致。

关于文档内容的基本格式和更多内容规范，可以查阅 [F.A.Q](https://oi-wiki.org/intro/faq/#_4)。