CHANGELOG
=========

3.6-FUTURE
----------
- Improved storage efficiency for large browse results
- Fixed unnecessary growth of the tmp_browse table from API usage (reported
  by Ondalf)
- Removed external module 'validateEmail'
- Updated PHPMailer to 5.2.6

3.6-alpha6 *2013-05-30*
-----------------------
- Fixed date searches using 'before' to use the correct comparison
  (patch by thinca)
- Fixed long-standing issue affecting Synology users (patch by NigridsVa)
- Added support for MySQL sockets (based on patches by randomessence)
- Fixed some issues with the logic around memory_limit (reported by CableNinja)
- Fixed issue that sometimes removed ratings after catalog operations (reported
  by stebe)
- Fixed catalog song stats (reported by stebe)
- Fixed ACL text field length to allow entry of IPv6 addresses (reported
  by Baggypants)
- Fixed regression preventing the use of an existing database during
  installation (reported by cjsmo)
- Fixed operating on all catalogs via the web interface
  (reported by orbisvicis)
- Added support for nonstandard database ports
- Updated getID3 to 1.9.5
- Improved the performance of stream playlist creation (reported by AkbarSerad)
- Fixed "Pure Random" / Random URLs (reported by mafe)

3.6-alpha5 *2013-04-15*
----------------------
- Fixed persistent XSS vulnerability in user self-editing (reported by
  Jean-Lou Hau)
- Fixed persistent XSS vulnerabilities in AJAX object editing (reported by
  Jean-Lou Hau)
- Fixed character set detection for ID3v1 tags
- Added matroska to the list of known tag types
- Made the getID3 metadata source work better with tag types that Ampache
  doesn't recognise
- Switched from the deprecated mysql extension to PDO
- stderr from the transcode command is now logged for debugging
- Made database updates more robust and verified that a fresh 3.3.3.5 import
  will run through the updates without errors
- Added support for external authenticators like pwauth (based on a patch by
  sjlu)
- Renamed the local auth method to pam, which is less confusing
- Removed the Flash player
- Added an HTML5 player (patch by Holger Brunn)
- Changed the way themes handle RTL languages
- Fixed a display problem with the Penguin theme by adding a new CSS class 
  (patch by Fred Thomsen)
- Made transcoding and its configuration more flexible
- Made transcoded streams more standards compliant by not sending a random
  value as the Content-Length or claiming that ranged requests are
  supported
- Changed rating semantics to distinguish between user ratings and the
  global average and add the ability to search for unrated items
  (< 1 star)
- Updated Prototype to git HEAD (4ce0b0f)
- Fixed bug that disclosed passwords for plugins to users that didn't
  have access to update the password (patch by Fred Thomsen)
- Fixed streaming on Android devices and anything else that expects to
  be able to pass a playlist URL to an application and have it work
- Removed the SHOUTcast localplay controller

3.6-Alpha4 *2012-11-27*
-----------------------
- Removed lyric support, which was broken and ugly
- Removed tight coupling to the PHP mysql extension
- Fixed an issue with adding catalogs on Windows caused by inconsistent 
  behaviour of is_readable() (reported by Lockzi)

3.6-Alpha3 *2012-10-15*
-----------------------
- Updated getID3 to 1.9.4b1
- Removed support for extremely old passwords
- Playlists imported from M3U now retain their ordering
  (patch by Florent Fourcot)
- Removed HTML entity encoding of plaintext email (reported by USMC Guy)
- Fixed a search issue which prevented the use of multiple tag rules
  (reported by Istarion)
- Fixed ASF tag parsing regression (reported by cygn)

3.6-Alpha2 *2012-08-15*
-----------------------
- Fixed CLI database load to work regardless of whether it's run from
  the top-level directory (reported by porthose)
- Fixed XML cleanup to work with newer versions of libpcre
  (patch by Natureshadow)
- Fixed ID3v2 disk number parsing
- Updated getID3 to 1.9.3
- Added php-gettext for fallback emulation when a locale (or gettext) isn't
  supported
- Fixed pluralisation issue in Recently Played
- Added support for extracting MBIDs from M4A files
- Fixed parsing of some tag types (most notably M4A)
- Corrected PLS output to work with more players (reported by bhassel)
- Fixed an issue with compound artists in media with MusicBrainz tags
  (reported by greengeek)
- Fixed an issue with filename pattern matching when patterns contained
  characters that are part of regex syntax (such as -)
- Fixed display of logic operator in rules (reported by Twister)
- Fixed newsearch issue preventing use of more than 9 rules 
  (reported by Twister)
