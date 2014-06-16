## CannyOS Ubuntu Dockerfile


This repository contains the *Dockerfile* and *associated files* for setting up a container with Ubuntu for CannyOS

### Dependencies

* docker


### Installation

1. Install [Docker](https://www.docker.io/).

	For an Ubuntu 14.04 host the following command will get you up and running:

	`sudo apt-get -y update && sudo apt-get -y install docker.io && sudo ln -sf /usr/bin/docker.io /usr/local/bin/docker && sudo restart docker.io`

2. You can then build the container set from the via entering:

	Manual building can be done with the following:
	`sudo docker build -t="intlabs/cannyos-base-ubuntu-gtk3" github.com/intlabs/cannyos-base-ubuntu-gtk3`

	Two stage building should not be required but is avaliblible via:
	`bash <(curl -s https://raw.githubusercontent.com/intlabs/cannyos-base-ubuntu-gtk3/master/Build.sh)`

	
### Usage

* this will run and drop you into a session with privileges to run FUSE:

`sudo docker run -it --rm --privileged=true --lxc-conf="native.cgroup.devices.allow = c 10:229 rwm" intlabs/cannyos-base-ubuntu-gtk3`
