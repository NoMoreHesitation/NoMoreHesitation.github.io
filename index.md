## Welcome to git learning record

Git 不仅仅是简单的复制粘贴，他保存了提交的历史记录，这也是为什么大多数提交记录的上面都有父节点的原因

具体指令：

git commit 生成新的节点并保存父节点

早建分支！多用分支！

git branch XX 用于在当前节点建立分支XX

git checkout XX  用于切换分支到XX

git merge 用于合并两个分支
git rebase 也用于合并，“线性”合并分支

git checkout 直接引用
HEAD 是一个对当前检出记录的符号引用

git checkout main^  一个^ 符号表示向父辈移动一位

git reset 本地撤销操作
git revert 共享撤销操作

git cherry-pick 需要复制的节点到当前节点
git rebase -i 从新的图窗人工具体操作




You can use the [editor on GitHub](https://github.com/NoMoreHesitation/NoMoreHesitation.github.io/edit/main/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/NoMoreHesitation/NoMoreHesitation.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
