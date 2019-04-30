# Linux

### 一、常用查看命令

- pwd：显示当前所在路径
- ls -l ：显示文件和目录详细资料
- ls -F：查看目录中的文件
- ls -a：显示隐藏文件
- tree：显示文件和目录由根目录开始的树形结构
- lstree： 显示文件和目录由根目录开始的树形结构

### 二、常用操作命令

- mkdir  dir1：创建叫dir1的目录，可以多个dir1 dir2
- mkdir -p /dir1/dir2：目录树
- rm -f file：删除file的文件
- rmdir dir：删除dir目录
- rm -rf dir1：删除dir1并删除其内容，可多个dir1 dir2 
- mv dir1 new_dir： 重命名/移动 一个目录 
- cp file1 file2： 复制一个文件 ，可以路径

### 三、压缩解压

- bunzip2  file1.bz2：解压一个叫做file1.bz2的文件
- bzip2 file ：压缩file文件
- gunzip file1.gz：解压file1.gz
- gzip file：压缩file
- gzip -9 file：最大程度压缩file
- rar a file1.rar  test_file：创建file1.rar的包
- rar a file1.rar file1 file2 dir1 同时压缩 'file1', 'file2' 以及目录 'dir1' 
- rar x file1.rar 解压rar包 
- unrar x file1.rar 解压rar包 
- unzip file1.zip 解压一个zip格式压缩包 
- zip file1.zip file1 创建一个zip格式的压缩包 
- zip -r file1.zip file1 file2 dir1 将几个文件和目录同时压缩成一个zip格式的压缩包 

### 四、查看文件内容

- cat file1 从第一个字节开始正向查看文件的内容 
- tac file1 从最后一行开始反向查看一个文件的内容 
- more file1 查看一个长文件的内容 
- less file1 类似于 'more' 命令，但是它允许在文件中和正向操作一样的反向操作 
- head -2 file1 查看一个文件的前两行 
- tail -2 file1 查看一个文件的最后两行 
- tail -f /var/log/messages 实时查看被添加到一个文件中的内容 

























