# ES2016_14353086
##DOL框架描述
```
qaq
```

##DOL安装笔记
* 首先创建一个一个名为DOL的文件夹。
	* mkdir dol
* 将`dolethz.zip`解压到dol文件中。
	* unzip dol_ethz.zip -d -dol
* 进入dol文件夹
	* cd dol
* 在systemc-2.3.1中查看当前的工作路径
	* pwd
* 在文件夹dol中找到build_zip.xml这个文件用gedit打开然后找到下面这段话，就是说上面编译的systemc位置在哪里，
	<property name="systemc.inc" value="YYY/include"/>
	<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）
* 然后编译这个文件
	* ant -f build_zip.xml all
* 等显示build successful的时候打开文件夹dol中的build中的lib中的main中的runexample.xml，将找到的
 ```<tstamp>
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>
    <touch datetime="${touch.time}">
      <fileset dir="example${number}"/>
    </touch>```

修改为：
```<!--     <tstamp>
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>
    <touch datetime="${touch.time}">
      <fileset dir="example${number}"/>
    </touch> -->```


##实验感想与实验心得
????


