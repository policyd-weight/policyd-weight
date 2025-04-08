Public repository of policyd-weight by Robert Felber

Policyd-weight is a postfix policy-server in order to score RBLs and bogus DNS-entries
from HELO, MAIL FROM and IP at the RCPT TO-stage.

Thus it reduces compute-intensive checks like amavis or rspamd and rejects the mail before
DATA has been sent.
