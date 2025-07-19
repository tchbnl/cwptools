I need to use CWP sometimes for work. CWP is... rough. Here are some tools I made to make working with it a little easier.

## Released
### docroot
Find the document root for domains on a CWP server

```
[root@cwp ~]# docroot
docroot: Find the document root for domains on a CWP server

USAGE: docroot DOMAIN
    --help -h           Show this message
    --version -v        Show version information
[root@cwp ~]# docroot cwpsite.tchbnl.net
/home/cwpsite/public_html
[root@cwp ~]# docroot testdomain.com
/home/cwpsite/testdomain.com
[root@cwp ~]# docroot test.testdomain.com
/home/cwpsite/test.testdomain.com
[root@cwp ~]# docroot sexylenin.com
sexylenin.com wasn't found in the CWP database.
```

### whoowns
A 'whoowns' script that works like the one from cPanel

```
[root@cwp ~]# whoowns
whoowns: Find the owner of a domain on a CWP server

USAGE: whoowns DOMAIN
    --help -h           Show this message
    --version -v        Show version information
[root@cwp ~]# whoowns cwpsite.tchbnl.net
cwpsite
[root@cwp ~]# whoowns test.testdomain.com
cwpsite
[root@cwp ~]# whoowns sexylenin.com
sexylenin.com wasn't found in the CWP database.
```

### review
Show detailed information about a CWP account

```
[root@cwp ~]# review
review: Show detailed information about a CWP account

USAGE: review USER
    --help -h           Show this message
    --version -v        Show version information
[root@cwp ~]# review cwpsite
🧔 Username: cwpsite
🌎 Domain: cwpsite.tchbnl.net
📦 Package: default
📅 Created: 2023-10-29 06:13:23
📧 Email: no.email@example.com
💾 Home Size: 8.0M
🌐 IP: 5.161.207.83
📂 Doc. Root: /home/cwpsite/public_html
[root@cwp ~]# review greg
greg wasn't found in the CWP database.
```

### switch
Like `su - user` but not. Quickly access a CWP user's shell account. Bypasses disabled shell and works around low nproc limits on accounts.

```
[root@cwp ~]# switch
switch: "Switch" into a local CWP user's shell account

USAGE: switch USER
    --help -h           Show this message
    --version -v        Show version information
[root@cwp ~]# switch example
[example@cwp ~]$
```

## In Development
### cwplogin
Like 'whmlogin' but for CWP (as much as possible). Haven't forgotten about this one. Basic idea right now is:

1. Copy the current shadow line for root
2. Update the root password
3. Show the new root password with a link to the CWP admin
4. Hit enter (or Ctrl+C or w/e) to restore the original shadow line

CWP doesn't have an API to create a root login session like cPanel does :(
