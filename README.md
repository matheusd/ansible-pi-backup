# Backup Raspi Ansible Script

**NOTICE **

I ended up not using this because performance of borg sending to a remote raspi repo was subpar.

I ended up using [Rsync.net attic/borg storage](http://rsync.net/products/attic.html) as my backup provider.

I'm leaving this repo for posterity.


### Original Instructions

Used for setting up a RaspberryPI as a backup server for borg usage.

How to use it:

Setup a pi with raspbian.

Copy or link the public key of the "pi" admin user into data/pi-key.pub.

Setup the inventory file (either global or local - I usually run with a local file - see the sample).

If you have not yet setup your public key in the pi yet, run the script using `--ask-pass`. Otherwise, run without it.

Test to see if you can reach the pi:

    ansible -m ping -i inventory all

Run the top-level playbook:

    ansible-playbook pi-backup.yml -i inventory

That's it.