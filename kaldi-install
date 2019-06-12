Kaldi可在多种系统下安装，这里是在Ubuntu16.04环境下安装的，分为本地安装（有root权限）和在服务器安装（无root权限）两种不同的情况进行安装。

一、本地安装

先安装git版本控制软件

sudo apt-get install git

从github上下载最新的Kaldi框架

git clone https://github.com/kaldi-asr/kaldi.git kaldi-trunk --origin golden

在安装Kaldi框架前先下载以下组件，都可使用sudo apt-get install命令下载

sudo apt-get install subversion,automake,autoconf,libtool,zlib,wget,libatal

安装完成后进入Kaldi的tools目录进行编译

cd kaldi-trunk/tools
make 或 make -j4(多核并行)

编译完成后进入src框架，分两步进行配置

./configure

make 或 make all

如果安装过程中报错，若是缺少组件根据提示安装对应的组件即可，若是缺少mkl矩阵库，需要到Intel官网下载MKL，并默认安装到/opt目录下或者在执行./configure时执行./configure --mathlib=OPENBLAS文件，将默认矩阵运算库改为openblas。这是我遇到过的问题，如果还遇到其他问题可自行百度解决。

二、服务器安装

从服务器端安装Kaldi没有root权限，因此无法使用sudo apt-get install命令按照组件，所以需要安装anaconda虚拟环境，安装过程可参考 https://blog.csdn.net/ITBigGod/article/details/85690257
安装完毕后，使用conda create 命令新建环境，如

conda create -name kaldi python3

然后激活环境

source activate kaldi

接着就可以进行Kaldi框架的安装，从github上下载最新的Kaldi框架

git clone https://github.com/kaldi-asr/kaldi.git kaldi-trunk --origin golden

在安装Kaldi框架前先下载以下组件，使用conda install命令下载，如果有出现安装问题，可百度对应组件在anaconda下的对应安装命令

conda install subversion,automake,autoconf,libtool,zlib,wget,libatal

安装完成后进入Kaldi的tools目录进行编译

cd kaldi-trunk/tools
make 或 make -j4(多核并行)

编译完成后进入src框架，分两步进行配置

 ./configure --mathlib=OPENBLAS

make 或 make all

如果安装过程中报错，若是缺少组件根据提示安装对应的组件即可，由于没有root权限无法安装默认矩阵运算库MKL，因此将默认矩阵运算库改为openblas。安装过程中若出现问题，可根据提示进行百度解决。
