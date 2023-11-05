I need to use CWP sometimes for work reasons. CWP is bad. It is bad and the CWP developers should feel bad. So here are some tools to make it a little easier to work with.

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
[root@cwp ~]# docroot yourlocalbatmanguy.com
yourlocalbatmanguy.com wasn't found in the CWP database.
```

## In Development
### review
Show detailed information about a CWP account

### cwplogin
Like 'whmlogin' but for CWP (as much as possible)

### whoowns
A 'whoowns' script that works like the one from cPanel
