# 如何参与项目维护

## 细节过程

- 如果有什么想法，建立 issues, 和我们来讨论。
- 首先点击 右上角的 fork 图标， 把 Seer-For-China fork 到自己的分支 比如我的是 Whisker17/Seer-For-China
- `git clone https://github.com/Whisker17/Seer-For-China.git ./src/github.com/zietgeistpm/Seer-For-China`

- 添加 `zietgeistpm/Seer-For-China` 远端分支： `git remote add upstream https://github.com/zietgeistpm/Seer-For-China.git` 我已经把这个加入了 Makefile 可以直接 运行 `make addupstream`
- 保持 `zietgeistpm/Seer-For-China` 和 `Whisker17/Seer-For-China` main 分支的同步，可以直接跑 `make sync` , 或者执行下面的命令

```
git fetch upstream
git checkout main
git merge upstream/main
注意：不要去修改 main 分支，这样，main 分支永远和upstream/main 保持同步
```

- 从最新的 zietgeistpm/Seer-For-China 建立分支开始修改

```
git fetch upstream
git checkout main
git merge upstream/main
git branch -b "xxx"
```

- 修改完成后, push 到 `Whisker17/Seer-For-China`

```
git fetch upstream
git checkout main
git merge upstream/main
git checkout xxx
git merge main
git push origin xxx
```

然后在界面上进行 pull request

## 简化流程

### 准备阶段

- 首先点击 右上角的 fork 图标， 把 Seer-For-China fork 到自己的分支 比如我的是 Whisker17/Seer-For-China
- `git clone https://github.com/Whisker17/Seer-For-China.git ./src/github.com/zietgeistpm/Seer-For-China`

### 开始修改： 这个分支名称自己设置

```
make branch b=mydevbranchname
```

### 修改完成: push

```
make push b=mydevbranchname m="这个提交的信息"
```

如果 m 不设置，那么不会执行 git commit 的命令

## 修改别人的 pull requset

比如我要修改 name=7uppp branch official-proposal 的 pr

##### step1: 拉取要修改的分支

```
make pull name=7uppp b=official-proposal
```

然后修改代码，修改完成后,并且在本地 commit

###### step2: push 已经修改好的内容

```
make pullpush name=7uppp b=official-proposal
```

