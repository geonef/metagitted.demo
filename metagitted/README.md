# Configuration of the Metagitted system

## NAME.guest

This directory contains one ```.guest``` file for each Gitted
sub-system (LXC container).

See the example ```demo.guest```.


## ipv4.forwarding.conf

This file configures the ```iptables``` forward rules.

It is needed for make a container service available from a public
interface from the host.
