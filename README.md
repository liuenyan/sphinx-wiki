# sphinx-wiki

一个使用 [sphinx](http://www.sphinx-doc.org/) 生成的静态 wiki 。

## 分支说明

sphinx-wiki 使用两个分支来存储文件。

1. master 分支用于存储 reStructuredText 源文件和 sphinx 配置文件。
2. gh-pages 分支保存由 sphinx 生成的网页。

## 静态网页生成步骤

1. 在 master 分支上使用 reStructuredText 语法编辑源文件，保存为以 rst 结尾的源文件。

2. 执行 make html 命令，生成的网页源代码保存在 \_build/html 目录中。

3. 切换到 \_build/html 目录，执行 `python3 -m http.server` 运行 http 服务器，在浏览器中打开 http://127.0.0.1:8000/ 预览生成的网页。

4. 使用 [ghp-import](https://github.com/davisp/ghp-import) 导出\_build/html 目录到 gh-pages 分支。注意一定要使用 -n 参数来生成.nojekyll 文件。

   `ghp-import -n _build/html/`

5. 分别 push master 分支和 gh-pages 分支到 github 。
