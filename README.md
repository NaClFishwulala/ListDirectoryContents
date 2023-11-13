# 一、任务：实现"ls -l"的基本功能  
要求:至少能输出  
1.文件类型  
2.9个权限位信息
3.文件大小
4.文件名称

# 二、项目进度  
## 总体规划:  
1.学习stat函数，完成对文件元数据信息的获取：文件名称、文件大小、文件类型、9个权限位信息  
2.学习读目录的基本操作: 打开目录，逐一读出目录项，关闭目录  
3.输出格式:  
FileName: "fileName"  FileType: "fileType"  FilePermission: "filePermission"  FileSize: "fileSize"

FINISH:  
11.9 完成文件名称以及文件大小的获取
11.10 完成文件类型以及9个权限位信息的获取，使用单例设计模式，编写类完成读目录的基本操作:打开目录，逐一读出目录项，关闭目录
11.13 统计当前目录下的文件数量


# 三、知识  
1. 在你的代码中，使用`lstat`而不是`stat`的原因是，当给定的路径是一个符号链接时，`lstat`会返回关于链接本身的信息，而不是它所指向的文件的信息¹。这是因为`lstat()`函数与`stat()`函数相同，除了如果路径名是一个符号链接，那么它返回关于链接本身的信息，而不是它所指向的文件的信息¹。

所以，如果你想要获取的是符号链接本身的信息，而不是它所指向的文件的信息，那么你应该使用`lstat`。如果你使用`stat`，它将会返回符号链接所指向的文件的信息，而不是符号链接本身的信息¹。这就是为什么在你的代码中必须使用`lstat`来获取文件信息的原因。

2. 八进制以数字0开头，十六进制以0x开头