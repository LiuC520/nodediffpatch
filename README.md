# nodediffpatch
#### 这是一个node命令，有两个命令可用，一是用于生成补丁文件，一个是合并补丁生成新的文件.

##### 很多情况下我们需要生成补丁文件，例如 react native 的热更新，自建服务器进行热更新，不用codepush和pushy，需要生成bundle的补丁文件，然后在手机上合并。

### 下载操作：
##### 1、我利用的是google的diff文件，下载地址为：[https://code.google.com/archive/p/google-diff-match-patch/downloads](https://code.google.com/archive/p/google-diff-match-patch/downloads)
##### 2、但是上面的官方地址需要科学上网，我的网站下载地址：[www.vr-react.com/file/diff_match_patch_20121119.zip](www.vr-react.com/file/diff_match_patch_20121119.zip)

##### 3、打开本地终端，输入  git clone https://github.com/LiuC520/nodediffpatch.git
##### 4、然后输入  cd nodediffpatch && npm i
##### 5、然后把你要生成的新、旧文件放到nodediffpatch的patch文件夹下，然后就可以用命令生成补丁了
### 命令如下：
###### 下面的 l1.txt 是旧文件，l2.txt 是新文件，只需要换成你自己的就行了
> 1、patbundle patch -o l1.txt -n l2.txt 
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这是生成补丁的命令
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;其中l1.txt是你的旧文件，l2.txt是新文件，需要把文件的后缀也带上哦,
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;假设你的旧文件为 index.android.bundle,新文件为 new.bundle,
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;命令行就是： patbundle patch -o index.android.bundle -n new.bundle
>2、patbundle merge -o l1.txt -p patches.pat -n newfile.txt
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;也可以简写的哦：patbundle merge -o l1.txt -p patches.pat ，这样的话新的文件名就是 newl1.txt
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;也可以简写的哦：patbundle merge -o l1.txt ，这样的话新的文件名就是 newl1.txt，默认的pat文件就是patches.pat
##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这就是把l1.txt和pat文件合并成一个新的文件