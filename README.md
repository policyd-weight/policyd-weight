### policyd-weight
 

Public repository of policyd-weight by Robert Felber

Policyd-weight is a postfix policy-server in order to score RBLs and bogus DNS-entries<br>
from HELO, MAIL FROM and IP at the RCPT TO-stage.

This allows to detect phishing or spam very early without receiving the complete mail.

Thus it reduces compute-intensive checks like amavis or rspamd and rejects the mail<br>
before DATA has been sent.


### installation (Linux)

1. Copy policyd-weight to /usr/bin/
2. Copy policyd-weight.conf to /etc/
3. Create a user polw
4. Create a systemd-unit-file that executes <b>/usr/bin/policyd-weight start</b> as user polw
5. Modify /etc/policyd-weight.conf to squit your needs
6. run systemctl start policyd-weight
