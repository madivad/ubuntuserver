# Ubuntu Server Install

I'll look further into scripting this down the track, but at the moment it's a list of applications and changes I make to a server install of Ubuntu I use for development purposes. 

# 1. Install Ubuntu Server
I use the standard ubuntu server install image, always using the LTS version. Currently 16.04.3

I usually run through all the default settings paying particuar note to only two sections:

1. for hostname, be sure to add a fully qualified domain name (FQDN) (it should be resolvable only for the virtualmin package, but I often don't bother with setting the "fully" part unless I'm doing remote testing, and
2. adding OpenSSH in the package selector dialog when it finally comes up. 

Everything else can be install later.

# 2. Update
Update and upgrade the system 

`sudo apt update && sudo apt upgrade`

# 3. Start installing your desired packages
The first package I usually install is VirtualMin. I ilke this package because it provides a nice visual GUI on a server platform for monitoring your server, setting up development domains and additional tools including webmin.

Go to: https://www.virtualmin.com/download.html and grab the `wget` line:

`wget http://software.virtualmin.com/gpl/scripts/install.sh`

`sudo /bin/bash ./install.sh

The install script will take care of adding the virtualmin and webmin RPM-GPG keys. It will also remove some default packages and replace them with the virtualmin supported versions. 

Grab a tea, coffe or stiff drink while it does the install. Depending on your speed it should only tae a few minutes. 

    Removing Debian standard Webmin package, if they exist...
    INFO - Removing Debian apache packages...`
    INFO - Installing dependencies using command: /usr/bin/apt-get --config-file apt.conf.noninteractive -y --force-yes install bsdutils postfix postfix-pcre webmin usermin ruby libxml-simple-perl libcrypt-ssleay-perl unzip zip libfcgi-dev bind9 spamassassin spamc procmail procmail-wrapper libnet-ssleay-perl libpg-perl libdbd-pg-perl libdbd-mysql-perl quota iptables openssl python mailman subversion ruby irb rdoc ri mysql-server mysql-client mysql-common postgresql postgresql-client awstats webalizer dovecot-common dovecot-imapd dovecot-pop3d proftpd libcrypt-ssleay-perl awstats clamav-base clamav-daemon clamav clamav-freshclam clamav-docs clamav-testfiles libapache2-mod-fcgid apache2-suexec-custom scponly apache2 apache2-doc libapache2-svn libsasl2-2 libsasl2-modules sasl2-bin php-pear php php-cgi libapache2-mod-php php-mysql ntpdate

### Let's take a closer look at virtual min:
* first off, select the new theme (if it's available to you, it's much nicer and easier to read. If it's not appearing at the top of the screen, don't worry about it)
* If there is a configuration wizard, you can either cancel it to select the defaults (usually ok for most systems), or click next to progress through it choosing the optimal settings for your system.
* 
