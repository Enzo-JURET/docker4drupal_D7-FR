# Pile Drupal à base de dockers

[![Build Status](https://travis-ci.org/wodby/docker4drupal.svg?branch=master)](https://travis-ci.org/wodby/docker4drupal)

## Introduction

Docker4Drupal est un ensemble d'images de docker optimisé pour Drupal. Utilisez le fichier `docker-compose.yml` de la [dernière version stable](https://github.com/wodby/docker4drupal/releases) pour faire tourner l'environnement local sous Linux, Mac OS X et Windows. 

* Lire la documentation sur [**comment utiliser**](https://wodby.com/docs/stacks/drupal/local#usage)
* Rejoignez notre communauté sur [Spectrum](https://spectrum.chat/wodby/drupal) et posez des questions sur le canal `#Drupal`.
* Suivez [@wodbycloud](https://twitter.com/wodbycloud) pour les annonces à venir

## Stack

La pile (stack) Drupal se compose des conteneurs par défaut suivants :

| Container       | Versions               | Service name    | Image                              | Default |
| --------------  | ---------------------- | --------------- | ---------------------------------- | ------- |
| [Nginx]         | 1.17, 1.16             | `nginx`         | [wodby/nginx]                      |         |
| [Apache]        | 2.4                    | `apache`        | [wodby/apache]                     | ✓        |
| [Drupal]        | 8, 7                   | `php`           | [wodby/drupal]                     |         |
| [PHP]           | 7.2				       | `php`           | [wodby/drupal-php]                 | ✓        |
| [MariaDB]       | 10.4				   | `mariadb`       | [wodby/mariadb]                    | ✓        |
| [PostgreSQL]    | 12, 11, 10, 9.x        | `postgres`      | [wodby/postgres]                   |         |
| [Redis]         | 5, 4                   | `redis`         | [wodby/redis]                      |         |
| [Memcached]     | 1                      | `memcached`     | [wodby/memcached]                  | ✓        |
| [Varnish]       | 6.0		               | `varnish`       | [wodby/varnish]                    | ✓        |
| [Node.js]       | 12, 10, 8              | `node`          | [wodby/node]                       |         |
| [Drupal node]   | 1.0                    | `drupal-node`   | [wodby/drupal-node]                |         |
| [Solr]          | 8			           | `solr`          | [wodby/solr]                       | ✓        |
| [Elasticsearch] | 7, 6                   | `elasticsearch` | [wodby/elasticsearch]              |         |
| [Kibana]        | 7, 6                   | `kibana`        | [wodby/kibana]                     |         |
| [OpenSMTPD]     | 6.0                    | `opensmtpd`     | [wodby/opensmtpd]                  |         |
| [Mailhog]       | latest                 | `mailhog`       | [mailhog/mailhog]                  |         |
| [AthenaPDF]     | 2.10.0                 | `athenapdf`     | [arachnysdocker/athenapdf-service] |         |
| [Rsyslog]       | latest                 | `rsyslog`       | [wodby/rsyslog]                    |         |
| [Blackfire]     | latest                 | `blackfire`     | [blackfire/blackfire]              |         |
| [Webgrind]      | 1.5                    | `webgrind`      | [wodby/webgrind]                   |         |
| [Xhprof viewer] | latest                 | `xhprof`        | [wodby/xhprof]                     |         |
| Adminer         | 4.6                    | `adminer`       | [wodby/adminer]                    |         |
| phpMyAdmin      | latest                 | `pma`           | [phpmyadmin/phpmyadmin]            |         |
| Selenium chrome | 3.141                  | `chrome`        | [selenium/standalone-chrome]       |         |
| Portainer       | latest                 | `portainer`     | [portainer/portainer]              | ✓        |
| Traefik         | latest                 | `traefik`       | [_/traefik]                        | ✓        |

Versions Drupal supportées : 7  

## Documentation

La documentation complète est disponible à l'adresse https://wodby.com/docs/stacks/drupal/local

## Images' tags

Le format des balises d'images est `[VERSION]-[STABILITY_TAG]` où :

`[VERSION]` est la _version d'une application_ (sans version patch) s'exécutant dans un conteneur, par exemple `wodby/nginx:1.1.15-x.x.x.x' où la version Nginx est `1.15' et `x.x.x' est un tag de stabilité. Pour certaines images, nous incluons des versions majeures et mineures comme PHP `7.2`, pour d'autres nous incluons seulement des versions majeures comme Redis `5`. 

'[STABILITY_TAG]` est la _version d'une image_ qui correspond à une balise git du référentiel d'images, par exemple `wodby/mariadb:10.2-3.3.3.8` a MariaDB `10.2` et la balise de stabilité[`3.3.8`](https://github.com/wodby/mariadb/releases/tag/3.3.8). Les nouvelles balises de stabilité incluent des mises à jour de patchs pour les applications et les corrections/améliorations d'images (nouvelles env vars, corrections d'actions d'orchestration, etc). Les changements d'étiquette de stabilité sont décrits dans la description correspondante de l'étiquette git. Les étiquettes de stabilité suivent[versionnement sémantique](https://semver.org/).
Nous vous encourageons fortement à n'utiliser des images qu'avec des étiquettes de stabilité.
Traduit avec www.DeepL.com/Translator (version gratuite)

## Maintenance

Nous mettons régulièrement à jour les images utilisées dans cette pile et les publions ensemble, voir[page des versions](https://github.com/wodby/docker4drupal/releases) pour le journal complet des modifications et les instructions de mise à jour. La plupart des mises à jour de routine pour les images et ce projet ont été effectuées par[the bot](https://github.com/wodbot) via des scripts situés sur[wodby/images](https://github.com/wodby/images).

## Au-delà de l'environnement local

Docker4Drupal est un projet conçu pour vous aider à créer un environnement local avec docker-compose. Si vous voulez déployer une pile cohérente avec orchestrations sur votre propre serveur, allez voir[Drupal stack](https://wodby.com/stacks/drupal) sur Wodby ![](https://www.google.com/s2/favicons?domain=wodby.com).

## Etapes de mise en place

* Télécharger / Cloner le projet dans un répertoire
* Modifier le fichier des variables d'environnement (.env)
* Modifier le fichier de configuration .yml (docker-compose.yml)
* Adapter les volumes selon l'emplacement de votre Drupal
* Démarer le serveur Docker avec la commande (docker-compose up -d)
* Accéder à votre site se type d'URL : PROJECT_BASE_URL:PORT_TRAEFIK


## Autres projets Docker4x

* [docker4php](https://github.com/wodby/docker4php)
* [docker4wordpress](https://github.com/wodby/docker4wordpress)
* [docker4ruby](https://github.com/wodby/docker4ruby)
* [docker4python](https://github.com/wodby/docker4python)

## Licence d'utilisation

Ce projet est licencié sous la licence open source du MIT.

[Apache]: https://wodby.com/docs/stacks/drupal/containers#apache
[AthenaPDF]: https://wodby.com/docs/stacks/drupal/containers#athenapdf
[Blackfire]: https://wodby.com/docs/stacks/drupal/containers#blackfire
[Drupal node]: https://wodby.com/docs/stacks/drupal/containers#drupal-nodejs
[Drupal]: https://wodby.com/docs/stacks/drupal/containers#php
[Elasticsearch]: https://wodby.com/docs/stacks/elasticsearch
[Kibana]: https://wodby.com/docs/stacks/elasticsearch
[Mailhog]: https://wodby.com/docs/stacks/drupal/containers#mailhog
[MariaDB]: https://wodby.com/docs/stacks/drupal/containers#mariadb
[Memcached]: https://wodby.com/docs/stacks/drupal/containers#memcached
[Nginx]: https://wodby.com/docs/stacks/drupal/containers#nginx
[Node.js]: https://wodby.com/docs/stacks/drupal/containers#nodejs
[OpenSMTPD]: https://wodby.com/docs/stacks/drupal/containers#opensmtpd
[PHP]: https://wodby.com/docs/stacks/drupal/containers#php
[PostgreSQL]: https://wodby.com/docs/stacks/drupal/containers#postgresql
[Redis]: https://wodby.com/docs/stacks/drupal/containers#redis
[Rsyslog]: https://wodby.com/docs/stacks/drupal/containers#rsyslog
[Solr]: https://wodby.com/docs/stacks/drupal/containers#solr
[Varnish]: https://wodby.com/docs/stacks/drupal/containers#varnish
[Webgrind]: https://wodby.com/docs/stacks/drupal/containers#webgrind
[XHProf viewer]: https://wodby.com/docs/stacks/php/containers#xhprof-viewer

[_/traefik]: https://hub.docker.com/_/traefik
[arachnysdocker/athenapdf-service]: https://hub.docker.com/r/arachnysdocker/athenapdf-service
[blackfire/blackfire]: https://hub.docker.com/r/blackfire/blackfire
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[portainer/portainer]: https://hub.docker.com/r/portainer/portainer
[selenium/standalone-chrome]: https://hub.docker.com/r/selenium/standalone-chrome
[wodby/adminer]: https://hub.docker.com/r/wodby/adminer
[wodby/apache]: https://github.com/wodby/apache
[wodby/drupal-node]: https://github.com/wodby/drupal-node
[wodby/drupal-php]: https://github.com/wodby/drupal-php
[wodby/drupal]: https://github.com/wodby/drupal
[wodby/elasticsearch]: https://github.com/wodby/elasticsearch
[wodby/kibana]: https://github.com/wodby/kibana
[wodby/mariadb]: https://github.com/wodby/mariadb
[wodby/memcached]: https://github.com/wodby/memcached
[wodby/nginx]: https://github.com/wodby/nginx
[wodby/node]: https://github.com/wodby/node
[wodby/opensmtpd]: https://github.com/wodby/opensmtpd
[wodby/postgres]: https://github.com/wodby/postgres
[wodby/redis]: https://github.com/wodby/redis
[wodby/rsyslog]: https://hub.docker.com/r/wodby/rsyslog
[wodby/solr]: https://github.com/wodby/solr
[wodby/varnish]: https://github.com/wodby/varnish
[wodby/webgrind]: https://hub.docker.com/r/wodby/webgrind
[wodby/xhprof]: https://hub.docker.com/r/wodby/xhprof
