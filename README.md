# BackupToDropbox
Code and configuration to backup systems like Leviathan to Dropbox.
# Background
Backing up a linux system to Dropbox can be a challenge becuase the easy backup systems tend to create backups which are not readable by standard users, but Dropbox needs read/write access to synchronize with Dropbox.
# Basic Idea
Script creates a collection of tar files of the system in the dropbox folder owned by the dropbox user.  Tar is chosen to preserve the original owner/group for the file/directories.  The script manages backup expiration.
# PseudoCode
```
su DropboxUser touch systemBackup-$Date
backup system > systemBackup-$Date
expire old backups
```
