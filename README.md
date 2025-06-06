### policyd-weight
 

Public repository of policyd-weight by Robert Felber

Status of the project: abandoned due to time constraints and health issues

Policyd-weight is a postfix policy-server in order to score RBLs and bogus DNS-entries<br>
from HELO, MAIL FROM and IP at the RCPT TO-stage. It is designed to run on a MX.

This allows to detect phishing, forged mail or spam very early without receiving the complete mail.

Thus it reduces compute-intensive checks like amavis or rspamd and rejects the mail<br>
before DATA has been sent.


### Installation (Linux, manually)

1. Copy [policyd-weight](https://github.com/policyd-weight/policyd-weight/raw/refs/heads/main/policyd-weight) to /usr/bin/
2. Copy [policyd-weight.conf](https://github.com/policyd-weight/policyd-weight/raw/refs/heads/main/policyd-weight.conf) to /etc/
3. Install dependencies, debian-based: libnet-dns-perl, libnet-ip-perl
4. Create a user polw
5. Create a systemd-unit-file that executes <b>/usr/bin/policyd-weight start</b>
6. Modify /etc/policyd-weight.conf to suit your needs
7. Run <b>systemctl start policyd-weight</b>
8. Check with <b>ps xa</b> whether policyd-weight runs
9. Add following to postfix' main.cf:

```
    smtpd_recipient_restrictions =
        permit_mynetworks,
        ...
        reject_unauth_destination,
        check_policy_service inet:127.0.0.1:12525
        ...
```

### Notes

There should be packages for debian, ubuntu, openSUSE, Solaris (OpenCSW), gentoo, FreeBSD (ports), NetBSD
