# webstorm设置自动编译LESS
1. 安装less环境
2. npm install less -g
3. 打开webstorm,File=>Setting=>Tools=>FileWatcher
4. 添加Less，参数设置如下：
    1. Pragramm: C:\Users\c-zouzhongxing1\AppData\Roaming\npm\lessc.cmd
    2. Arguments: $FileName$ $FileParentDir$\assets\css\$FileNameWithoutExtension$.css --compress --source-map

# webstorm设置自动编译scss,sass
1. 安装scss环境
2. npm install sass -g
3. 打开webstorm,File=>Setting=>Tools=>FileWatcher
4. 添加Scss，参数设置如下：
    1. Pragramm: C:\Users\c-zouzhongxing1\AppData\Roaming\npm\sass.cmd
    2. Arguments: $FileName$ $FileParentDir$\css\$FileNameWithoutExtension$.css --style=compressed --no-source-map
