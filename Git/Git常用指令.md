## Git代码回退

```shell
git reset --hard a_commit_id
git reset --soft a_commit_id
git push -f
```

<!--a_commit_id是要回退到的提交的id-->

合并分支配置

```shell
git config pull.rebase false
```

