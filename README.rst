MediaServer - Simple Network Attached Media Storage
===================================================

TurnKey MediaServer makes it easy to bring all of your home videos, music,
and photos together into a single server that automatically converts and
streams your media on-the-fly to play on any device. This app integrates
`Emby`_ with a file management web app, Windows-compatible network file
sharing and other transfer protocols including SFTP, rsync, NFS, and
WebDAV. Files can be managed in private or public storage.

This appliance includes all the standard features in `TurnKey Core`_,
and on top of that:

- SSL support out of the box.

- Media server (`Emby`_) configurations:
   
   - Web UI listening on ports 8096 (http) and 8920 (https).
   - Preconfigured path substitution for Samba access
   - Preconfigured Music, Movies, TVShows, and Photos directories

- File server (`Samba`_) configurations:
   
   - Preconfigured wordgroup: WORKGROUP
   - Preconfigured netbios name: MEDIASERVER
   - Configured Samba and UNIX users/groups synchronization (CLI and
     Webmin).
   - Configured root as administrative samba user.
   - Configured shares:
      
      - Users home directory.
      - Public storage.
      - CD-ROM with automount and umount hooks (/media/cdrom).

- Webmin module for configuring Samba.
- Includes popular compression support (zip, rar, bz2).
- Includes flip to convert text file endings between UNIX and DOS
  formats.
- `WebDAV CGI`_ providing WebUI and WebDAV access.

- Access your files securely from anywhere via `WebDAV CGI`_:
   
   - Web GUI access to your files, with online previews of major formats and drag-n-drop
     support.
   - Pre-configured authentication (Samba).
   - Pre-configured repositories (storage, user home directories).

- Default storage: */srv/storage*
- Accessing file server via samba on the command line::

    smbclient //1.0.0.61/storage -Uroot
    mount -t cifs //1.0.0.61/storage /mnt -o username=root,password=PASSWORD

Credentials *(passwords set at first boot)*
-------------------------------------------

-  Emby webUI: username **emby**
-  Webmin, Webshell, SSH, Samba: username **root**
-  Web based file manager (WebDAV CGI):
   
   - username **root** (or Samba users)

.. _Emby: https://emby.media/
.. _TurnKey Core: https://www.turnkeylinux.org/core
.. _Samba: http://www.samba.org/samba/what_is_samba.html
.. _WebDAV CGI: https://github.com/DanRohde/webdavcgi

