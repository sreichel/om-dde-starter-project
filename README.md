# OpenMage DDE-Starter-Project
A flexible docker based sample setup for [__OpenMage LTS__](https://github.com/OpenMage/magento-lts) based on [sandstein/docker-dev-environment](https://github.com/sandstein/docker-dev-environment).

## Installation

To easily follow sample files, it is recommended to install _docker-dev-environment_ and all your projects to `~/workspace`.

- `mkdir ~/workplace`

### Install requirements
- docker
- docker-compose
  
### Install _docker-dev-environment_
Follow [Initialisation and commands](https://github.com/sandstein/docker-dev-environment#initialisation-and-commands).
- `cd ~/workspace`
- `git clone git@github.com:sandstein/docker-dev-environment.git docker/dev-environment`
- `cd ~/workspace/docker/dev-environment`
- `ln -s ../.. vhosts`

### Install _OpenMage LTS_
- `cd ~/workspace`
- `git clone https://github.com/sreichel/OpenMage-Docker-Dev-Environment.git magento1/openmage`
- `cd ~/workspace/magento1/openmage`

#### Project configuration
Copy and adjust environment setting ...
- `cp docker/config/.env.sample .env`

Copy and adjust virtual host setting ...
- `cp docker/config/openmage.conf ~/workspace/docker/dev-environment/config/apache-24/conf.d/`

#### Start docker containers
- `dde-start`

#### Install composer inside docker container

Follow [Customizable bin commands in the PHP-CLI-Containers](https://github.com/sandstein/docker-dev-environment#customizable-bin-commands-in-the-php-cli-containers).

- `dde-cli bash`
- `cd /home/phpcli/bin`
- run composer install command

### Initial setup
Here you can add all you CLI commands to set up your project.

- create database <small>(already done)</small>
- import DB backups
- symlink media files
- run custom commands, e.g. `n98-magerun <command>`
- ... 

Adjust and run ...
- `dde-cli docker/init-dev-environment.sh`

<small>_(DB shema should be created and OpenMage should be installed to htdocs)_</small>

### Check setup

If everything worked http://openmage.localhost should show up _OpenMage_ installation wizzard page.

## ToDo
- optionally add sample data

## Thanks to
- @wilfriedwolf for _docker-dev-environment_
