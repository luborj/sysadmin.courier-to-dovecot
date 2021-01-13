

1) Stop postfix and courier
```
systemctl stop postfix
systemctl stop courier-authdaemon
systemctl stop courier-imap
systemctl stop courier-imap-ssl
systemctl stop courier-pop
systemctl stop courier-pop-ssl
```

2) Install dovecot
```
apt-get install dovecot-core dovecot-imapd dovecot-lmtpd dovecot-mysql dovecot-pop3d dovecot-sieve
apt-get remove courier-base courier-imap courier-imap-ssl courier-pop courier-pop-ssl courier-authlib-userdb courier-authlib-mysql courier-authlib courier-authdaemon
```
This will remove the courier packages automatically

3) Login to ISPConfig, go to System > Server config > mail and set:

POP3/IMAP Daemon: dovecot
Mailfilter Syntax: sieve

and click on save.

4) Create a remoting user, downlod the ispconfig courier to dovecot 
  migration script, adjust the values in it and run the script.
  
  ```php courier_to_dovecot.php```
  
5) Run a ispconfig update and select to reconfigure services.

6) Reconfigure squirrelmail








