# Configuration

## Definition

	* Configuration files estabilish the initial settings for applications, as well as servers and operating systems

## PHP.INI

	* Configuration file for PHP
	* File run upon server starting (CGI) or upon invocation (CLI) (REVISAR)
	* Search Order:
		* sapi MODULE > phprc VARIABLE > Registry Keys > HKEY_LOCAL_MACHINE\software\php > Working Directory (NOT CLI) > Directory (SERVER or PHP) > Win Directory (REVISAR)

## USER.INI (REVISAR)

	* PHP Supports user type ini files

		* Processed by cgi/fastcgi SAPI (REVISAR)
		* Must use PHP_INI_PERDIR or PHP_INI_USER
	* PHP searches for these ini files in all directories
	* Controlled by directives user_ini.filename,user.cache_ttl
		* File name by user_ini.filename (default=user.ini)
		* File reading frequency defined by user.cache_ttl

## Settings

	* Can define version/s of PHP in ini file
	* Generally, use ini_set() within the php script; some settings require php.ini or httpd.conf
	* Apache: change config settings using directives in apache config files and .htaccess; requires AllowOverride [Options/All] PRIVILEGES
