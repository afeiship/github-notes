# what is action
> GitHub Actions 是什么？

## 持续集成(Action)
- 抓取代码
- 运行测试
- 登录远程服务器
- 发布到第三方服务等等。
- GitHub 把这些操作就称为 actions。

## share actions
- 很多操作在不同项目里面是类似的，完全可以共享。
- 如果你需要某个 action，不必自己写复杂的脚本，直接引用他人写好的 action 即可
- 整个持续集成过程，就变成了一个 actions 的组合。

## resources
- https://github.com/marketplace?type=actions

## 引用 action 的方式
```conf
actions/setup-node@74bc508 # 指向一个 commit
actions/setup-node@v1.0    # 指向一个标签
actions/setup-node@master  # 指向一个分支
```
