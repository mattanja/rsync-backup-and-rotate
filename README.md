# rsync-backup-and-rotate

These scripts provide a simple way to run rsync and rotate the backups to keep copies of modified files.

The rotation is done with hardlinks, which means that the disk space is only used for multiple copies of
an unchanged file in multiple backup sets (daily, monthly, yearly). Only changed files contribute to the disk
space.

## Credits

The original version of these scripts have been created by Heinlein Support and were
published to the German Linux Magazine 09/2004.
https://www.heinlein-support.de/howto/backups-und-snapshots-von-linux-servern-mit-rsync-und-ssh
