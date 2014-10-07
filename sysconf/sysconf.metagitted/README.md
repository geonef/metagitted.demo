# sysconf profile for gitted-gitted systems

[Gitted](https://github.com/geonef/sysconf.gitted) provides a way to import/export machine state.
In the usual case, a "gitted" system is an LXC container.

The **metagitted** profile is meant to import/export the set of LXC containers.
That is: a push-to-deploy solution for bringing up new guest services (LXC containers) and update them with ```git push```.

## How to setup

To enable the meta-gitted host (the one that runs LXC containers), you need to setup [Sysconf](https://github.com/geonef/sysconf.base/).

As root:
```
apt-get install git
git init /sysconf
cd /sysconf

```
