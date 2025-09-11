运行网页：
```bash
bundle install
bundle exec jekyll serve
```

你必须在 master 分支构建网站后，再把 _site 的内容复制到 gh-pages 分支：
```bash
# 在 master 分支
bundle install
bundle exec jekyll build

# 切换到 gh-pages
git checkout gh-pages

# 删除旧文件（如果有）
git rm -rf .

# 回到 master 分支拷贝 _site
git checkout master -- _site

# 拷贝 _site 内容到 gh-pages 根目录
cp -R _site/* .

# 添加、提交、推送
git add .
git commit -m "Deploy Jekyll site to gh-pages"
git push origin gh-pages

# 回到 master 分支
git checkout master
```

