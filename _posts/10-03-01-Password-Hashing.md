---
isChild: true
anchor:  password_hashing
---

## 密码哈希 {#password_hashing_title}

每个人在建构 PHP 应用时终究都会加入用户登录的模块。用户的帐号及密码会被储存在数据库中，在登录时用来验证用户。

It is important that you properly [_hash_][3] passwords before storing them. Password hashing is an irreversible,
one-way function performed against the user's password. This produces a fixed-length string that cannot be feasibly
reversed. This means you can compare a hash against another to determine if they both came from the same source string,
but you cannot determine the original string. If passwords are not hashed and your database is accessed by an
unauthorized third-party, all user accounts are now compromised.

Passwords should also be individually [_salted_][5] by adding a random string to each password before hashing. This prevents dictionary attacks and the use of "rainbow tables" (a reverse list of crytographic hashes for common passwords.)

Hashing and salting are vital as often users use the same password for multiple services and password quality can be poor.

Fortunately, nowadays PHP makes this easy.

**使用 `password_hash` 来哈希密码**

`password_hash` 函数在 PHP 5.5 时被引入。 此函数现在使用的是目前 PHP 所支持的最强大的加密算法 BCrypt 。 当然，此函数未来会支持更多的加密算法。 `password_compat` 库的出现是为了提供对 PHP >= 5.3.7 版本的支持。

在下面例子中，我们哈希一个字符串，然后和新的哈希值对比。因为我们使用的两个字符串是不同的（'secret-password' 与 'bad-password'），所以登录失败。

{% highlight php %}
<?php
require 'password.php';

$passwordHash = password_hash('secret-password', PASSWORD_DEFAULT);

if (password_verify('bad-password', $passwordHash)) {
    // Correct Password
} else {
    // Wrong password
}
{% endhighlight %}

`password_hash()` takes care of password salting for you. The salt is stored, along with the algorithm and "cost", as part of the hash.  `password_verify()` extracts this to determine how to check the password, so you don't need a separate database field to store your salts.

* [了解 `password_hash()`] [1]
* [PHP >= 5.3.7 && < 5.5 的 `password_compat`] [2]
* [了解密码学中的哈希] [3]
* [Learn about salts] [5]
* [PHP `password_hash()` RFC] [4]


[1]: http://php.net/function.password-hash
[2]: https://github.com/ircmaxell/password_compat
[3]: http://en.wikipedia.org/wiki/Cryptographic_hash_function
[4]: https://wiki.php.net/rfc/password_hash
[5]: https://en.wikipedia.org/wiki/Salt_(cryptography)
