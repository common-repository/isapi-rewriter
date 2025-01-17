=== ISAPI Rewriter ===
Contributors: theandystratton
Donate link: http://theandystratton.com/donate
Tags: windows, iis, permalinks
Requires at least: 2.6
Tested up to: 5.3
Stable tag: trunk

This plugin makes WordPress' default permalinks behavior work with ISAPI Rewrite 3 (which supports .htaccess files).

== Description ==

This plugin ensures the REQUEST_URI header is set during the initialization of WordPress, allowing permalinks to work on Windows IIS hosting. The nice thing about the plugin 
is it can remain activated when upgrading WordPress, as opposed to modifying the core WordPress files as many have in the past.

The plugin has been tested on Windows Server 2003 with ISAPI Rewrite 3. Please comment with feedback if you're experiencing other issues or if it has helped you!

Find more information, comments, and support here: <a href="http://theandystratton.com/2009/get-wordpress-permalinks-working-with-windows-iis-and-isapi-rewrite">http://theandystratton.com/2009/get-wordpress-permalinks-working-with-windows-iis-and-isapi-rewrite</a>

== Installation ==

1. Download and unzip to the 'wp-content/plugins/' directory 
1. Activate the plugin.

== Frequently Asked Questions ==

= Do I need to do anything special before/after activation? =

Just make sure the .htaccess file is setup. The default WordPress created .htaccess file should work as expected with this plugin enabled.

Example .htaccess file:

<pre>RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule .* /index.php [L]</pre>
