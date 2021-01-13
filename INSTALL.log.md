
# nooo - not compatible w/ 2.7
torchy:~/d/j/2/talking-point-tracker on master
$ python2 -m virtualenv .venv2
# no no no
####

torchy:~/d/j/2/talking-point-tracker on master
$ python3 -m venv .venv3

torchy:~/d/j/2/talking-point-tracker on master
$ source .venv3/bin/activate.fish



## fix deps
# spacy>=2.0.10,<2.1.0
# spacy>=2.0.10
##

torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $ pip install --prefer-binary  -r nlp/requirements.txt
Requirement already satisfied: six==1.11.0 in ./.venv3/lib/python3.9/site-packages (from -r nlp/requirements.txt (line 7)) (1.11.0)
Collecting en_core_web_sm==2.0.0
  Using cached en_core_web_sm-2.0.0-py3-none-any.whl
Collecting nltk==3.3
  Using cached nltk-3.3-py3-none-any.whl
Collecting hug<3.0.0,>=2.4.0
  Using cached hug-2.6.1-py2.py3-none-any.whl (75 kB)
Collecting falcon==2.0.0
  Using cached falcon-2.0.0-py2.py3-none-any.whl (163 kB)
Collecting hug-middleware-cors<2.0.0,>=1.0.0
  Using cached hug_middleware_cors-1.0.0-py3-none-any.whl (4.1 kB)
Collecting spacy>=2.0.10
  Using cached spacy-2.3.5-cp39-cp39-macosx_10_9_x86_64.whl (10.1 MB)
Requirement already satisfied: numpy>=1.15.0 in ./.venv3/lib/python3.9/site-packages (from spacy>=2.0.10->-r nlp/requirements.txt (line 4)) (1.19.5)
Requirement already satisfied: cymem<2.1.0,>=2.0.2 in ./.venv3/lib/python3.9/site-packages (from spacy>=2.0.10->-r nlp/requirements.txt (line 4)) (2.0.5)
Requirement already satisfied: tqdm<5.0.0,>=4.38.0 in ./.venv3/lib/python3.9/site-packages (from spacy>=2.0.10->-r nlp/requirements.txt (line 4)) (4.56.0)
Requirement already satisfied: setuptools in ./.venv3/lib/python3.9/site-packages (from spacy>=2.0.10->-r nlp/requirements.txt (line 4)) (51.1.1)
Collecting waitress<2.0.0,>=1.0.2
  Using cached waitress-1.4.4-py2.py3-none-any.whl (58 kB)
Collecting blis<0.8.0,>=0.4.0
  Using cached blis-0.7.4-cp39-cp39-macosx_10_9_x86_64.whl (5.8 MB)
Collecting catalogue<1.1.0,>=0.0.7
  Using cached catalogue-1.0.0-py2.py3-none-any.whl (7.7 kB)
Collecting murmurhash<1.1.0,>=0.28.0
  Using cached murmurhash-1.0.5-cp39-cp39-macosx_10_9_x86_64.whl (18 kB)
Collecting plac<1.2.0,>=0.9.6
  Using cached plac-1.1.3-py2.py3-none-any.whl (20 kB)
Collecting preshed<3.1.0,>=3.0.2
  Using cached preshed-3.0.5-cp39-cp39-macosx_10_9_x86_64.whl (106 kB)
Collecting requests
  Using cached requests-2.25.1-py2.py3-none-any.whl (61 kB)
Requirement already satisfied: urllib3<1.27,>=1.21.1 in ./.venv3/lib/python3.9/site-packages (from requests->hug<3.0.0,>=2.4.0->-r nlp/requirements.txt (line 1)) (1.26.2)
Collecting certifi>=2017.4.17
  Using cached certifi-2020.12.5-py2.py3-none-any.whl (147 kB)
Collecting chardet<5,>=3.0.2
  Using cached chardet-4.0.0-py2.py3-none-any.whl (178 kB)
Collecting idna<3,>=2.5
  Using cached idna-2.10-py2.py3-none-any.whl (58 kB)
Collecting srsly<1.1.0,>=1.0.2
  Using cached srsly-1.0.5-cp39-cp39-macosx_10_9_x86_64.whl (179 kB)
Collecting thinc<7.5.0,>=7.4.1
  Using cached thinc-7.4.5-cp39-cp39-macosx_10_9_x86_64.whl (992 kB)
Collecting wasabi<1.1.0,>=0.4.0
  Using cached wasabi-0.8.0-py3-none-any.whl (23 kB)
