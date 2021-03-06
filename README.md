# 文档自动部署手册
该手册是为了说明如何创建一个可以自动部署的gitbook项目.即接收到提交之后,将gitbook编译为网页并部署至http://115.29.184.56:10000/html

本文档github地址为https://github.com/TSS-Document/DocServerManual

## 环境
1. git
2. npm
2. gitbook
3. 你喜欢的`markdown`编辑器.推荐`atom`或`gitbook editor`

## 步骤
1. 在TssRequirement的<a href="https://github.com/TSS-Document" target="_blank_">organization</a>中创建仓库
2. 本地clone仓库,在 `.git`同级目录执行`gitbook init`
4. 创建.gitignore文件,写入内容
   ```
   /_book
   ```
   >可选,建议这样做,就像maven项目要ignore `/target`一样

3. 创建`styles`文件夹,在其中添加`website.css`文件,内容为

  ```css
    .book .book-summary, .book .book-body,code{
      font-family:"Microsoft YaHei UI",
                  "Microsoft Yahei",
                  "PingFang SC",
                  "Lantinghei SC",
                  "Hiragino Sans GB",
                  "WenQuanYi Micro Hei",
                  "WenQuanYi Zen Hei",
                  "Noto Sans CJK SC",
                  "Microsoft JhengHei UI",
                  "Microsoft JhengHei",
                  "PingFang TC",
                  "Lantinghei TC",
                  "Noto Sans CJK TC",
                  "Helvetica Neue",
                  Helvetica,
                  Arial,
                  sans-serif;
    }
  ```

  >可选,这样做是为了让字体变好看

3. commit and push
4. 约20秒后,http://115.29.184.56:10000/html 中可查看与repository同名的文件夹,点击可查看编译好的网页
5. 若上一步成功,则自动部署配置成功,之后的commit都会触发文档部署
