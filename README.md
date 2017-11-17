# python-demo
python基础教程，由浅入深，一步一步学习python，最后学到的不单单是基础！

## 一、Mac上最简单配置python3开发环境

### 1、安装python3

    首先我们需要先安装python3，这里使用homebrew安装，方便快捷好管理.
    ```javascript
    $ brew install python3
    ```

    安装好后可以尝试输入python3看是否能进入python3命令行，可以看到我这里安装的python3的版本是3.5.2
    ```javascript
    Python 3.5.2 (v3.5.2:4def2a2901a5, Jun 26 2016, 10:47:25)
    [GCC 4.2.1 (Apple Inc. build 5666) (dot 3)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    ```

### 2、Virtualenv

Virtualenv是一个python的虚拟环境，中文也叫虚拟沙盒，就是说它能把项目放在一个虚拟的环境里边，在这个环境里你使用的python版本以及安装的依赖都不会影响环境外的项目.

    安装
    ```javascript
    $ pip install virtualenv
    ```

### 3、创建虚拟环境

    virtualenv 环境名称[自定义] 参数
    参数：
    --no-site-packages package //不依赖已经装好的第三方package，默认会依赖
    可以通过virtualenv --help 查看更多其它参数
    ```javascript
    appledeMacBook-Pro:pythons apple$ sudo virtualenv test_env
    Password:
    New python executable in /Users/apple/Documents/jobs/pythons/test_env/bin/python
    Installing setuptools, pip, wheel...done
    ```

    完成后在当前目录会创建一个test_env的文件夹，进入文件夹会发现生成了以下的目录
    ```javascript
    ├── bin
    ├── include
    │   └── python2.7
    ├── lib
    │   └── python2.7       //所有的新包会被存在这
    │       ├── distutils
    │       ├── encodings
    │       ├── lib-dynload
    │       └── site-packages
    ├── local
    │   ├── bin
    │   ├── include
    │   └── lib
    ```

### 4、启动虚拟环境

    ```javascript
    wwwuser@iZ28u3wd0b6Z:~/test_env$ source ./bin/activate
    (test_env) wwwuser@iZ28u3wd0b6Z:~/test_env$
    ```
    启动成功后，会在前面多出test_env字样
    输入pip list查看项目依赖

    ```javascript
    (test_env) wwwuser@iZ28u3wd0b6Z:~/test_env$ pip list
    pip (8.0.2)
    setuptools (19.6.1)
    wheel (0.26.0)$
    ```
    可以发现沙箱确实已经是一个单独的环境了

### 5、退出虚拟环境

    ```javascript
    deactivate
    ```

### 6、搭建python3项目

    使用--python参数指定python版本创建一个基于python3的虚拟环境
    ```javascript
    $ sudo virtualenv -p python3 py3_test
    ```
    检查环境中python版本，可以发现虚拟环境中的python版本已经是python3啦，好啦，这样即大功告成！