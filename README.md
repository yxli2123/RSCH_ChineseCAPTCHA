# ChineseCAPTCHA

## 说明

从 mainMode0.py 或者 mainMode1.py 运行

他们都是同一个文件，只是文件中的mode变量取值不同

字体文件夹为font，背景图片文件夹为backgroundImage，注意不要改变文件夹的名字和结构

调整训练样本数目请打开，更改for循环中的迭代数目，这里设置成10，最大可以100000（也可以更大，但请自行修改图片命名的代码）

## Mode0 生成图片验证码

背景图片被resized到200\*200，上面随机摆放四个汉字，汉字大小为26piexl左右

随机的意思是：汉字的位置是随机的，但尽量不重叠；汉字的字体是随机的；汉字的颜色是深色随机的；汉字的旋转是随机角度；图片背景是随机的。

![Image example](/image/00000.png)

标签生成在本目录下的pos.csv文件中

| |string|left0|top0|right0|bottom0|left1|top1|right1|bottom1|left2|top2|right2|bottom2|left3|top3|right3|bottom3|
|-|------|-----|----|------|-------|-----|----|------|-------|-----|----|------|-------|-----|----|------|-------|
|0|忆时块山|60|17|92|49|22|148|54|180|138|108|170|140|113|141|145|173|

top, left, right, bottom 表示这个汉字的位置，是这个汉字的边框，后缀0～3表示第对应汉字。

## Mode1 生成文本验证码

生成160\*40的长框，框内有浅色背景和杂乱的条纹。随机生成文字，从左到右排布。

同样，汉字的字体是随机的；汉字的颜色是深色随机的；汉字的旋转是随机角度。

![Image example](/textImage/00000.png)

标签生成在本目录下的textImageLabel.txt中

顺序排列生成的字符串，之间用换行符隔开。

## 注意

python文件鲁棒性不高，运行前，自行添加Image目录和textImage目录

不要更改目录结构
