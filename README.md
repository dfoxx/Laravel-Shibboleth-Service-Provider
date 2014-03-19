Laravel Shibboleth Service Provider
===================================

Shibboleth Authentication for Laravel

Include the follwoing in your composer.json file and run composer update or install if it's a new project.

<pre><code>{
    "require": {
        "saitswebuwm/shibboleth": "dev-master": "dev-master"
    }
}</code></pre>

Include the following line to the end of your /app/config/app.php  'providers array'

<pre><code>'Saitswebuwm\Shibboleth\ShibbolethServiceProvider'</code></pre>

You will also need to change your auth driver in /app/config/auth.php

<pre><code>'driver' => 'shibboleth',</code></pre>

Add the included .htaccess file to your public folder. This should work for everyone. If users must authenticate with shibboleth you will have to modify this as it's set up to allow for both shibboleth and non-shibboleth users by default.

Now we can set it up for your install. Run the following two commands to created the needed database tables and config file.

<pre><code>php artisan config:publish saitswebuwm/shibboleth
php artisan migrate --package="saitswebuwm/shibboleth"</code></pre>

Config Overview
===============