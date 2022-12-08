整理我使用过的好工具

## 资源相关

### httrack
输入网站就能自动化地把整个网站资源给爬下来，官网：https://www.httrack.com/

### Prince
根据网络链接把内容爬下来并转换成PDF输出，还可以根据css自定义输出PDF的样式。官网：https://www.princexml.com/

### wkhtmltopdf
将HTML转换成PDF，与Chrome自带转换不同的是他转换出的PDF不仅带目录，而且体积更小，转换速度也更快。官网：https://wkhtmltopdf.org/

```plain
wkhtmltopdf --enable-local-file-access -B 0px -L 0px -R 0px -T 0px [input html name] [output pdf file name]

Tips:
--enable-local-file-access	允许访问本地文件，这样就可以生成包含css样式的PDF文件。
-B	设置底页边距，相当于css中的margin-bottom。
-L	设置左页边距，相当于css中的margin-left。
-R	设置右页边距，相当于css中的margin-right。
-T	设置上页边距，相当于css中的margin-top。
```

## 开发相关

### Hyper Terminal
基于Electron开发的终端，用过的终端很多但他的特殊在于可以自定义样式向终端中文字体这样的他都可以，此外他还有丰富的插件库算是Window平台下我用过最满意的终端工具了。当然，不能和suckless.st比，但已经足够了。

