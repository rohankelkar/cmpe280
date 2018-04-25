# Install Mongodb (https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
```
brew install mongodb
sudo mkdir -p /data/db
sudo chmod 777 /data/db
```
you will see
```
2018-04-15T13:26:40.767-0700 I NETWORK  [initandlisten] waiting for connections on port 27017
```


# Install dependencies and run
```
npm install
npm run start
```

# Install Docker via Homebrew (https://stackoverflow.com/questions/40523307/brew-install-docker-does-not-include-docker-engine?answertab=active#tab-top)
1.  Install Docker.
```
  brew cask install docker
```
2.  Launch Docker.
  * Press Command + Space to bring up Spotlight Search and enter Docker to launch Docker.
  * In the Docker needs privileged access dialog box, click OK.
  * Enter password and click OK.
  * When Docker is launched in this manner, a Docker whale icon appears in the status menu. As soon as the whale icon appears, the symbolic links for `docker`, `docker-compose`, `docker-credential-osxkeychain` and `docker-machine` are created in ``/usr/local/bin`.
'''
    $ ls -l /usr/local/bin/docker*
    lrwxr-xr-x  1 susam  domain Users  67 Apr 12 14:14 /usr/local/bin/docker -> /Users/susam/Library/Group Containers/group.com.docker/bin/docker
    lrwxr-xr-x  1 susam  domain Users  75 Apr 12 14:14 /usr/local/bin/docker-compose -> /Users/susam/Library/Group Containers/group.com.docker/bin/docker-compose
    lrwxr-xr-x  1 susam  domain Users  90 Apr 12 14:14 /usr/local/bin/docker-credential-osxkeychain -> /Users/susam/Library/Group Containers/group.com.docker/bin/docker-credential-osxkeychain
    lrwxr-xr-x  1 susam  domain Users  75 Apr 12 14:14 /usr/local/bin/docker-machine -> /Users/susam/Library/Group Containers/group.com.docker/bin/docker-machine
  ```

  3.  Click on the docker whale icon in the status menu and wait for it to show Docker is running.
  ![Alt text](https://i.stack.imgur.com/yTOjR.png)
  ![Alt text](https://i.stack.imgur.com/KYhp8.png)

  4.  Test that docker works fine.
```
    $ docker run hello-world
    Unable to find image 'hello-world:latest' locally
    latest: Pulling from library/hello-world
    78445dd45222: Pull complete
    Digest: sha256:c5515758d4c5e1e838e9cd307f6c6a0d620b5e07e6f927b07d05f6d12a1ac8d7
    Status: Downloaded newer image for hello-world:latest

    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
     1. The Docker client contacted the Docker daemon.
     2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
     3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
     4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
     $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker ID:
     https://cloud.docker.com/

    For more examples and ideas, visit:
     https://docs.docker.com/engine/userguide/

    $ docker version
    Client:
     Version:      17.03.1-ce
     API version:  1.27
     Go version:   go1.7.5
     Git commit:   c6d412e
     Built:        Tue Mar 28 00:40:02 2017
     OS/Arch:      darwin/amd64

    Server:
     Version:      17.03.1-ce
     API version:  1.27 (minimum version 1.12)
     Go version:   go1.7.5
     Git commit:   c6d412e
     Built:        Fri Mar 24 00:00:50 2017
     OS/Arch:      linux/amd64
     Experimental: true
```
  5.  If you are going to use docker-machine to create virtual machines, install VirtualBox.
```
    brew cask install virtualbox.
```

    Note that if VirtualBox is not installed, then docker-machine fails with the following error.
```
    $ docker-machine create manager
    Running pre-create checks...
    Error with pre-create check: "VBoxManage not found. Make sure VirtualBox is installed and VBoxManage is in the path"
```
