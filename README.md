# 2018-11-05 MOVED

Newest docker-compose.yml has moved to https://raw.githubusercontent.com/wekan/wekan/edge/docker-compose-postgresql.yml

# Docker: Wekan to PostgreSQL read-only mirroring

* [Wekan kanban board, made with Meteor.js framework, running on
  Node.js](https://wekan.io) -- [GitHub](https://github.com/wekan/wekan)
* [MongoDB NoSQL database](https://www.mongodb.com)
* [ToroDB: MongoDB to PostgreSQL read-only mirroring, programmed with Java](https://www.torodb.com) --
  [GitHub](https://github.com/torodb/torodb) --
  [Interview at FLOSS Weekly](https://twit.tv/shows/floss-weekly/episodes/377)
* [LibreOffice 3.5 with native PostgreSQL support](https://www.libreoffice.org)

## Screenshot

![Screenshot of PostgreSQL with LibreOffice][screenshot]

## Install

1) Install docker-compose.

2) Clone this repo.

```bash
git clone https://github.com/wekan/wekan-postgresql.git
cd wekan-postgresql
```

3) IMPORTANT: In docker-compose.yml, to use Wekan on local network, change ROOT_URL=http://localhost to http://IPADRESS like http://192.168.10.100 or http://example.com

4) OPTIONAL: In docker-compose.yml, change PostgreSQL database name, username and password from wekan to something else.

5) Write:

```bash
docker-compose up
```

6) Wekan is at http://IPADDRESS or http://example.com (port 80)

7) PostgreSQL is at address postgresql://127.0.0.1:15432/wekan or other name database
   that you changed in step 3), and changed username: wekan, password: wekan too.
   Do not write to PostgreSQL, as it's readonly mirror. Write to MongoDB or make
   changes in Wekan. If server port 15432 open, PostgreSQL can be accessed also
   remotely at local network at http://IPADDRESS:15432/wekan

8) MongoDB is at 127.0.0.1:28017

9) Wekan and databases bind to address 0.0.0.0 so could be also available to other
   computers in network. I have not tested this.

10) [Restore your MongoDB data](https://github.com/wekan/wekan/wiki/Export-Docker-Mongo-Data).

## Feedback

[GitHub issue 787](https://github.com/wekan/wekan/issues/787)

[screenshot]: http://i.imgur.com/tpmY1xH.png
