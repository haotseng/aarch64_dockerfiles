## ARM64 Debian with SSHD

Build image :

    docker build -t ebspace/aarch64-debian-sshd:latest .


Start the image :

    docker run -d -p 22000:22 ebspace/aarch64-debian-sshd


Test the image :

    ssh -p 22000 root@localhost

The root password is  `root`


