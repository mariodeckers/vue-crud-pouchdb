# vue-crud-pouchdb

## v5 - Vue CRUD PouchDB + CouchDB

### Install CouchDB on Windows

- Documentation https://docs.couchdb.org/
- Download msi from http://couchdb.org/#download
- Be sure to install CouchDB to a path with no spaces, such as C:\CouchDB
- Admin (admin:couchdb)
- Admin panel http://127.0.0.1:5984/_utils
- Add CORS

```
$ npm install -g add-cors-to-couchdb

$ add-cors-to-couchdb -u admin -p couchdb
```

or if database is not localhost:

```
$ add-cors-to-couchdb http://me.example.com -u myusername -p mypassword
```

- Server admin set (serveradmin:couchdb)
- Make sure that database \_users, \_global_changes and \_replicator exist. These should be installed automatically...

### Install CouchDB on CentOS

- Place the following text into `/etc/yum.repos.d/bintray-apache-couchdb-rpm.repo`:

```
[bintray--apache-couchdb-rpm]
name=bintray--apache-couchdb-rpm
baseurl=http://apache.bintray.com/couchdb-rpm/el$releasever/$basearch/
gpgcheck=0
repo_gpgcheck=0
enabled=1`
```

```
$ sudo yum -y install epel-release
```

```
$ sudo yum -y install couchdb
```

- Since previous commands complained, I installed the dependencies like below and the reran installation

```
sudo yum install autoconf autoconf-archive automake \
    curl-devel erlang-asn1 erlang-erts erlang-eunit gcc-c++ \
    erlang-os_mon erlang-xmerl erlang-erl_interface help2man \
    js-devel-1.8.5 libicu-devel libtool perl-Test-Harness
```

```
$ sudo yum -y install couchdb
```

... on a second attempt, it did seem to install. Since it was installed on Windows by now, the admin link http://127.0.0.1:5984/_utils#setup points to the Windows instance and setup cannot continue.
