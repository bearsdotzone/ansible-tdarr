# Deploy Tdarr with Ansible
Read my blog post at abneyonline.com/ansible-tdarr

## Usage
I hardcoded a goodly number of values because I don't actually expect anybody else to have such a ridiculous problem, so this part is as much a reminder for myself.

### rclone
Drop an rclone config in the same folder as this playbook.

### ansible
A local host needs no special configuration. A remote host needs wireguard specific configuration.

### wireguard
Set the environment variables `wg=wireguard-ip` and `wg_file=wireguard-conf` to update the docker compose and upload a wireguard configuration as appropriate. One necessitates the other.

### directories
The docker compose file is going to default to being stored in /home/bears
I hardcoded the google drive directory as /home/bears/gdrive and the nas nfs mount directory as /data.
For both of these you need to update the docker compose.
Changing the nfs location is easy, just update the auto.nfs section.
Changing the google drive location is more annoying, the .mount and .automount files need to be renamed appropriately.

