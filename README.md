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
A `whoowns` script that works like the one from cPanel

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
[root@cwp ~]# review example
🧔 Username: example
🌎 Domain: example.com
📦 Package: default
📅 Created: 2025-07-17 16:23:33
📧 Email: example@example.com
💾 Home Size: 21M
🌐 IP: 5.161.200.209
📂 Doc. Root: /home/example/public_html

🌎 Add-on Domains
   example.net /home/example/example.net

🌎 Subdomains
   subdomain.example.com /home/example/subdomain.example.com
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

### cwplogin
Like `whmlogin` but for CWP (as much as possible)

```
[root@cwp ~]# cwplogin --help
cwplogin: Like "whmlogin" but for CWP

USAGE: cwplogin
    --help -h           Show this message
    --version -v        Show version information
[root@cwp ~]# cwplogin
URL: https://cwp.example.com:2087
Username: root
Password: gd+1VgjR+ILDs6NcBtS7

Hit ENTER to restore original password and exit (or wait 5 minutes):
```
