# 使用 Git 命令将本地仓库上传至 GitHub 教程


<hr>

* ### 本地仓库上传至GitHub（新仓库）
``` 

    echo "# Test" >> README.md

    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin https://github.com/JinghuiChan/Test.git
    git push -u origin master

```

* ### 本地仓库上传至GitHub（有内容）
```
    git init
    git pull origin master
    git add *
    git commit -m "first commit"
    git remote add origin https://github.com/JinghuiChan/Test.git
    git push -u origin master
```
