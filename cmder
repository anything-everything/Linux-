官网: http://cmder.net/

就像它自己说的，它将 conemu，msysgit 和 clink 打包在一起，让你无需配置就能使用一个真正干净的 Linux 终端！还附带了漂亮的 monokai 配色主题。作为一个压缩档的存在, 可即压即用。你甚至可以放到 USB 就可以随时带着走，连调整过的设定都会放在这个目录下，不会用到系统机码(Registry)，所以也很适合放在 Dropbox / Google Drive / OneDrive 共享于多台电脑。

Install

下载的时候，会有两个版本，分别是 mini 与 full 版；唯一的差别在于有没有内建 msysgit 工具，这是 Git for Windows 的标准配备；全安装版 cmder 自带了 msysgit, 除了 git 本身这个命令之外, 里面可以使用大量的 linux 命令；比如 grep, curl(没有 wget)； 像 vim, grep, tar, unzip, ssh, ls, bash, perl 对于爱折腾的 Coder 更是痛点需求。

下载完成后，解压到某个目录直接运行就可以了。

Configue

配置环境变量
系统变量添加：

Key:  CMDER_HOME
Value:  absolute path //cmder的解压路径
PATH 添加   %CMDER_HOME%

添加到右键菜单：

win + x 再 a 以管理员身份打开cmd

执行

Cmder.exe /REGISTER ALL

修改lamd提示符为$

将一下目录的文件进行修改：cmder\vendor\clink.lua文件中第41行中{lamb}修改为$

修改前：local cmder_prompt = "\x1b[1;32;40m{cwd} {git}{hg} \n\x1b[1;30;40m{lamb} \x1b[0m"

修改后：local cmder_prompt = "\x1b[1;32;40m{cwd} {git}{hg} \n\x1b[1;30;40m$ \x1b[0m"

修改成功
