NoteDown
=============

Presentation
-------------
NoteDown is a MarkDown-powered simple note-taking application.

NoteDown is made with the following technologies :

- HTML5, [Thymeleaf](http://www.thymeleaf.org/) and [Twitter Bootstrap](http://twitter.github.com/bootstrap/)
- [The Spring Framework](http://www.springsource.org/)

Installation for developers
---------------------------
### 3 minutes installation

- Clone, fork or download the source code from this Github page
- Install [Maven 3](http://maven.apache.org/)
- Run NoteDown from Maven : `mvn spring-boot:run`
- Connect to the application at http://127.0.0.1:8080

An in-memory embedded HSQLDB Database is used for development needs.

Installation for production use
-------------------------------
Download latest release from here : https://github.com/jchampemont/notedown/releases

See bundled INSTALL.md file for installation details.


Upgrading from a previous version
---------------------------------------
Upgrading is normally just a matter of using a newer version of the application.

Database schema upgrades should be handled gracefully thanks to liquibase migrations.

Contributing
------------
I am happy to accept any pull request as long as it respects the following guidelines :

- Meets some basic code quality requirements
- Please do some basic unit testing on your code
- Use current technology stack before introducing any new dependency
- You accept your code to be licensed under the Apache License, Version 2.0
- NoteDown should stay *KISS* : Keep It Simple, Stupid.

Feel free to add your name on the list of contributors below.

In case you need to modify the data model, you should do the following :

- Edit `liquibase.properties` and `application.properties` to use a real RDBMS (MySQL or PostgreSQL supported)
- Launch the application once in order to create tables
- Add the required modifications to entities
- `mvn clean install liquibase:diff` will generate a liquibase diff file `db.changelog-master-diff.xml`
- Add the generated change set to `db.changelog-master.xml` with your author's name and correct incremental id
- Please preferably use XML syntax over pure SQL
- Launch the application and check everything went fine with liquibase migration

Contributors
------------

- Jean Champémont

License
-------

Copyright 2014, 2015 [Jean Champémont](http://www.jeanchampemont.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this application except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
