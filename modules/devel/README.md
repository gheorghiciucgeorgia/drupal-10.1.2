[[_TOC_]]

#### Introduction

Devel module contains helper functions and pages for Drupal developers and
inquisitive admins:

 - A block and toolbar for quickly accessing devel pages
 - A menu tab added to entities to give access to internal entity properties
 - Urls created to view the internal entity properties even when there is no menu tab, for example /devel/paragraph/n
 - Debug functions for inspecting a variable such as `dpm($variable)`
 - Debug a SQL query `dpq($query` or print a backtrace `ddebug_backtrace()`
 - A block for masquerading as other users (useful for testing)
 - A mail-system class which redirects outbound email to files
 - Drush commands such as `fn-hook`, `fn-event`, `token`, `uuid`, and `devel-services`
 - *Devel Generate*. Bulk creates nodes, users, comment, taxonomy, media, menus for development. Has
 Drush integration.

This module is safe to use on a production site. Just be sure to only grant
_access development information_ permission to developers.

#### Collaboration
- https://gitlab.com/drupalspoons/devel is our workplace for code, MRs, and CI. See
[DrupalSpoons](https://gitlab.com/drupalcontrib/webmasters/-/blob/master/README.md)
for more info.
- Drupalspoons auto-pushes back to git.drupalcode.org in order to keep
[Security Team](https://www.drupal.org/security) coverage and packages.drupal.org integration.
- Chat with us at [#devel](https://drupal.slack.com/archives/C012WAW1MH6) on Drupal Slack.

#### Local Development
1. Clone devel `git clone https://gitlab.com/drupalforks/devel.git` (note - this is the shared fork, not the "spoon")
1. `cd devel`
1. Install the composer plugin from https://gitlab.com/drupalspoons/composer-plugin. Your source tree now looks like:
![Folder tree](/icons/folder.png)
1. Configure a web server to serve devel's `/web` directory as docroot. __Either__ of these works fine:
    1. `vendor/bin/spoon runserver`
	1. Setup Apache/Nginx/Other. A virtual host will work fine. Any domain name works.
1. Configure a database server and a database.
1. Install a testing site `vendor/bin/spoon si -- --db-url=mysql://user:pass@localhost/db`. Adjust as needed.

#### Testing
- [CI docs](https://gitlab.com/drupalspoons/webmasters/-/blob/master/docs/ci.md) gives info on running tests.
- See [develCommandsTest.php](tests/src/Functional/DevelCommandsTest.php) for an example of Drush command testing. This uses [Drush Test Traits](https://www.drush.org/contribute/#drush-test-traits).

#### Version Compatibility
| Devel version | Drupal core | PHP  | Drush |
|---------------|-------------|------|-------|
| 5.x           | 9,10        | 7.4+ | 11+   |
| 4.x           | 8.9+,9      | 7.2+ | 9+    |
| 8.x-2.x       | 8.x         | 7.0+ | 8+    |

#### Maintainers

See https://gitlab.com/groups/drupaladmins/devel/-/group_members.
