## Automated install (Unix)
To install with curl run the following command:
```
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

Go `sudo nano /etc/iptables/rules.v4` to Add Firewall rule and add below lines
```
-A INPUT -p udp --dport 53 -j ACCEPT
-A INPUT -p tcp --dport 53 -j ACCEPT
-A INPUT -p tcp -m state --state NEW -m tcp --dport 80 -j ACCEPT
-A INPUT -p tcp -m state --state NEW -m tcp --dport 443 -j ACCEPT
-A INPUT -p tcp -m state --state NEW -m tcp --dport 3000 -j ACCEPT
```

### You can control the service status with the following commands:
```
sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
```

### Install Utility to Generate UI Password
```
sudo apt install apache2-utils
```

### Generate Password Hash to Reset the Password
```
htpasswd -B -n -b <USERNAME> <PASSWORD>
```
Go to `sudo nano /opt/AdGuardHome/AdGuardHome.yaml` and change password hash which was generated with above command.
```
users:
 - name: username
   password: <HASH>
```


Official [Adgurad Docs](https://github.com/AdguardTeam/AdGuardHome)

