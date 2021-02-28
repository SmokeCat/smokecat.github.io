# screen 使用笔记

## 安装

```shell
sudo apt install screen
```

## 使用

### 查看 screen 绑定的命令

> 快捷键需要在 screen 中执行

```
<C-a> ?
```

### 创建并进入一个 screen

```shell
# 创建一个名为<pid>.<tty>.<host>的screen并进入
$ screen
```

### 创建指定 sockname 的 screen 并进入

```shell
# 创建一个名为<pid>.<sockname>的screen并进入
$ screen -S <sockname>
```

### 断开 screen 连接(screen 后台运行)

```shell
$ screen -d
```

```
<C-a> <C-d>
or
<C-a> d
```

### 列出所有 screen

```shell
$ screen -ls
```

### 恢复指定 screen 连接

```shell
$ screen -r [pid.tty.host]|[sockname]

# 恢复可用的 screen(只有一个 detached 的 screen 时)
$ screen -R
```

### kill screen

```shell
# 未连接 screen 时

# 查看所有screen进程
$ screen -ls

# 执行退出进程命令
$ screen -X -S [指定screen] quit

# 清除sockdir目录
$ screen -wipe
```

```
# quit: 关闭所有 window 并终止 screen
<C-a> \

# kill: 关闭当前 window
<C-a> k
or
<C-a> <C-k>
```

### 共享 screen

```shell
$ screen -x [指定screen]
```

### 清屏

```
<C-a> C
```

### 创建 window

```
<C-a> c
or
<C-a> <C-c>
```

### 命名当前 window

```
<C-a> A
```

### 列出所有 window

```
<C-a> "
or
<C-a> w
or
<C-a> <C-w>
```

### 切换 window

```
# 提示输入需要切换到的 window
<C-a> '

# 切换到指定 window
<C-a> [num]

# 切换到上一次使用的 window
<C-a> <C-a>

# 切换到下一个 window
<C-a> <Space>
<C-a> n
<C-a> <C-n>

# 切换到上一个window
<C-a> <Backspace>
<C-a> <C-h>
<C-a> p
<C-a> <C-p>
```

### 分屏

```
# 新分屏无可用的东西，需要用 <C-a> c 创建一个wondow

# 垂直分屏
<C-a> |
# 水平分屏
<C-a> S
```

### 切换分屏

```
<C-a> <Tab>
```

### 关闭分屏

```
# 关闭当前分屏
<C-a> X

# 关闭除了当前所在之外的所有分屏
<C-a> Q
```
