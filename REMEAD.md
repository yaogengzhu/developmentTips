# 前端开发小技巧
* [开发小技能]()
    * [如何更好的使用.gitignore](#1)

<h2 id="1">如何使用.gitignore</h2>

### 通常我们在使用git工具将自己的代码git到仓库时，经常会遇到一些问题，比如。如何才能将不需要的文件夹去掉？删掉的话十分不方便。但是这个时候，`.gitignore`应运而生，顾名思义，意思就是忽略掉`git`内容。但是如何用好，又是一个问题。

### 在使用`.gitignore`时，必须遵循语法。首先一起来看看语法是什么样的？
- `#` 表示为注释，将被git 忽略
- `*.a` 表示忽略所有的 .a 结尾的文件
- `!lib.a` 表示但lib.a除外的文件
- `/TODO` 表示仅仅忽略项目根目录下的TODO文件，不包括FIile/TODO文件
- `bulid/` 表示忽略bulid目录下所有的文件，包括过滤掉bulid的文件。
- `doc/*.txt` 表示会忽略掉doc/notes.txt的文件。但是不会忽略掉/doc/file/info.txt的文件。
- `bin/:` 表示会忽略掉当前路径下的bin文件夹该文件夹下的所有内容都会被忽略，不忽略bin文件。
- `/bin:` 表示会忽略根目录下的bin文件。
- `/*.c:` 表示会忽略掉cat.c。但是不会忽略buid/cat.c
- `**/foo:` 表示会忽略foo,a/foo,a/b/foo包含foo的文件。
- `a/**/b:` 表示会忽略带掉a/b,a/xxx/b, a/x/y/xxx/b 等文件夹，跟上一个类似，但是指定了那个目录下。
- `!/bin/run.sh` 表示不忽略bin/run.sh 。排除
- `config.php` 表示会忽略掉当前路径下config.php 文件
- `/mtk/` 表示会忽略掉mtk整个文件。
- `*.zip` 表示过滤掉所有的.zip文件。
- `/mtk/doc.c` 表示会忽略掉mtk文件下的doc.c文件

#### 值得注意的是，gitignore过滤掉这些文件之后，当然本地库还有，但是push不会上传到代码仓库。

### `.gitignore`忽略规则查看。
如果发现`.gitignore`写的有问题，但是又不知道哪里出了问题，可以使用`git check-ignore`命令检查。
`$ git check-ignore -v helloWordl.class`
`.gitignore: 1.calss helloWorld.calss` 
#### 看到匹配的内容，我们就可以看到自己哪些是可以被忽略掉的呢。
#### 总结
当然我写的只是`gitignore的基础用法` 原文参考于[点我，查看更多！关注原创,获取更多内容](https://www.cnblogs.com/kevingrace/p/5690241.html)