## Automated install (Unix)
To install with curl run the following command:
```
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

### Install Utility to Generate UI Password
```
sudo apt install apache2-utils
```

### Generate Password Hash
```
htpasswd -B -n -b <USERNAME> <PASSWORD>
```
Go to `sudo nano /opt/AdGuardHome/dGuardHome.yaml` and change password hash whihc was generated with above command.
```
users:
 - name: username
   password: <HASH>
```


Official [Adgurad Docs](https://github.com/AdguardTeam/AdGuardHome)

