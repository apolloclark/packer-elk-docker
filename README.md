# packer-docker

I rebuild my Docker images every week. You should too! 🧐

Gradle, Packer, Ansible, Serverspec, project to create Docker images for:
- Ubuntu 18.04
- Ubuntu 16.04
- Debian 10 Buster
- Debian 9 Stretch
- RHEL 8 UBI
- RHEL 7 UBI
- CentOS 7
- Amazon Linux 2

## Requirements

- [Gradle](https://gradle.org/install/#manually)
- [Packer](https://packer.io/)
- [Ansible](https://www.ansible.com/)
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
    - [Serverspec](https://serverspec.org/): gem install serverspec
    - [docker-api](https://github.com/swipely/docker-api/releases): gem install docker-api





## Install
```shell
git clone --recurse-submodules https://github.com/apolloclark/packer-python3
    git clone --recurse-submodules https://github.com/apolloclark/packer-prowler
    git clone --recurse-submodules https://github.com/apolloclark/packer-pacu
git clone --recurse-submodules https://github.com/apolloclark/packer-nodejs
    git clone --recurse-submodules https://github.com/apolloclark/packer-cloudsploit
git clone --recurse-submodules https://github.com/apolloclark/packer-ruby
git clone --recurse-submodules https://github.com/apolloclark/packer-openjdk
    git clone --recurse-submodules https://github.com/apolloclark/packer-tomcat
    git clone --recurse-submodules https://github.com/apolloclark/packer-es
    git clone --recurse-submodules https://github.com/apolloclark/packer-logstash

git clone --recurse-submodules https://github.com/apolloclark/packer-kibana
git clone --recurse-submodules https://github.com/apolloclark/packer-vault

git clone https://github.com/apolloclark/packer-docker
cd ./packer-docker

# add submodules
git submodule add https://github.com/apolloclark/gradle-build
git submodule add https://github.com/apolloclark/packer-build

# update submodules
git submodule update --recursive --remote

# set your Docker hub username, beats version, java version
export DOCKER_USERNAME="apolloclark" # $(whoami)
```
<br/><br/><br/>



## Support Matrix

<!--
|                   | Ubuntu | Ubuntu | Debian | Debian |  RHEL |  RHEL | CentOS | Amazon |
|                   |  18.04 |  16.04 |   10   |   9    |   8   |   7   |   7    |    2   | -->

|                   | Ubuntu<br/>18.04 | Ubuntu<br/>16.04 | Debian<br/>10 | Debian<br/>9 | RHEL<br/>8 | RHEL<br/>7 | CentOS<br/>7 | Amazon<br/>Linux<br/>2 |
|------------------:|:------:|:------:|:------:|:------:|:-----:|:-----:|:------:|:-----:|
|       **Python3** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|           Prowler |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|              Pacu |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|       **Node.js** |   ✓    |   ✓    |   ✓    |   ✓    |       |   ✓   |   ✓    |   ✓   |
|       Cloudsploit |   ✓    |   ✓    |   ✓    |   ✓    |       |   ✓   |   ✓    |   ✓   |
|          **Ruby** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|       **OpenJDK** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|            Tomcat |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|     Elasticsearch |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|          Logstash |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|        **Agents** |        |        |        |        |       |       |        |       |
|            Kibana |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|   HashiCorp Vault |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |

<br/><br/><br/>

## History

The following is a matrix of OS support and popularity of distros in deploy environments.

<!--
|                   | Ubuntu | Ubuntu | Debian | Debian |  RHEL |  RHEL | CentOS | Amazon |
|                   |  18.04 |  16.04 |   10   |   9    |   8   |   7   |   7    |    2   | -->
|                   | Ubuntu<br/>18.04 | Ubuntu<br/>16.04 | Debian<br/>10 | Debian<br/>9 | RHEL<br/>8 | RHEL<br/>7 | CentOS<br/>7 | Amazon<br/>Linux<br/>2 |
|------------------:|:------:|:------:|:------:|:------:|:-----:|:-----:|:------:|:-----:|
|       **Desktop** |   ✓    |   ✓    |        |        |       |       |        |       |
|     **Server VM** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |       |
|    **Amazon AWS** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |   ✓   |
|      **MS Azure** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |       |
|    **Google GCP** |   ✓    |   ✓    |   ✓    |   ✓    |   ✓   |   ✓   |   ✓    |       |
|        **Docker** |   ✓    |   ✓    |   ✓    |   ✓    |       |       |   ✓    |   ✓   |

Ubuntu 18.04 / 16.04 is the only Linux distro which is widely used and supported
on the widest range of deploy environments. Admittedly, Debian 10 / 9 and Alpine
are more popular within the Docker environment.


## Build
```
# Gradle, lint, build, test
./clean_packer_docker.sh
gradle testBaseImages --parallel --rerun-tasks
gradle testChildImages --parallel --rerun-tasks
# gradle test --parallel --rerun-tasks

screen -dmS packer gradle testBaseImages --parallel
ctrl + a d
screen -ls
screen -r

# Gradle, print taskTree / dependency graphy
gradle test taskTree --no-repeat --dry-run



# run a specific container
docker run -it $DOCKER_USERNAME/auditbeat:$(date -u '+%Y%m%d') /bin/bash

# run auditbeat, with necessary privs
docker run \
  --cap-add audit_control \
  --pid=host \
  --rm \
  --interactive \
  $DOCKER_USERNAME/auditbeat:$(date -u '+%Y%m%d') \
  test config -c /etc/auditbeat/auditbeat.yml

# run packetbeat, with necessary privs
docker run \
  --cap-add net_raw \
  --cap-add net_admin \
  --rm \
  --interactive \
  $DOCKER_USERNAME/packetbeat \
  test config -c /etc/packetbeat/packetbeat.yml

# run a test suite
rake spec

# push image

# delete ALL images on your system (including non Beat images)
docker system prune -af

```





## Architecture

- PCI / NYDFS, HITECH / HIPAA, FIPS / FedRAMP, etc. security compliance
regulations require upgrading a system within 30 days of a critical severity
vulnerability fix being available
- Docker image rebuilds should be automated
- Docker images should be rebuilt weekly
- Multiple builds should be parallelized
- Bash is tedious to write, maintain, debug, and terrible at parameterized service configuration
- Makefile format is only slightly more maintainable than Bash scripts
- Maven and Ant are decent, but are also outdated
- Dockerfiles are little more than wrappers around Bash, while Ansible / Puppet / Chef exist
- Ansible has the greatest support for popular services, most OSes, parameterized configuration, and test suites
- Packer is a great tool to build Docker images, using a JSON file, to call Ansible
- Goss is very popular for testing (3200+ stars vs. serverspec's 2200+ stars),
uses a simple YAML file, and does not require installing an additional
programming language dependency
- Jenkins, TravisCI, etc. require a third-party external service to run
- Gradle strikes a good balance between being command-line only, and parallelizable
- I chose to create a Jenkinsfile, to allow for quick adoption into existing 
Jenkins build pipelines





## Build Details

```shell
Beats, 6.5.4, 2018-12-19
https://github.com/elastic/beats/releases

Java, 11.0.4, 2019-07-16
https://en.wikipedia.org/wiki/Java_version_history
https://launchpad.net/~linuxuprising/+archive/ubuntu/java
https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa/+packages?field.name_filter=&field.status_filter=published&field.series_filter=xenial

Tomcat, 9.0.22, 2018-07-09
http://tomcat.apache.org/whichversion.html
https://tomcat.apache.org/tomcat-9.0-doc/changelog.html
https://github.com/docker-library/tomcat/blob/master/9.0/jre11/Dockerfile

Zookeeper, 3.4.13, 2018-06-15
https://zookeeper.apache.org/releases.html

Kafka, 2.1.1, 2019-02-15
https://kafka.apache.org/downloads

https://github.com/idealista/java-role
https://github.com/idealista/tomcat-role
https://github.com/idealista/zookeeper-role
https://github.com/idealista/kafka-role

https://github.com/elastic/elasticsearch-docker/tree/master/.tedi/template
https://molecule.readthedocs.io/en/latest/index.html

```
