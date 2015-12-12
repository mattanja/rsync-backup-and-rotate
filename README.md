# rsync-backup-and-rotate

These scripts provide a simple way to run rsync and rotate the backups to keep copies of modified files.

The rotation is done with hardlinks, which means that the disk space is only used for multiple copies of
an unchanged file in multiple backup sets (daily, monthly, yearly). Only changed files contribute to the disk
space.

## Usage

Before using this script, you should have a functional SSH connection for the user
you're planning to use for the backup (can be root) using keys for authentication.
https://help.ubuntu.com/community/SSH/OpenSSH/Keys provides good information about
how to setup SSH key authentication.

### On Synology box (busybox system)

Busybox / Synology systems do not have bash installed (by default), but
"ash". To execute the scripts, you simply have to call ash to execute
the scripts.

Example to run script on home Synology to backup web server:

    ash /volume1/data/bin/rsync-backup-and-rotate/backup-rsync -e /volume1/data/bin/server-backup.excludelist -p /volume1/data/Data my.server.com &> /volume1/data/Data/server-backup-rsync.log

This script can be scheduled and executed via Task Scheduler (Control Panel/Task Scheduler, Create "User-defined script").

## Credits

The original version of these scripts have been created by Heinlein Support and were
published to the German Linux Magazine 09/2004.
https://www.heinlein-support.de/howto/backups-und-snapshots-von-linux-servern-mit-rsync-und-ssh
