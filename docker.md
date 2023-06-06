## System (requires password) - blocked;  Forced to install in $HOME
> Need to manually add $HOME/.docker/bin to your PATH.

## Allow the default Docker socket to be used (requires password) - Blocked
> To ensure the Docker socket exists after restart, Docker Desktop sets up a launchd startup task that creates the symlink by running ln -s -f /Users/<user>/.docker/run/docker.sock /var/run/docker.sock. This ensures the user is not prompted on each startup to create the symlink. If the user does not enable this option at installation, the symlink and the startup task is not created and the user may have to explicitly set the DOCKER_HOST environment variable to /Users/<user>/.docker/run/docker.sock in the clients it is using. The Docker CLI relies on the current context to retrieve the socket path, the current context is set to desktop-linux on Docker Desktop startup.

## Allow privileged port mapping (requires password) - blocked
> Binding privileged ports that are less than 1024. The so-called “privileged ports” are not generally used as a security boundary, however OSes still prevent unprivileged processes from binding them which breaks commands like docker run -p 127.0.0.1:80:80 docker/getting-started.