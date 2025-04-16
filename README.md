
项目基于[MKdocs](https://www.mkdocs.org/)，主题为[MateriaL](https://squidfunk.github.io/mkdocs-material/)。

项目开设于 2025 年 2 月 21 日

## 部署相关问题

要让 GitHub 部署这个网页要再 `setting` （设置）中的 `page` （页面）中将 `Build and deployment` (构建与部属) - `Source` （来源）改为 `Deploy from a branch` （从分支部署）

`Branch` （分支）选择 `gh-page` - `/(root)` ，然后 `save` （保存）就好了

原因是因为我在 [GitPage.yml](./.github/workflows/GitPage.yml) 中设置了将 mackdocs提交到仓库后进行自动编译，将编译后的文件自动上传到 gh-page 分支，这时只需要将 gitpage 页面指定到这个分支页面就可以显示了