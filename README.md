该仓库仅包含repo xml，适用 **tiny4412 project**，由韦东山学员自行组织，对4412进行系统性深入学习并分享。

项目链接 http://wiki.100ask.org/Tiny4412

# 集成环境
当前使用buildroot进行系统集成，考虑uboot/kernel等代码仓库较多，不方便进行切换，故而使用repo进行管理。

# 下载repo工具
根据您的办公网络情况，获取repo工具。
```
$ git clone  https://git.dev.tencent.com/codebug8/repo.git
$ sudo cp repo/repo /bin/
```

# repo init
新建目录存放仓库
```
$ mkdir -p tiny4412 && cd tiny4412
$ repo init -u https://github.com/tinylaker/manifest -m default.xml --no-repo-verify
```
```
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 1), reused 5 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), done.
From https://github.com/tinylaker/manifest
 * [new branch]      master     -> origin/master

If you want to change this, please re-run 'repo init' with --config-name

repo has been initialized in /work/tiny4412
```
# repo sync

```
$ repo sync -j4
From https://github.com/TinyWindzz/tiny4412_uboot_2018_07B/s
 * [new branch]      master     -> github/master
Fetching projects:  75% (6/8)
remote: Total 55652 (delta 28), reused 41 (delta 23), pack-reused 55601
Receiving objects: 100% (55652/55652), 147.79 MiB | 744 KiB/s, done.
Resolving deltas: 100% (4475/4475), done.
From https://github.com/zczjx/linux-4.4.38-for-tiny44125 MiB/s
 * [new branch]      master     -> github/master
Fetching projects:  87% (7/8)
remote: Total 66325 (delta 5015), reused 66325 (delta 5015), pack-reused 0
Receiving objects: 100% (66325/66325), 178.20 MiB | 1.35 MiB/s, done.
Resolving deltas: 100% (5015/5015), done.
From https://github.com/TinyWindzz/linux-4.20
 * [new branch]      master     -> github/master
Fetching projects: 100% (8/8)
Fetching projects: 100% (8/8), done.
Checking out files: 100% (62468/62468), done.
Checking out files: 100% (52228/52228), done.es:  35% (18672/52228)
Syncing work tree: 100% (8/8), done.
```
# 代码目录
查看下载好的源码目录
```
$ ls 
buildroot  firmware  kernel  test  uboot
$ ls kernel/ uboot/ test/
kernel/:
linux-4.20  linux-4.4.38

test/:
bsp  lib

uboot/:
uboot-2010.12  uboot-2018.07
```
