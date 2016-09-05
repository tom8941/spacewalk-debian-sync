spacewalk-debian-sync
=====================

An improvised repo-sync to bring Debian packages into Spacewalk

## How to use it

```
spacewalk-debian-sync.pl --url [url of the repo] --channel [name of the channel on spacewalk] --username [spacewalk user] --password [spacewalk password] --packagelist [filepath of package list] --proxy [proxy url]
```
--proxy and --packagelist are optional

The package list should have 1 package per line.

proxy url : http://username:password@proxy:port

ex:

```
spacewalk-debian-sync.pl --url 'ftp://ftp.fr.debian.org/debian/dists/Debian7.11/main/binary-amd64/' --channel wheezychannel --username spaceuser --password spacepassword --packagelist /opt/packagelist --proxy http://proxyuser:proxypassword@myproxy.local:8080
```
You can obtain a package list by using the command : 

```
#for installed package
dpkg-query -f '${binary:Package}\n' -W
```
```
#for available package
apt-cache pkgnames
```
You can modify this list manually or have it from another source if needed. Don't forget that the filter is performed by a simple match of grep between the package names of this file and the one contained in Packages.gz of the repository.
...



## External Source

- Forked project from https://github.com/stevemeier/spacewalk-debian-sync
