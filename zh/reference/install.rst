安装
============

PHP扩展到传统的基于php的库或框架需要一个稍微不同的安装方法。你可以下载一个与您的操作系统匹配的二进制包或从源来构建。

在过去的几个月中，我们已经广泛地研究了PHP的行为，为显着的优化（大或小）进行研究（investigating areas for significant optimizations (big or small)）。通过对Zend引擎的理解，我们设法消除不必要的验证，压缩代码，进行优化和在底层提供解决方案，从而使Phalcon达到最大性能。

.. highlights::
   Phalcon编译自PHP5.3.1，但由于原有的PHP错误会导致内存泄漏，我们强烈建议您至少使用PHP5.3.11或更高。


Windows
-------

在windows上安装任何扩展都是很简单的，安装phalcon也是一样，下载.dll文件，放到extension目录，然后修改php.ini文件，加入以下行：

    extension=php_phalcon.dll

重启web server.

以下视频是教你如何一步一步在windows上安装phalcon

.. raw:: html

   <div align="center"><iframe src="http://player.vimeo.com/video/40265988" width="500" height="266" frameborder="0" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe></div>

Related Guides
^^^^^^^^^^^^^^

.. toctree::
   :maxdepth: 1

   xampp
   wamp

Unix/Linux
----------

在Unix/Linux操作系统上，你可以很容易的从源代友编译和安装扩展

Requirements
^^^^^^^^^^^^
Prerequisite packages are:

* PHP 5.x development resources
* GCC compiler (Linux) or Xcode (Mac)
* Git (if not already installed in your system - unless you download the package from GitHub and upload it on your server via FTP/SFTP)

.. code-block:: bash

    #Ubuntu
    sudo apt-get install php5-dev php5-mysql gcc
    sudo apt-get install git-core

    #Suse
    yast2 -i php5-pear php5-dev php5-mysql gcc
    yast2 -i git-core

Compilation
^^^^^^^^^^^
Creating the extension:

.. code-block:: bash

    git clone git://github.com/phalcon/cphalcon.git
    cd cphalcon/build
    ./install

（译者备注）./install其实是默认包含了phpize,configure,make,make install命令。如果您的机器中phpize,php-config不在环境命令中，请执行以下操作后再执行./install

.. code-block:: bash

   ln -s phpdir/bin/phpize /usr/bin
   ln -s phpdir/bin/php-cofnig /usr/bin

phpdir是你的php安装路径。

编辑php.ini文件，加入扩展

.. code-block:: bash

    extension=phalcon.so

重启web server,如果是php-fpm,重启php-fpm即可

FreeBSD
^^^^^^^
A port is available for FreeBSD. Just only need these simple line commands to install it:

.. code-block:: bash

    pkg_add -r phalcon

or

.. code-block:: bash

    export CFLAGS="-O2 -fno-delete-null-pointer-checks"
    cd /usr/ports/www/phalcon && make install clean

Installation Notes
^^^^^^^^^^^^^^^^^^

Installation notes for Web Servers:

.. toctree::
   :maxdepth: 1
   
   apache
   nginx