- Fixed JSON escaping issue that broke search in some cases
  (reported by XeeNiX)
- Overhauled CLI tools for installation and database management
- Fixed admin form issue (reported by the3rdbit)
- Improved efficiency of fetching song lists via the API
  (reported by lotan_rm)
- Added admin_enable_required option to user registration
- Fixed session issue preventing some users from streaming
  (reported by miir01)
- Quote Content-Disposition header for art, fixes Chrome issue
  (patch by Sébastien LIENARD)
- Fixed art URL returned via the API (patch by lotan_rm)
- Fixed video searches (reported by mchugh19)
- Fixed Database Upgrade issue that caused catalog user/pass for
  remote catalogs to not be added correctly
- Added the ability to locally cache passwords validated by external
  means (e.g. to allow LDAP authenticated users to use the API)
- Fixed session handling to actually use our custom handler
  (reported by ss23)
- Fixed Last.FM art method (reported by claudio)
- Updated Captcha PHP to 2.3
- Updated PHPMailer to 5.2.0
- Fixed bug in MPD module which affected toggling random or repeat 
  (patch from jherold)
- Properly escape config values when writing ampache.cfg.php
- Fixed session persistence with auth disabled (reported by Nathanael
  Anderson)
- Fixed item count retention for Advanced Random (reported by USAF_Pride) 
- Made catalog verify respect memory_cache
- Some catalog operations are now done in chunks, which works better on
  large catalogs
- API now returns year and bitrate for songs
- Fixed search_songs API method to use Search::run properly
- Fixed require_session when auth_type is 'local'
- Catalog filtering fix
- Toggle artwork with a button instead of a checkbox (patch from mywindow)
- API handshake code cleanup, including a bugfix from postfuturist
- Improved install process when JavaScript is disabled
- Fixed duplicate searching even more
- Committed minor bugfixes for Penguin theme
- Added Fresh theme
- Fixed spurious API handshake failure output

