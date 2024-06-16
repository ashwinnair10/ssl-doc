# SSL TASK DOCUMENTATION
## SETUP
- Logged into Azure and created a VM (**Ubuntu 22.04**)
- UserID: ashwin.10 , Public IP: 4.240.76.39

This is the first time I'm using a VM, so its a bit confusing.

## SYSTEM UPDATES AND SECURITY
- Updated packages using 'sudo apt update'
- Configured unattended upgrades to be automatically done by system using 'dpkg-reconfigure -plow'

## SSH SECURITY
### SSH CONFIGURATION
- Disabled root login and password-based authentication by modifying '/etc/ssh/sshd_config' and setting corresponding fields to 'NO'
- Struggled quite a bit with the public key authentication.
    - Kept facing an error stating 'Permission denied(publickey)'. Trying to figure out what that is. 
  
  
