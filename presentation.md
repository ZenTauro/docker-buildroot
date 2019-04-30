

# Contenedores


## Que son?

Aplicaciones empaquetadas en entornos aislados.


## Como funcionan?


### Cgroups

    mount --type cgroup

1.  cpu
2.  cpuacct
3.  cpuset  - bind to set of CPUs, NUMA nodes
4.  memory
5.  devices - creation read/write devices (mknod)
6.  freezer
7.  net<sub>cls</sub>
8.  blkio
9.  etc.


### Namespaces

    unshare

1.  Mount    - filesystem mount points
2.  UTS      - hostname and domainname
3.  IPC      - interprocess communication (IPC) resources
4.  PID      - PID number space
5.  Network  - network interfaces
6.  User     - UID/GID number spaces
7.  Cgroup   - cgroup root directory


### chroot

    chroot


## Runtimes

![img](./img/lxc.png)

-   First unprivileged

![img](./img/docker.svg)

![img](./img/rkt.svg)

![img](./img/systemd.png)


# Problemas


## Tamaño

    $ docker images | grep node
      node           latest 8672b25e842c 2 weeks ago   674MB
      node_defconfig latest 57b17e145fa8 8 seconds ago 16.5MB


## Tiempo de creación

    $ cat > Dockerfile << EOF
      FROM node:latest
      ADD  path/to/sampletext.js /usr/bin
      CMD  /usr/bin/node
      EOF
    $ time docker build .
      mucho tiempo

    $ cat > Dockerfile << EOF
      FROM node_defconfig:latest
      ADD  path/to/sampletext.js /usr/bin
      CMD  /usr/bin/node
      EOF
    $ time docker build .
      menos tiempo :)


# Docker \`FROM scratch\`

-   Minimización
-   ‎Manejo de dependencias


## Complejidad


# Buildroot


## Buildroot y contenedores


## Alternativas

-   Open Embedded
-   BitBake
-   YoctoProject
-   Buildroot


## Ventajas

-   Dependencias
-   Control granular de opciones


# Comandos

-   make savedefconfig
-   make ${target name}
-   make menuconfig
-   make clean / distclean
-   make source
-   make all
-   make


# Demo

    git clone https://git.digitales.cslabrecha.org/zentauro/buildroot_starter.git