3.6-Alpha1 *2011-04-27*
-----------------------
- Fixed forced transcoding
- Fixed display during catalog updates (reported by Demonic)
- Fixed duplicate searching (patch from Demonic)
- Cleaned up transcoding assumptions
- Fixed tag browsing
- Added new search/advanced random/dynamic playlist interface
- byterange handling for ranges starting with 0 (patch from uberbrady)
- Fixed issue with updating ACLs under Windows (reported by Citlali)
- Add function that check ampache and php version from each website.
- Updated each ampache header comment based on phpdocumentor.
- Fixed only admin can browse phpinfo() for security reasons on /info.php
- Added a few translation words.
- Updated version 3.6 on docs/*
- Implemented ldap_require group (patch from eliasp)
- Fix \ in web path under Apache + Windows Bug #135
- Partial MusicBrainz metadata gathering via plugin
- Metadata code cleanup, support for plugins as metadata sources
- New plugin architecture
- Fixed display charset issue with catalog add/update
- Fixed handling of temporary playlists with >100 items
- Changed Browse from a singleton to multiple instances
- Fixed setting access levels for plugin passwords
- Fixed handling of unusual characters in passwords
- Fixed support for requesting different thumbnail sizes
- Added ability to rate Albums of the Moment
- Added ability to edit/delete playlists while they are displayed
- Fix track numbers not being 0 padded when downloading or renaming.
- Rating search now allows specification of operator (>=, <=, or =)
  and uses the same ratings as normal display.
- Add -t to catalog_update.inc for generating thumbnails
- Generate Thumbnails during catalog art operations
- Fixed transcode seeking of Flacs by switching to MM:SS format for
  flacs being transcoded
- Change album_art_order to art_order to reflect general nature of
  config option
- Fix PHP warning with IP History if no data is found.
- Add -g flag to catalog update to allow for art gathering via cmdline
- Change Update frequency of catalog display to 1 second rather then
  %10 reduces cpu load due to javascript excution (Thx Dmole)
- Add bmp to the list of allowed / supported album art types
- Strip extranious whitespace from cmdline catalog update (Thx ascheel)
- Fix catalog size math for catalogs up to 4TB (Thx Joost.t.Hart@planet.nl) 
- Fix httpq not correctly skipping to new song 
- Fix refreshing of localplay playlist when an item is skipped to
- Fix missing Content-Disposition filename= on non-transcoded songs
- Fix refresh of localplay playlist when you delete a track from it
- Added ability to add Ampache as a search descriptor (Thx Vlet)
- Correct issue with single song downloads
- Removed old useless files
- Added local auth method that uses PHP's PAM module
- Correct potential security issues due to misuse of REQUEST for write
  operations rather then POST (Thx Raphael Geissert <geissert@debian.org>)
- Finished switching to Dba::read() Dba::write() for database calls
  (Thx dipsol)
- Improved File pattern matching (Thx october.rust)
- Updated Amazon Album art search to current Amazon API specs (Thx Vlet)
- Fix typo that caused song count to not be set on tag xml response
- Fix tag methods so that alpha_match and exact_match work
- Fix limit and offset not working on search_songs API method
- Fix import m3u on catalog build so it does something
- Fix inconsistent view during catalog operations    
- Sort malformed files into "Unknown (Broken)" rather then leaving
  them in "Unknown (Orphaned)"
- Fix API democratic voting methods (Thx kindachris)
- Add server version to API ping response
- Fix Localplay API methods (Thx thomasa) 
- Improve bin/catalog_update.inc to allow only verify, clean or add
  (Thx ascheel)
- Fix issue with batch download and UNC paths (Thx greengeek) 
- Added config option to turn caching on/off, Default is off
- Fix issue where file tag pattern was ignore if files have no tag structure
- Add TDRC to list of parsed id3v2 tags
- Added the rating to a single song view
- Fix caching issue when updating ratings where they would not
  display correctly until a page reload
- Altered the behavior of adding to playlists so that it maintains
  playlist order rather then using track order
- Strip excessive \n's from catalog_update (Thx ascheel)
- Fix incorrect default ogg transcode target in base config file
- Fix stream user preferences using cached system preferences 
  rather then their own 
- Fixed prevent_multiple_logins preventing all logins (Thx Hugh)
- Added additional information to installation process 
- Fix PHP 5.3 errors (Thx momo-i)
- Fix random methods not working for localplay
- Fixed extra space on prefixed albums (Thx ibizaman)
- Add missing operator on tag and rating searches so they will
  work with other methods (Thx kiehnet@netscape.net)
- Add MusicBrainz MBID support to uniqly identify albums and
  also get more album art (Thx flowerysong)
- Fix the url to song function
- Add full path to the files needed by the installation just to 
  make it a little clearer
- Fixed potential endless loop with malformed genre tags in mp3s
  (Thx Bernhard Weyrauch)
- Fixed web path always returning false on /test.php
- Updated Man Page to fix litian problems for Debian packaging
- Fixed bug where video was registering as songs for now playing
  and stats
- Add phpmailer and change ampache.cfg.php.dist
- Fixed manpage (Thx Porthose)

3.5 *2009-05-05*
----------------
- Added complete Czech translation (Thx martin hason)
- Add the AlmightyOatmeal-Sanity check to prevent a clean from
  removing all songs if your mount failed, but is still
  readable by ampache
- Make the Lang Install page prettier
- Added Check for hash,inet_pton,windows PHP Version to init so
  that upgrades without pre-reqs are handled correctly
- Allow mms,mmsh,mmsu,mmst,rstp in Radio Stream URLs
- Fixed a problem where after adding a track to a saved playlist
  there was no UI response upon deleting the track without
  a page refresh
- Fix an issue where the full version of the album art was never
  used even when requested
- Fix maxlength on acl fields being to small for all IPv6 addresses
- Add error message when file exists but is unreadable do not
  remove unreadable songs from catalog
- Fixed missing title tag on song browse for the title 
  (Thx flowerysong)
- Fix htmlchar'd rss feed url
- Fix Port not correctly being added to URL in most cases
  even when defined in config

  v.3.5-Beta2 04/07/2009
- Fix ASX playlists so more data shows up in WMP (Thx Jon611)
- Fix dynamic playlist items so they work in stream methods again
- Fixed Recently played so that it correctly shows unique songs
  with the correct data
- Fix some issues with filenames with Multi-byte characters 
  (Thx Momo-i)
- Add WMV/MPG specific parsing functions (Thx Momo-i)
- Add text to /test.php for hash() and SHA256() support under PHP
  section
- Fix SHA256 Support so that it references something that exists
- Fix incorrect debug_event() on login due to typo
- Remove manage democratic playlist as it has no meaning in the 
  current version
- Run Dba::reset_db_charset() after upgrade in case people are playing
  hot potato with their charsets. 
- Move Server Preferences to Admin menu (Thx geekdawg)
- Fixed missing web_path reference on radio creation link
- Fixed remote catalog_clean not working
- Fixed xmlrpc get image. getEncoding wasn't static 

3.5-Beta1 *2009-03-15*
----------------------
- Add democratic methods to api, can now vote, devote, get url
  and the current democratic playlist through the api
- Revert to old Random Play method
- Added proxy use for xmlrpcclient
- Added Configuration 'Wizard' for democratic play
- Fixed interface feedback issues with democratic play actions
- Add extension to image urls for the API will add to others as
  needed due to additional query requirement. Needed to fix
  some DLNA devices
- Fixed typo that caused the height of album art not to display
- Modified database and added GC for tmp_browse table
- Added get lyrics and album art using http proxy server #313 + username,
  password patch
- Added lyricswiki link Ticket #70
- Updated README language
- Updated getid3 library 2.0.0b4 to 2.0.0b5
- Make the Democratic playlist be associated with the user
  who sends it to a 'player' 
- Fixed missing page headers on democratic playlist
- Show who voted for the sogns on democratic playlist
- Increase default stream length to account for the fact that movies
  are a good bit longer then songs
- Correct Issues with multi-byte characters in Lyrics (Thx Momo-i)
- Added caching to Video
- Added Video calls to the API
- Remove redundent code from Browse class by making it extend
  nwe Query class
- Update Prototype to 1.6.0.3
- Add Time range to advanced search
- Add sorting to Video Browse
- Changed to new Query backend for Browsing and Dynamic Playlists

3.5-Alpha2 *2009-03-08*
-----------------------
- Fixed caching of objects with no return value
- Fixed updating of songs that should not be updated during catalog
  verify
- Added default_user_level config option that allows you to define
  the user level when use_auth is false. Also allows manual
  login of admin users when use_auth is false. 
- Fix Version checking and Version Error Message on install (Thx Paleo)
- Moved Statistics to main menu, split out newest/popular/stats
- Fixed bug where saved Thumbnails were almost never used
- Fixed Localplay HTTPQ and MPD controls to reconize Live Stream
  urls. 
- Added Localplay controls to API 
- Added Added/Updated filters to API include the ability to specify
  a date range using ISO 8601 format with [START]/[END]
- Changed API Date format to ISO 8601 
- Fixed Incorrect Caching of Album records that caused the 
  Name + Year + Disk to not be respected
- Added Lyrics Patch (Thx alister55 & momo-i)
- Fixed password not updating when editing an HTTPQ localplay
  instance
- Added Video support
- Fixed normalize tracks not re-displaying playlist correctly
- Fixed now playing now showing currently playing song
- Fixed now playing clear all not correctly refreshing screen
- Fixed adding object to playlist so that it correctly shows the 
  songs rather then an empty playlist
- Added User Agent to IP History information gathering
- Added Access Control List Wizards to make API interface
  setup easier
- Added IPv6 support for Access Control, Sessions, IP History 
- Fixed sorting issue on artist when using search method
- Updated flash player to 5.9.5
- Fixed bug where you admins couldn't edit preferences of
  users due to missing 'key' on form
- Added Mime type to Song XML 

3.5-Alpha1 *2008-12-31*
-----------------------
- Fixed sort_files script so that it properly handles variable
  album art file names in the directories
- Fixed issue where small thumbnails were used for larger images
  if gd based resizing was enabled in the config
- Fixed catalog_update.inc so it doesn't produce errors
- Made democratic play respect force http play
- Make installation error messages more helpful
- Added Swedish (sv_SE) translation (Thanks yeager)
- Allow Add / Verify of sub directories of existing catalogs
- Prevent an fread of 0 bytes if you seek to the end of a file
- Added require_localnet_session config that allows you to exclude
  IP(s) from session checks, see config.dist 
- Added Nusoap (http://sourceforge.net/projects/nusoap/) library
  for use with future lyrics feature
- Fixed problem with flash player where random urls were not being
  added correctly
- Fixed problem with user creation using old method (Thx Purdyk)
- Switched to SHA256() for API and Passwords
- Added check for BADTIME error code from Last.FM and correctly
  return the error rather then a generic one
- Fix http auth session issues, where every request blew away the 
  old session information
- Many other minor improvements (Thx Dipsol)
- Fixed warnings in caching code (Thx Dipsol)
- Massive text cleanup (Thx Dipsol)
- Fixed tag searching and improved some other search methods to 
  prevent SQL warnings on no results
- Improved Test page checks to more accuratly verify putENV support
- Make network downsampling a little more sane, don't require 
  access level
- Added caching to Playlist dropdown 
- Fixed double caching on some objects
- Added base.css and 4 tag 'font' sizes depending on weight/count
- Fixed inline song edit
- Updated registration multi-byte mail.
- Fixed vainfo.class.php didn't catch exception for first analyze.
- Fixed iconv() returns an empty strings (Thx abs0)
- Updated getid3 for multi-byte characters, but some wrong id3tags
  have occurred exception error.
- Fixed use_auth = false not correctly re-creating the session if
  you had just switched from use_auth = true
- Add links to RSS feeds and set default to TRUE in config.dist
- Fixed Dynamic Random/Related URLs with players that always send
  a byte offset (MPD)
- Added Checkbox to use existing Database
- Updated language code and Fixed catalan language code
- Added Emulate gettext() from upgradephp-15
  (http://freshmeat.net/p/upgradephp)
- Fixed Test.php parse error.
- Updated multibyte character strings mail.
- Fixed To send mail don't remove the last comma from recipient.
- Updated More translatable templates.
- Removed merge-messages.sh and Add LANGLIST (each languages 
  translation statistics).
- Fixed If database name don't named ampache, can't renamed tags
  to tag.
- Fixed count issue on browse Artists (Thx Sylvander)
- Fixed prevent_multiple_logins, preventing all logins (Thx hugh)
- Fixed Export catalog headers so it corretly prompts you to download
  the file
- Add ability to sort by artist name, album name on song browse
- Implemented caching on artist and album browse, added total
  artist time to the many artist view
- Fixed test config page so it bounces you back to the test page
  if the config starts parsing correctly
- Fixed browsing so that you can browse two different types in two 
  windows at the same time 
- Improved gather script for translations (Thx momo-i)
- Added paging to the localplay playlist
- Updated German Translation (Thx Laurent)
- Fixed issue where Remote songs would never be removed from
  the democratic playlist
- Fixed issue where user preferences weren't set correctly
  on stream (Thx lorijho)
- Added caching of user preferences to avoid a SQL query on load
  (Thx Protagonist)
- Fixed home menu not always displaying the entire contents
- Fixed logic error with duplicate login setting which caused it
  to only work if mysql auth was used
- Changed Passwords to SHA1 will prompt to reset password
- Corrected some translation strings and added jp_JP (Thx momo-i)
- Ignore filenames that start with . (hidden) solves an issue
  with mac filesystems
- Fix tracking of stats for downloaded songs 
- Fix divide by 0 error during transcode in some configurations
- Remove root mysql pw requirement from installer
- Added Image Dimensions on Find Album Art page
- Added Confirmation Screen to Catalog Deletion
- Reorganized Menu System and Added Modules section
- Fix an error if you try to add a shoutbox for an invalid object
  (Thx atrophic)
- Fixed issue with art dump on jpeg files (Thx atrophic)
- Fixed issue with force http play and port not correctly specifying
  non-standard http port (Thx Deathcrow)
- Remember Starts With value even if you switch tabs
- Fixed rating caching so it actually completely works now
- Removed redundent UPDATE on session table due to /util.php
- Added Batch Download to single Artist view
- Added back in the direct links on songs, requires download set
  to enabled as it's essentially the same thing except with
  now playing information tied to it
- Bumped API Version to 350001 and require that a version is sent
  with handshake to indicate the application will work
- Removed the MyStrands plugin as did not provide good data, and does
  not appear to have been used
- Added Catalog Prefix config option used to determine which prefixes
  should not be used for sorting
- Merged Browse Menu with Home
- Added checkbox to single artist view allowing you to enable/disable
  album art thumbnails on albums of said artist
- Added timeout override on update_single_item because the function
  is a lie
- Fix translations so it's not all german
- Genre Tag is now used as a 'Tag', Browse Genre removed
- Ignore getid3() iconv stuff doesn't seem to work
- Improved fix_filenames.inc, tries a translation first then strips
  invalid characters 
- Fixed album art not clearing thumbnail correctly on gather 
- Fixed localplay instance not displaying correctly after change
  until a page refresh
- Fixed endless loop on index if you haven't played a song in 
  over two years
- Fixed gather art and parse m3u not working on catalog create
  also added URL read support to m3u import
- Upped Minimum requirements to Mysql 5.x
- Add codeunde1load's Web 2.0 style tag patch
- Fixed typo in e-mail From: name (Thx Xgizzmo)
- Fixed typo in browse auto_init() which could cause ampache to not
  remember your start point in some situations. (Thx Xgizzmo)
