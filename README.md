# ES2016_14353086
##DOL框架描述
```
The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL  
 allows to specify applications based on the Kahn process network model of computation and features a simulation engine  
 based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation  
 of a parallel application on a multi-processor systems, including binding and mapping.

```

##DOL安装笔记
* 首先创建一个一个名为DOL的文件夹。
    * `mkdir dol`
* 将`dolethz.zip`解压到dol文件中。
    * `unzip dol_ethz.zip -d -dol`
* 进入`dol`文件夹
    * `cd dol`
* 在`systemc-2.3.1`中查看当前的工作路径
	* pwd
* 在文件夹dol中找到`build_zip.xml`这个文件用gedit打开然后找到下面这段话，就是说上面编译的systemc位置在哪里，
```
	<property name="systemc.inc" value="YYY/include"/>
	<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>```
把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，`lib-linux`要改成`lib-linux64`）
* 然后编译这个文件
	* `ant -f build_zip.xml all`
* 等显示build successful的时候打开文件夹dol中的build中的lib中的main中的`runexample.xml`，将找到的
 ```
	<tstamp>
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>
    <touch datetime="${touch.time}">
      <fileset dir="example${number}"/>
    </touch>```

  修改为：

 ```
	<!--     <tstamp>
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>
    <touch datetime="${touch.time}">
      <fileset dir="example${number}"/>
    </touch> -->```
* 在终端打开文件夹dol中的build中的lib中的main。
	* `cd dol/build/lib/main`
* 然后打开runexample.xml查看结果是否为build successful。
	* `sudo ant -f runexample.xml -Dnumber=1`
 ```

##实验感想与实验心得

```
这次实验配置过程中配置dol和仓库的过程出现了很多问题。
1.刚开始的时候忘记更改systemc的当前工作路径，只注意了后面的2.3.1然后就按照ppt上面的打进去就一直报错浪费了很久时间。
2.忘记更改linux为64位。
3.在本机上使用的时候忘记给仓库我的用户名和邮箱，也一直报错。
相对于这些，markdown的使用我觉得也还行，只要看些模板就能使用基本的操作。
