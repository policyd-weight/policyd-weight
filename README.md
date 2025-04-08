### policyd-weight
 

Public repository of policyd-weight by Robert Felber

Policyd-weight is a postfix policy-server in order to score RBLs and bogus DNS-entries<br>
from HELO, MAIL FROM and IP at the RCPT TO-stage.

This allows to detect phishing or spam very early without receiving the complete mail.

Thus it reduces compute-intensive checks like amavis or rspamd and rejects the mail<br>
before DATA has been sent.
