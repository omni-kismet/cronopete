# CRONOPETE

** IMPORTANT: Cronopete has been migrated to Gitlab **

https://gitlab.com/rastersoft/cronopete



A backup utility for Linux.

Cronopete is a backup utility for Linux, modeled after Apple's Time Machine. It aims to simplify the creation of periodic backups.

## BUILDING CRONOPETE

To build Cronopete, you need to install CMAKE or Ninja, Vala-0.30 or later, and Gtk 3.10 or later.

Now, type

    mkdir BUILD
    cd BUILD
    cmake ..
    make
    sudo make install

This will compile Cronopete.

## DBUS INTERFACE

Cronopete offers a DBus interface to allow a remote control. It is at the session bus, at the address **com.rastersoft.cronopete**. The object **com/rastersoft/cronopete** offers the **com.rastersoft.cronopete** interface, which has the follow methods:

* DoPing(Int32) -> Int32 : receives a 32bit integer and returns that integer plus 1. Useful for tests.
* DoBackup() : starts a backup now
* StopBakup() : ends the current backup
* ShowPreferences() : shows the preferences window
* RestoreFiles() : shows the restore interface
* RestoreFilesFromFolder(string folder) : shows the restore interface, setting it to show the specified folder. The folder can be passed as an URI (file:///...). This is useful for integration with file managers.
* UnmountBackupDisk : tries to unmount the backup disk. If it is not possible (because it is not mounted, or there is a backup in progress) it will return an error
* SetStatus(boolean) : enables or disables the backup process

## CONTACTING THE AUTHOR

Sergio Costas Rodriguez  
rastersoft@gmail.com  
http://www.rastersoft.com  
https://gitlab.com/rastersoft/cronopete.git  