Installing collected packages: murmurhash, wasabi, srsly, preshed, plac, idna, chardet, certifi, catalogue, blis, thinc, requests, falcon, spacy, hug, waitress, nltk, hug-middleware-cors, en-core-web-sm
Successfully installed blis-0.7.4 catalogue-1.0.0 certifi-2020.12.5 chardet-4.0.0 en-core-web-sm-2.0.0 falcon-2.0.0 hug-2.6.1 hug-middleware-cors-1.0.0 idna-2.10 murmurhash-1.0.5 nltk-3.3 plac-1.1.3 preshed-3.0.5 requests-2.25.1 spacy-2.3.5 srsly-1.0.5 thinc-7.4.5 waitress-1.4.4 wasabi-0.8.0
(.venv3)



torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $ ...
wget https://github.com/nreimers/truecaser/releases/download/v1.0/english_distributions.obj.zip
unzip english_distributions.obj.zip
mv distributions.obj nlp/truecaser_distributions.obj
rm english_distributions.obj.zip



(.venv) $ createdb tpt
createdb: error: could not connect to database template1: could not connect to server: No such file or directory
	Is the server running locally and accepting
	connections on Unix domain socket "/tmp/.s.PGSQL.5432"?

(.venv) $ tldr pg_ctl

pg_ctl

Utility for controlling a PostgreSQL server and database cluster.
More information: <https://www.postgresql.org/docs/current/app-pg-ctl.html>.

- Initialize a new PostgreSQL database cluster:
    pg_ctl -D data_directory init

- Start a PostgreSQL server:
    pg_ctl -D data_directory start

- Stop a PostgreSQL server:
    pg_ctl -D data_directory stop

- Restart a PostgreSQL server:
    pg_ctl -D data_directory restart

- Reload the PostgreSQL server configuration:
    pg_ctl -D data_directory reload
(.venv)
torchy:~/d/j/2/talking-point-tracker on master
(.venv) $ mkdir db
(.venv)
torchy:~/d/j/2/talking-point-tracker on master
(.venv) $ pg_CTL -D db init
The files belonging to this database system will be owned by user "100ideas".
This user must also own the server process.

The database cluster will be initialized with locale "en_US.UTF-8".
The default database encoding has accordingly been set to "UTF8".
The default text search configuration will be set to "english".

Data page checksums are disabled.

fixing permissions on existing directory db ... ok
creating subdirectories ... ok
selecting dynamic shared memory implementation ... posix
selecting default max_connections ... 100
selecting default shared_buffers ... 128MB
selecting default time zone ... America/Los_Angeles
creating configuration files ... ok
running bootstrap script ... ok
performing post-bootstrap initialization ... ok
syncing data to disk ... ok

initdb: warning: enabling "trust" authentication for local connections
You can change this by editing pg_hba.conf or using the option -A, or
--auth-local and --auth-host, the next time you run initdb.

Success. You can now start the database server using:

    /usr/local/Cellar/postgresql/13.1/bin/pg_ctl -D db -l logfile start

(.venv)
torchy:~/d/j/2/talking-point-tracker on master
(.venv) $ pg_ctl -D db -l db.log start
waiting for server to start.... done
server started
torchy:~/d/j/2/talking-point-tracker on master
(.venv) $ createdb tpt
(.venv)
torchy:~/d/j/2/talking-point-tracker on master
(.venv) $ createuser tpt -P
Enter password for new role: mollysball
Enter it again:
(.venv)

# set earlier node
$ nodenv local 11.15.0

## fix deps in package.json
## add these if not there
#    "sequelize": "^4.44.4",
#    "sequelize-cli": "^4.1.1",


torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $ createdb tpt_dev

torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $ createdb tpt_test

torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $ npm run migrate

> talking-point-tracker@0.1.0 migrate /Users/100ideas/dev/js/2020-captions/talking-point-tracker
> sequelize db:migrate


Sequelize CLI [Node: 11.15.0, CLI: 4.1.1, ORM: 4.44.4]

Loaded configuration file "config/sequelize-config.js".
Using environment "development".
== 20181101190050-create-channels-table: migrating =======
== 20181101190050-create-channels-table: migrated (0.022s)

== 20181101190103-create-sentences-table: migrating =======
== 20181101190103-create-sentences-table: migrated (0.024s)

== 20181101190108-create-named-entities: migrating =======
== 20181101190108-create-named-entities: migrated (0.016s)

(.venv3)
torchy:~/d/j/2/talking-point-tracker on master
(.venv3) $
