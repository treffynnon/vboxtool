VBoxTool currently consist only of a set of scripts. With this scripts, virtual 
machines of VirtualBox in a Linux headless server can be controlled. Start, stop, 
save, backup and show status of sessions in batch mode from the command line.

Usage and installation is tested only on Ubuntu. Please report if a specific 
function is not working in another environment, say OpenSUSE, Fedora, etc.

INSTALLATION
(Precede commands with 'sudo' when not operated as root)

* Place the main script script/vboxtool in /usr/local/bin
  Make it executable: chmod +x /usr/local/bin/vboxtool

* Place the init script script/vboxtoolinit in /etc/init.d
  Make it executable: chmod +x /etc/init.d/vboxtoolinit
  
* Activate the init script vboxtoolinit:
  update-rc.d vboxtoolinit defaults 99 10
  
* Create a folder /etc/vboxtool. In here, two config files have to be created, 
  type 'vboxtool help' for instructions.
  Create the configuration folder: mkdir /etc/vboxtool 

Note. To remove vboxtoolinit from autostart: update-rc.d -f vboxtoolinit remove

UPGRADING FROM 0.2

Sorry for breaking things here, but it's all in the name of naming consistency...

- Config folder is moved from /etc/vbox to /etc/vboxtool. Rename this folder.
- Main script 'vbox' is renamed to 'vboxtool'

USAGE

After installation, type 'vboxtool help' for more info.

KNOWN ISSUES

- Backup is not working as expected when using snapshots. When a snapshot is 
  present, the main vdi file is not copied, even if it's different from 
  previous backups. Problem is that once a snapshot is made, the main vdi 
  (according to info from 'VBoxManage showvminfo') is pointing to the snapshot 
  vdi instead of the expected, chained main vdi in the vdi folder.
  (Tracker #2132265)
  
See http://vboxtool.sourceforge.net for more details.    

