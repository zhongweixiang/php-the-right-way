---
isChild: true
anchor:  opcode_cache
---

## Opcode 缓存 {#opcode_cache_title}

<<<<<<< HEAD
当一个 PHP 文件被解释执行的时候，首先是被编译成名为 [opcodes](http://php.net/manual/en/internals2.opcodes.php) (machine language instructions for the CPU)
如果PHP文件没有被修改过，opcode 始终是一样的。这就意味着编译步骤白白浪费了 CPU 的资源。

此时 opcode 缓存就派上用场了。通过将 opcode 缓存在内存中，它能防止冗余的编译步骤，并且在下次调用执行时得到重用。It will typically check signature or modification time of the file first, in case there have been any changes.

It's likely an opcode cache will make a significant speed improvement to your application.  Since PHP 5.5 there is one built in - [Zend OPcache][opcache-book]. Depending on your PHP package/distribution, it's usually turned on by default - check [opcache.enable](http://php.net/manual/en/opcache.configuration.php#ini.opcache.enable) and the output of `phpinfo()` to make sure. For earlier versions there's a PECL extension.

Read more about opcode caches:

* [Zend OPcache][opcache-book] (bundled with PHP since 5.5)
* Zend OPcache (formerly known as Zend Optimizer+) is now [open source][Zend Optimizer+]
* [APC] - PHP 5.4 and earlier
* [XCache]
* [WinCache] (extension for MS Windows Server)
* [list of PHP accelerators on Wikipedia][PHP_accelerators]


[opcache-book]: http://php.net/book.opcache
[APC]: http://php.net/book.apc
[XCache]: http://xcache.lighttpd.net/
[Zend Optimizer+]: https://github.com/zendtech/ZendOptimizerPlus
[WinCache]: http://www.iis.net/download/wincacheforphp
[PHP_accelerators]: http://en.wikipedia.org/wiki/List_of_PHP_accelerators
