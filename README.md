# SSL TASK DOCUMENTATION
## SETUP
- Logged into Azure and created a VM (**Ubuntu 22.04**)
- UserID: ashwin , Public IP: 4.240.109.79

This is the first time I'm using a VM, so its a bit confusing.

## SYSTEM UPDATES AND SECURITY
- Updated packages using 'sudo apt update'
- Configured unattended upgrades to be automatically done by system using 'dpkg-reconfigure -plow'

## SSH SECURITY
### SSH CONFIGURATION
- Disabled root login and password-based authentication by modifying '/etc/ssh/sshd_config' and setting corresponding fields to 'NO'
- Struggled a bit with the public key authentication.
    - Kept facing an error stating 'Permission denied(publickey)'. Fixed it ( was trying to match incorrect pair of keys.)
- Restricted SSH access to a range (4.240.109.) by modifying '/etc/hosts.allow/' file. Also denied all other users by modifying '/etc/hosts.deny' file.
- fail2ban setup done
-Accidentally ended up locking myself out.
