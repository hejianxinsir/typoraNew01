# 如何使用以下命令
1. ls
2. cat
3. mv
4. touch
5. 如何使用 explainshell.com

### Use ls
ls means 'list',list the file or directory that visible. And yes, you can't see the file hiddened.
> $ ls
> $ ls -a ('a' means 'all', list all the visible file to you)
> $ ls -l (use a long listing format)
> $ ls -al(refer to the upper two explanation)

### Use cat
concatenate files and print on the standard output. When you've editted a file,you can use cat to watch the result.
> cat 1.js

### Use mv
move (rename) files
> $ mv 1.txt 2.txt  (rename)
> $ mv 1.txt 2.txt dir1 (move 1.txt and 2.txt to dir1)

### Use touch
change file timestamps
> $ touch 1.txt (if there is no 1.txt,then creat 1.txt)
> $ touch -t 201905261233.00 1.txt (change 1.txt's timestamps)
> $ touch -r 1.txt 2.txt (set 2.txt's time as 1.txt's time)

### Use explainshell.com
First,enter the website explainshell.com.Input the command you want to know,and explanation is below.

### Another points
<kbd>↑</kbd> <kbd>↓</kbd> 上一命令 / 下一命令
<kbd>!</kbd><kbd>!</kbd> 上一命令占位符
<kbd>Tab</kbd> 自动补全路径
<kbd>Alt</kbd>+<kbd>.</kbd> 上一命令的最后一个参数

&& 前面的执行成功了，再执行后面的
|| 前面的执行失败了，就执行后面的
；前面的执行完了，无论失败与否，就执行后面的
> 重定向。比如 echo hello > 1.txt
| 管道。什么意思？不知道。
