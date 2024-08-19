# Postmortem

Upon the release of ALX's System Engineering & DevOps project 0x19,
approximately 08:00 West African Time (WAT) here in Nigeria, an outage occurred on an isolated
Ubuntu 20.04.5 LTS (GNU/Linux 5.15.0-1021-aws x86_64) container running an Apache web server. GET requests on the server led to
`400 status code Error`'s, when the expected response was an HTML file defining a
simple ALX WordPress site.

## Debugging Process

Bug debugger Brennan (BDB... as in my actual initials... made that up on the spot, pretty
good, huh?) encountered the issue upon opening the project and being, well, instructed to
address it, roughly 19:20 PST. He promptly proceeded to undergo the following steps to solve the problem.

1. Looked in the running processes using `ps aux`. Two `apache2` processes - `root` and `www-data` -
were properly running.

2. Examined the `sites-available` folder of the `/etc/apache2/` directory. Determined that
the web server was serving content located in `/var/www/html/`.

3. In one terminal, ran `strace` on the PID of the `root` Apache process. In another, curled
the server. Expected great response code... only to be disappointed with another error code. `strace` gave no useful
information.

4. Ensured to Repeat step 3, except on the PID of the `www-data` process. The expectations was lowered this
time but was eventually a great step to take. `strace` revelead an `-1 ENOENT (No such file or directory)` error
occurring upon an attempt to access the file `/var/www/html/wp-includes/alx-wp-locale.pphp`.

5. Checked through files in the `/var/www/html/` directory one-by-one, using Emac pattern
matching to try and find out the erroneous `.pphp` file extension. Located it in the
`wp-settings.php` file. (Line 137, `require_once( ABSPATH . WPINC . '/alx-wp-locale.php' );`).

6. Deleted the erroneous `p` from the line.

7. Tested another `curl` on the server. 200 A-ok!

8. Wrote a Puppet manifest to automate fixing of the error.

## Summation

In short, a typo error spoilt the mood all this time. In full, the WordPress app was encountering a critical
error in `wp-settings.php` when tyring to load the file `alx-wp-locale.pphp`. The correct
file name, located in the `wp-content` directory of the application folder, was
`alx-wp-locale.php`.

Patch involved a simple fix on the typo, removing the trailing `p`.

## Prevention

This outage was an application error not a web server error which was thought to be at first. To prevent such outages
moving forward, please keep the following in mind.

*  Review and Improve Testing Processes:

Implement automated tests for configuration files in staging environments.
Assign responsibility for pre-deployment testing to the DevOps team.

* Enhance Monitoring:

Set up detailed monitoring for individual services (e.g., Apache) to detect specific failures.

* Documentation Updates:

Update the Apache configuration documentation to reflect changes in version 2.4.57 and note incompatibilities with custom modules.

* Conduct a Team Review:

Schedule a review meeting to discuss the incident and ensure all team members are aware of the new processes.

Note that in response to this error, I wrote a Puppet manifest
[0-strace_is_your_friend.pp](https://github.com/bdbaraban/alx-system_engineering-devops/blob/master/0x18-webstack_debugging_3/0-strace_is_your_friend.pp)
to automate fixing of any such identitical errors should they occur in the future. The manifest
replaces any `phpp` extensions in the file `/var/www/html/wp-settings.php` with `php`.

But of course, it will never occur again, because we're programmers, and we never make
errors! :wink:
