# Security

## Configuration

* PHP.ini error configuration directives (REVISAR)
	* display_error = off, log_errors = on (Production)
	* error_reporting = E_ALL (Development)
	* error_reporting = E_ALL & ~E_DEPRECATED & ~E_STRICT (Production)

* Using PHP as a CGI binary
	PHP has built-in safeguards against common attack schemes using interpreters, along with configurable settings for added security:
		* Accessing system files: PHP doest no interpreted command line arguments pased by the interpreted to the CGI interface
		* Accessing private documents: runtime directives cgi.force_redirect, doc_root and user_dir can be used to overcome security vulnerabilities in server setups when dealing with restricted directories
		* Accessing public files: option --enable-force-cgi-redirect can be added to the configure script for servers that do not allow redirects or do not have a way to confirm a request has been safely redirected
		* Directly calling php: the configuration directive cgi.force_redirect blocks the abilit to call php directly from a URL; directive will allow php to parse only if it has been redirected (APACHE Web Server)
		* Parser: (optional) Place PHP Parser binary outside of the web tree
		* Active content (scripts, executables)(REVISAR): set up a separate script directory for executables to avoid security issues due to displaying active content as HTML documents; set document root using directive doc_root in the config file or set environment variable PHP_DOCUMENT_ROOT; files will be opened with doc_root and path info in the request; another option is to utilize user_dir - when unset causes a requested file to open under doc_root and not user's home directory (file formar ~user/document.php)

# Using PHP installed as an apache module

PHP in this configuration will inherit the permissions structure of the Apache server, common security steps to take include:

* Set the Apache authorization (VS. using default 'nobody' setting)
* Create an access model using .htaccess files, ldap, ...
* Do not grant the web server user root permission (permit the use of sudo, chroot); instead, use open_basedir to control directory use

# Filesystem security

* Only allow limited permissions to the apache web user binary

# Error Handling

* Display errors only in a development enviroment; in production, display_errors = OFF and log_errors = on

* Use high error reporting settings
error_reporting = E_ALL

# Session security

* Description: session hijacking
	* Occurs when the session id is stolen
	* A session ID is the sole authentication token for the web site

* Counter-measures
* Regenerate the session id upon login, before authentication, using session_regenerate_id(true). Passing boolean true removes the old session and is critical as a counter measure
	
	* Also, regenerate session id prior "critical" operations
	* Use SSL encryption for the login, or assign a hidden key (not as good)
	* Check that the IP address remains the same (although not always reliable)
	* Use short session timeout
	* Provide user logout
	* Destroy an old and create a new session with: session_regenerate_id(true)
	* Set PHP configuration directive session.use_only_cookies = 1
	* Prevent javascript access to session cookie with PHP configuration directive session.cookie_httponly=1

# Cross-site scripting

* Description
	
	* Injection of HTML, CSS, or script code into a page
	Ex: <script> alert(document.cookie)</script>
	* Insertion could be permanent (incorporated) or via a link
	* Javascript is particularly dangerous because of its ability to:
		* Redirect the user
		* Modify the page
		* Read out cookies

	* Counter-measures
		* Escape data before outputting it
			* htmlspecialchars()
				* Doest not escape single quotes by default; use ENT_QUOTES option.
			* htmlentities()
			* strip_tags()
		* Whitelisting is effective, blacklisting is not

# Cross-site request forgeries

* Description 
	* A requested generated from a user's browser without the user's knowledge
	* Relies on web site trust of logged-in users
	* An attack involves tricking a user into transmitting 'bad' html with a request, which then returns sensitive data to the attacker
	* Executed via iframes, XmlHttpRequest calls or embedded in tags such as:
		<script>, <object>, <embed>, <img>, ...
	  Ex:
	  	<form name="myForm">
	  	<input type="hidden" name="item_id" value="123"/>
	  	<input type="hidden" name="quantity" value="1"/>
	    </form>
	    <script>document.forms['myForm'].submit();</script>

* Counter-measures
	* Use a unique form token in a hidden input field to verify the request
	* Require re-login before sensitive operations (Ex: financial)

# SQL Injection

* Description

	* SQL code is injected into the SQL query
	* Allows attacker to do almost anything the database user is permitted
	* Example SQL statement will return all the data from the 'users' table:
		$sql = "SELECT * FROM users WHERE username='$user' and password='$pass'";
		$user and $pass contain the value ' or 1=1"
	* Further attack possibilities: insert data, delete data, read data, denial of service...

* Counter-measures
	* Use prepared statements when supported by the database
	* Use database-specific escaping functions when creating the SQL statement
		Ex: mysqli_real_escape_string()
	* addslashes() is not a sufficient approach

# Remote code injection

* Remote code injections attempt to run the attacker's code on a server, often by exploiting the functionality of the include or require functions

* The eval(), exec(), system() and shell_exec() functions are vulnerable to remote code injections

* Include / require attacks
	* Occur when including and executing files
		* Possible from remote servers
		* Includes remote code execution

* Counter-measures
	* Check data against a whitelist
	* Remove paths using basename()
	* Set allow_url_include = Off in php.ini
		* Helps somewhat but not sufficient, as some attack vectors remain open

* Dynamic data call attacks
	* Code injection can occur when using dynamic data in calls to system() and related

* Counter-measures
	* Limit or remove use of system(), exec(), eval(),
	back tick (`) and shell_exec()
	* escapeshellarg() to escape arguments
	* escapeshellcmd() to escape commands

# Email Injection

* Email/SMTP
	* Do not provide open relays
	* Open the SMTP port only if essential
	* Use a "tarpits" technique to slow requests as a means of dissuading attacks

# Input filtering

	* Input is everything that comes as a part of the http request
	* Some data does not seem to be input, but may contain data originating from the user, thus must be considered as input (Ex: Session data that was originally supplied by the user)

	* Character set:
		* Risk:
			* Attack vectors may employ a non-standard char set (Ex: UTF-8 enconded) that may be missed by filtering, but executed by the browser
		* Counter:
			* Use the same char set for filtering as the target procedure
			* Convert charsets prior to filtering
				Content-type: text/html; charset="UTF-8"
			* Use PHP's filter extension
			* Use filters native to the databse (Ex: DB Quoting functions)

# Escape output

* One of two fundamental security rules: (1) Filter and validate all input; (2) Escape output

* Always escape outside data unless previously filtered

* Typical output formats that require escaping when containing user data: HTML, JSON, SQL

* Never rely on client side (Javascript) filtering

* Functions used to escape data before outputting within html:
	htmlspecialchars()
	htmlentities()
	strip_tags()
