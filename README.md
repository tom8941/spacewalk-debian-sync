spacewalk-debian-sync
=====================

An improvised repo-sync to bring Debian packages into Spacewalk

## How to use it

```
spacewalk-debian-sync.pl --url [url of the repo] --channel [name of the channel on spacewalk] --username [spacewalk user] --password [spacewalk password] --packagelist [filepath of package list]

The package list should have 1 package per line

ex:

spacewalk-debian-sync.pl --url 'ftp://ftp.fr.debian.org/debian/dists/Debian7.11/main/binary-amd64/' --channel wheezychannel --username spaceuser --password spacepassword --packagelist /opt/packagelist

You can optain a package list by using the command : 

#for installed package
dpkg-query -f '${binary:Package}\n' -W

#for available package
apt-cache pkgnames

...

```

## External Source

- Forked project from https://github.com/stevemeier/spacewalk-debian-sync
