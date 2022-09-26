# Vulnerability Description

Chipolo's access sharing functionality has a vulnerability. A trusted owner can remotely share Chipolo access to another user, who may be a potential attacker. The attacker's mobile phone operating system is untrusted and the attacker can extract the Chipolo authentication secret from the mobile app, and possibly reuse it to control the Chipolo device even after the trusted owner has revoked the attacker's access from the server side.
