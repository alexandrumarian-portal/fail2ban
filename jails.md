Configure the Postfix, Dovecot, Roundcube jails : 

```
vim /etc/fail2ban/jail.local

[sshd]
enabled = true
port = 22
filter = sshd
logpath = /var/log/auth.log
maxretry = 3
bantime = 3hh
backend = %(sshd_backend)s
action = iptables-allports

[dovecot]
enabled         = true
port            = pop3,pop3s,imap,imaps,submission,465,sieve
logpath         = /var/log/mail.log
filter          = dovecot
maxretry        = 5
findtime        = 1200
bantime         = 21600
action          = iptables-allports


[postfix]
enabled         = true
mode            = more
port            = smtp,465,submission
logpath         = /var/log/mail.log
filter          = postfix
maxretry        = 3
findtime        = 1200
bantime         = 21600
action          = iptables-allports


[roundcube-auth]
enabled         = true
port            = http,https
logpath         = /var/www/webmail.example.com/html/logs/errors.log
filter          = roundcube-auth
maxretry        = 3
findtime        = 1200
bantime         = 21600
action          = iptables-allports
```

Useful commands:
```
systemctl status fail2ban.service
fail2ban-client reload
fail2ban-client status 
```
