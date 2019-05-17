# uglifyjs压缩JS
## 安装uglifyjs
> npm install uglify-js -g
## 使用方法
> uglifyjs a.js -m -c -o a.min.js
> PS:-m混淆，-C压缩，-o输出 
## 参数说明
````   Usage: uglifyjs [options] [files...]
  
    Options:
  
      -V, --version                            output the version number
      -p, --parse <options>                    Specify parser options.
      -c, --compress [options]                 Enable compressor/specify compressor options.
      -m, --mangle [options]                   Mangle names/specify mangler options.
      --mangle-props [options]                 Mangle properties/specify mangler options.
      -b, --beautify [options]                 Beautify output/specify output options.
      -o, --output <file>                      Output file (default STDOUT).
      --comments [filter]                      Preserve copyright comments in the output.
      --config-file <file>                     Read minify() options from JSON file.
      -d, --define <expr>[=value]              Global definitions.
      -e, --enclose [arg[,...][:value[,...]]]  Embed everything in a big function, with configurable argument(s) & value(s).
      --ie8                                    Support non-standard Internet Explorer 8.
      --keep-fnames                            Do not mangle/drop function names. Useful for code relying on Function.prototype.name.
      --name-cache <file>                      File to hold mangled name mappings.
      --rename                                 Force symbol expansion.
      --no-rename                              Disable symbol expansion.
      --self                                   Build UglifyJS as a library (implies --wrap UglifyJS)
      --source-map [options]                   Enable source map/specify source map options.
      --timings                                Display operations run time on STDERR.
      --toplevel                               Compress and/or mangle variables in toplevel scope.
      --verbose                                Print diagnostic messages.
      --warn                                   Print warning messages.
      --wrap <name>                            Embed everything as a function with “exports” corresponding to “name” globally.
      -h, --help                               output usage information
````
      
## 以下内容来自张鑫旭：
[https://www.zhangxinxu.com/wordpress/2013/01/uglifyjs-compress-js/]
### 生成批处理:
```` @echo off
 :: 设置压缩JS文件的根目录，脚本会自动按树层次查找和压缩所有的JS
 SET JSFOLDER=C:\Users\Administrator\Desktop\formini
 echo 正在查找JS文件
 chdir /d %JSFOLDER%
 for /r . %%a in (*.js) do (
      @echo 正在压缩 %%~a ...
      uglifyjs %%~fa  -m -o %%~fa
  )
  echo 完成!
  pause & exit
````
