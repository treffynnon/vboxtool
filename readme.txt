VBoxTool currently consist only of a script. With this script, virtual 
machines of VirtualBox (virtualization solution) in a Linux headless 
server can be controlled. Start, stop, save, backup and show status of 
sessions in batch mode from the command line. A web server solution will be 
added later.

INSTALLATION

- copy to /usr/local/bin
- sudo chmod +x /usr/local/bin/vbox

USAGE

Type 'vbox help' for more info.

KNOWN ISSUES

- Backup is not working as expected when using snapshots. When a snapshot is 
  present, the main vdi file is not copied, even if it's different from 
  previous backups. Problem is that once a snapshot is made, the main vdi 
  (according to info from 'VBoxManage showvminfo') is pointing to the snapshot 
  vdi instead of the expected, chained main vdi in the vdi folder.

