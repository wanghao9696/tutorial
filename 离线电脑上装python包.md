## 将联网电脑上的python包，安装到未联网的电脑上


1.在互联网电脑上安装我们需要的包
>`pip install ** -i https://pypi.tuna.tsinghua.edu.cn/simple/`

2.在联网电脑执行下面语句
>`pip freeze > requirments.txt`

>>这个时候就会在命令行所在的目录生成一个requirments.txt，这里面列出了联网电脑的包的名字和版本。

3.在联网电脑上下载所有包
>`pip download -r requirments.txt -d "./Desktop/Package" -i https://pypi.tuna.tsinghua.edu.cn/simple/`

>>pip download的命令是从互联网上下载包，其中-r表示依赖包的列表，也就是上一步我们得到的文件，-d后面接着我们想要把包放在那个目录下的文件夹的名字， -i是指定下载源，我们指定了清华源。

>>经过这一步我们在目标文件夹里就得到了很多whl文件

4.把刚才得到的requirments.txt和下载的包复制到离线电脑上

5.在离线电脑上用pip安装下载好的包，执行下面的命令
>`pip install --no-index --find-links=./packages -r dependency.txt`

>>其中`--no-index --find-links=`后面就是我们包所在的文件夹，-r指定的是我们生成的文件