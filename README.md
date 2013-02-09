MediaWiki
=========

A plugin for [Minion](http://github.com/rfreebern/minion). Allows your bot to
perform simple keyword searches on a MediaWiki installation.

Installation
------------

Place `MediaWiki.php` in `plugins/MediaWiki/` in your Minion install. If your Minion
install is a git repository, you can

    git submodule add https://github.com/rfreebern/minion-mediawiki-plugin.git plugins/MediaWiki

from the Minion base directory.

Configuration
-------------

Required `config.php` parameters:

* WikiURL

  URL to access your MediaWiki installation.

* Username
* Password

  Credentials to allow the bot full API access.

* curlCookieFile

  Path and filename where cURL can store session cookies for login.

Optional parameters:

* HTTPAuth
  * Username
  * Password

  HTTP basic authentication credentials to access your MediaWiki installation.

Example:

    $this->PluginConfig['MediaWiki'] = array(
        'HTTPAuth' => array(
            'Username' => 'abaddon',
            'Password' => 'inferno'
        ),
        'Username' => 'minion',
        'Password' => 'test1234',
        'WikiURL' => 'http://wiki.yoursite.com',
        'curlCookieFile' => './cookies.txt'
    );

Usage
-----

* `!wiki`

  Prints the URL to your wiki installation.

* `!wiki keyword`

  Performs an article title search for `keyword` in your wiki; prints the URL to the top hit.

