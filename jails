vim /etc/fail2ban/jail.local
```
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
