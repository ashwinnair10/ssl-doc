# SSL TASK DOCUMENTATION
## SETUP
- Logged into Azure and created a VM (**Ubuntu 22.04**)
- UserID: ``` ashwin ``` , Public IP: ``` 4.240.109.79 ```

This is the first time I'm using a VM, so its a bit confusing.

## SYSTEM UPDATES AND SECURITY
- Updated packages.
- Configured unattended upgrades to be automatically done by system using ``` dpkg-reconfigure -plow ```

## SSH SECURITY
### SSH CONFIGURATION
- Disabled root login and password-based authentication by modifying ``` /etc/ssh/sshd_config ``` and setting corresponding fields to 'NO'
- Struggled a bit with the public key authentication.
    - Kept facing an error stating ``` Permission denied(publickey) ```. Fixed it ( was trying to match incorrect pair of keys.)
- Restricted SSH access to a range (4.240.109.) by modifying ``` /etc/hosts.allow/ ``` file. Also denied all other users by modifying ``` /etc/hosts.deny ``` file.
- fail2ban setup done
- Accidentally ended up locking myself out after I enabled ufw without changing default rules(showed error with kex-exchange... and connection reset by peer).

Had to start over.

## New UserID: ``` ashwin ``` , Public IP:``` 4.213.195.41 ```
Completed tasks upto pubkeyauthentication. Turns out the error I faced earlier was also due to the hosts.allow and deny not working correctly. Even though I added my local IP to the ``` /etc/hosts.allow ``` and set other IPs to be denied in ```/etc/hosts.deny```, my Local IP also got denied. Trying to figure what went wrong. So skipping the IP restriction for now.
- fail2ban setup done.
- Added 'ssladmin@mediaserver' pubkey to ```~/.ssh/authorized_keys```

### Firewall and Network Security
#### Firewall Configuration
- Configured ufw to allow ssh,OpenSSH,http,https and port 2222
