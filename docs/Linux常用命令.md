### 一、文件目录操作

#### ls 命令

ls 命令不仅可以查看Linux文件夹包含的文件而且可以查看文件权限（包括目录、文件夹、文件权限）、目录信息等等。

##### 命令格式

ls [选项] [目录名]

##### 常用参数

- -l：列出长数据串，包含文件的属性与权限数据等；

- -a：列出全部的文件，联通隐藏文件（开头为.的文件）一起列出来（常用）；

- -d：仅列出目录本身，不列出文件目录的文件数据；

- -h：将文件容量以较易读的方式（GB、KB等）列出来；

- -R：连同子目录的内容一起列出（递归列出），等于该目录下的所有文件都会显示出来；

##### 使用举例

1. 列出home目录下的所有文件和目录的详细信息
   
   ```textile
   ls -a -l /home
   ls -al /home
   ```

2. 列出当前目录下所有以"d"开头的文件目录详情内容
   
   ```textile
   ls -l d*
   ```

#### cd 命令

用于切换（跳转）当前目录至目标目录。

##### 命令格式

cd [目录名]

##### 使用举例

1. 从当前目录进入系统根目录。
   
   ```textile
   cd /
   ```

2. 跳转到home/test 目录。
   
   ```textile
   cd /home/test
   ```

#### pwd 命令

查看"当前工作目录"的完整路径。

##### 命令格式

pwd [选项]

##### 常用参数

- -P：显示实际物理路径，而非使用连接（link）路径；

- -L：当前目录为连接路径时，显示连接路径；

##### 使用举例

1. 显示当前目录所在的路径
   
   ```textile
   pwd
   ```

#### mkdir 命令

用来创建指定名称的目录，要求创建目录的用户在当前目录中具有写权限，并且指定的目录名不能是当前目录中已有的目录。

##### 命令格式

mkdir [选项] 目录名

##### 常用参数

- -m：--mode，设定权限《模式》（类似于chmod），而不是rwxrwxrwx减umask；

- -p：--parents，可以是一个路径名称。此时若路径中的某些目录尚不存在，加上此选项后，系统将自动建立好那些尚不存在的目录，即一次可以创建多个目录；

- -v：--verbose，每次创建新目录都显示信息；

- --help：显示此帮助信息并退出；

- --version：显示版本信息并退出；

##### 使用举例

1. 创建一个 test 空目录
   
   ```textile
   mkdir test
   ```

2. 递归创建多层（多个）目录
   
   ```textile
   mkdir test/test1
   ```

3. 创建权限为777的目录
   
   ```textile
   mkdir -m 777 test2
   ```

4. 创建目录都显示信息
   
   ```textile
   mkdir -v test3
   ```

#### rm 命令

删除一个目录中的一个或多个文件或目录，如果没有使用-r选项，则rm不会删除目录。如果使用rm来删除文件，通常可以将改文件恢复原状。

##### 命令格式

rm [选项] 文件名(目录名)

##### 常用参数

- -f：--force，忽略不存在的文件，从不给出提示；

- -i：--interactive，进行交互式删除；

- -r：-R，--recursive，提示rm将参数中列出的全部目录和子目录均递归删除。

- -v：--verbose，详细显示进行的步骤；

- --help：显示此帮助信息并退出；

- --version：显示版本信息并退出；

##### 使用举例

1. 删除文件test.txt，系统会提示是否删除
   
   ```textile
   rm test.txt
   ```

2. 强制删除test.txt，系统不会再提示
   
   ```textile
   rm -f test.txt
   ```

3. 将test目录及目录中所有档案删除
   
   ```textile
   rm -r test
   ```

#### rmdir 命令

该命令从一个目录中删除一个或多个子目录项，删除某目录时也必须具有对父目录的写权限。

##### 命令格式

rmdir [选项] 目录名

##### 常用参数

- -p：递归删除目录，当子目录删除后其父目录为空时，也一同被删除。如果整个路径被删除或者由于某种原因保留部分路径，则系统在标准输出上显示相应的信息；

- -v：--verbose，显示指令执行的过程；

##### 使用举例

1. 删除空目录test1，非空目录无法删除。
   
   ```textile
   rmdir test1
   ```

2. 当子目录被删除后使它也成为空目录的话，则顺便一并删除。
   
   ```textile
   rmdir -p test2
   ```

#### mv 命令

可以用来移动文件或者将文件重命名。当第二个参数类型是文件时，mv命令完成文件重命名。当第二个参数是已存在的目录名称时，源文件或目录参数可以有多个，mv命令将各参数指定的源文件均移至目标目录中。

##### 命令格式

mv [选项] 源文件或目录 目标文件或目录

##### 常用参数

- -b：若需覆盖文件，则覆盖前先行备份。

- -f：force强制的意思，如果目标文件已存在，不会询问而是直接覆盖。

- -i：若目标文件已经存在时，就会询问是否覆盖。

- -u：若目标文件已经存在，且source比较新，才会更新。

- -t：--target-directory=DIRECTORY move all SOURCE arguments into DIRECTORY，即指定mv的目标目录，该选项适用于多个源文件到一个目录的情况，此时目标目录里在前，源文件在后。

##### 使用举例

1. 将test.txt重命名为test1.txt
   
   ```textile
   mv test.txt test1.txt
   ```

2. 移动文件test1.txt到目录test2下
   
   ```textile
   mv test1.txt test2
   ```

3. 将文件test1.txt、test2.txt、test3.txt移动到目录test3下
   
   ```textile
   mv test1.txt test2.txt test3.txt test3
   ```

#### cp 命令

将源文件复制到目标目录，或将多个源文件复制到目标目录下。

##### 命令格式

cp [选项] 源文件 目录 或 cp [选项] -t 目录 源文件

##### 常用参数

- -t：--target-directory，指定目标目录。

- -i：--interactive，覆盖前询问（使前面的 -n 选项失效）。

- -n：--no-clobber，不要覆盖已存在的文件（使前面的 -i 选项失效）。

- -f：--force，强行复制文件或目录，不论目标文件或目录是否已存在。

- -u：--update，使用这个参数后，只会在源文件的修改时间比目的文件的更新时间更新时，或是对应的目的文件并不存在，才会复制文件。

##### 使用举例




