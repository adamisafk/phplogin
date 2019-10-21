# Another PHP MySQL Login System
## but this time with design patterns!

### This project was initially built off of this tutorial:
https://codeshack.io/secure-login-system-php-mysql/

### Description
A PHP MySQL system featuring a login, logout, and user dependant page content. This implementation of a login system is part of my assignment where I will be showcasing various implementations of design patterns where appropriate.

### How to Use
Using a LAMP stack (can be XAMPP or custom), locate your htdocs file in your apache2 directory. For me using Linux XAMPP; this is /opt/lampp/(apache2)/htdocs. In Windows, the default installation is in the C:/ drive (I think).

Clone this project to htdocs, create a new a database called 'phplogin' then execute the following SQL statement:

```
CREATE TABLE IF NOT EXISTS `accounts` (
	`id` int(11) NOT NULL AUTO_INCREMENT,
  	`username` varchar(50) NOT NULL,
  	`password` varchar(255) NOT NULL,
  	`email` varchar(100) NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;

INSERT INTO `accounts` (`id`, `username`, `password`, `email`) VALUES (1, 'test', '$2y$10$SfhYIDtn.iOuCW7zfoFLuuZHX6lja4lF4XA4JqNmpiH/.P3zB8JCa', 'test@test.com');
```

The above statement will create a new accounts table with a primary id, username, password, and email. A sample account is also inserted, the username is 'test' and the unencrypted password is 'test'.

Changing any database or table name will result in changing the sql connection parameters in authenticate.php and profile.php.

Next, simply load the index.html page in a browser. If apache is local, use the URL [localhost/phplogin/index.html](localhost/phplogin/index.html)


### To Do:

- [ ] Use Observer pattern to log all access to the site. Can be logged to the database or emailed to an admin. Must be flexible enough to support different login systems.
- [ ] Use a design pattern (Composite, Decorator, or Strategy) to change the content of the homepage slightly depending on the user's security rights.
- [ ] Use Facade to isolate database handling from the application for the potential need of changing the database.
