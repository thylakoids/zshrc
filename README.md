
<!-- vim-markdown-toc GFM -->

1. [zshrc](#zshrc)
    1. [Usefull tool](#usefull-tool)
        1. [pbcopy, pbpaste](#pbcopy-pbpaste)
        1. [synctime](#synctime)
        1. [open](#open)
        1. [trash](#trash)

<!-- vim-markdown-toc -->
# zshrc
## Usefull tool
### pbcopy, pbpaste
- mac
    - pbcopy, pbpaste
- linux
    - alias pbcopy="xclip -selection clipboard"
    - alias pbpaste="xclip -selection clipboard -o"
### synctime
- mac
    - alias synctime="sudo sntp -sS time.apple.com"
- linux
    - alias synctime="sudo ntpdate time.windows.com"
### open
- mac
    - open
- linux
    - alias open="xdg-open  >/dev/null 2>&1"

            /dev/null 表示把输出丢弃，而2>&1 表示把stderr 绑定到stdout
            0 表示stdin, 1 表示stdout, 2表示stderr

    - alias o="xdg-open  2>/dev/null"

### trash
1. `mkdir /tmp/trash_tmp`
2. .zshrc
```bash
function trash{
mv $@ /tmp/trash_tmp
}
```

        $@：表示脚本所有参数的内容；$#：表示返回脚本所有参数的个数。 $$：脚本运行的当前进程ID号

3. `chmod 755 /tmp/trash_tmp`

        chmod命令：
            421 分别代表读、写、执行的权限
            -R 递归处理
        drwxr-xr-x:
            d:file type. '-',file, 'd',folder
            rwx:owner, 7
            r-x:group, 5
            r-x:other, 5
