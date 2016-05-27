# Roundcube-Plugin-ownCloud

Open ownCloud instance directly in Roundcube with authentication

Features
--------

* access owncloud with single login (working)
* interaction attachments with the Roundrive plugin (not tested) #4
* open files from interaction attachments (not tested) #4
* open files from interaction external url using RC interface (progress) #4

License
-------

This plugin is released under the GNU General Public License Version 3
(http://www.gnu.org/licenses/gpl-3.0.html).

Install
-------

1) roundcube part:
* Place this plugin directory into plugins directory of Roundcube;
* When downloading the plugin from GitHub you will need to create a 
  directory called owncloud and place the files in there, 
  ignoring the root directory in the downloaded archive directory in the downloaded archive.

2) owncloud part:
* copy or move directory 'owncloud/apps/roundcube_external' into owncloud apps directory
* go to menu oc and enable "roundcube_external" apps on your ownCloud instance panel apps
* To avoid cross-domain errors you should use the same url (domain) for Roundcube and ownCloud.
* You can also add melanie2 theme to owncloud

*NOTES* you need to use the same login/password between Roundcube and ownCloud

Configuration
-------------

1) roundcube part:
 * inside the rouncube plugin directory just note a file named config.inc.php.dist
   copy file config.inc.php.dist in same place to config.inc.php, then edit that copy file and
 * sure set 'roundcube_owncloud_des_key' config option 
   to a 24 chars values like  'my_key_is_good_need_to24'
 * sure set 'owncloud_url' config option to the full url of owncloud root
   just like "domain.url/owncloud/" *NOTE* please use same url/domain of rounducbe
   to avoid cross-domain errors

2) owncloud part:
 * go to config/config.php file in owncloud root install path and edit that file 
   take in consideration if this files are not exits u'r oc install are not completed
 * edit that file and inside, previous to end of file before the last line will found 
   a string like that ");" just a line before u must added a new line:
 * in that new line paste 'roundcube_owncloud_des_key' => 'my_key_is_good_need_to24', 
   note that the part "my_key_is_good_need_to24" must be equal to the part in roundcube config.
