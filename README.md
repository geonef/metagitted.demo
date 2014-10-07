# sysconf profile for gitted-gitted systems

[Gitted](https://github.com/geonef/sysconf.gitted) provides a way to import/export machine state.
In the usual case, a "gitted" system is an LXC container.

The **metagitted** profile is meant to import/export the set of LXC containers.
That is: a push-to-deploy solution for bringing up new guest services (LXC containers) and update them with ```git push```.

## How to setup

To enable the meta-gitted host (the one that runs LXC containers), you need to setup [Sysconf](https://github.com/geonef/sysconf.base/).

As root, setup sysconf from the [metagitted-demo](https://github.com/geonef/metagitted.demo) *sysconf* directory:
```
apt-get install curl
curl -L https://github.com/geonef/metagitted.demo/archive/master.tar.gz | tar xz -C / --strip-components=1
/sysconf/sysconf.base/tree/usr/bin/sysconf compile install update
```

Then, choose a directory somewhere from where you will administrate the meta-gitted system with git push and pull. There, clone the [metagitted-demo](https://github.com/geonef/metagitted.demo) repository:
```
git clone https://github.com/geonef/sysconf.metagitted.git
```

Then add the remote.
If it's a directory local to the metagitted system:
```
git remote add alhena "ext::gitted git-remote-command %S"
```

If it's from outside through SSH (replace ```metagitted.host.net``` with the host name):
```
git remote add metagitted "ext::ssh root@metagitted.host.net gitted git-remote-command %S"
```

You're done! Ready to make push and pulls...


## Push & pull

Suppose you want to import
```
git push metagitted master
```
