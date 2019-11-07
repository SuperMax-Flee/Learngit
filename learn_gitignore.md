#<center>gitignore学习(过滤不想推送的内容)</center>  

---
&emsp;我们知道在一个本地库中,我们每一次推送都会把所有已经被Track的文件或者文件夹推送到远程库,但现实中往往很多的文件的内容不想让别人看到,比如SSH或者一些配置文件等,这时候我们就要用到Git的过滤方法之一配置.gitignore<br>

     
1. 首先我们要新建一个.gitignore文件,这个文件在我们初始化库的时候,不会被自动生成.
2. 比如我有个secret的文件不想在Push的时候把内容推送上去,那么首先我们要把这个文件加入到.gitignore的文件中
```
cat .gitignore
secret
```

    这里注意的是,针对不同情况有不同的过滤规则,比如要过滤掉是所有.txt文件,则我们要写*.txt,再比如要过滤到某个文件夹用xxx/

3. 接下来我们要把.gitignore文件加入到版本库
4. 完成提交之后,要修改config配置文件了(在.git文件夹里),加入下面代码
`git config code.excludesfile.gitignore`
跟刚安装好配置用户名和邮箱是一样的.
---
完成以上操作,我们就可以推送到远程库了.
PS.这边如果想要过滤的文件已经被Track了,则要先恢复成未被Track状态.用以下代码可以恢复
`git rm -f --cached file`

