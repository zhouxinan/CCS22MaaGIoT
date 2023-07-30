# Tile MaaG IoT Attack

# Vulnerability Description

Tile's access sharing functionality has a vulnerability. A trusted owner can remotely share Tile access to another user, who may be a potential attacker. The attacker's mobile phone operating system is untrusted and the attacker can extract the Tile authentication secret from the mobile app, and possibly reuse it to control the Tile device even after the trusted owner has revoked the attacker's access from the server side.

# Vendor report
We reported the issues to the vendor in a timely manner. Unfortunately, we still did not manage to obtain any clearance from the vendor to release a CVE.

# Credits
Xin'an Zhou, UC Riverside; Jiale Guan, Indiana University Bloomington; Luyi Xing, Indiana University Bloomington; Zhiyun Qian, UC Riverside.
