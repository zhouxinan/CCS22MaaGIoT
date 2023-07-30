# August and Yale MaaG IoT Attack

# Vulnerability Description
For affected August and Yale smart locks, after an owner invitee is invited to access the lock, the owner invitee can have his own offline key onto the lock. However, there
lacks a reliable protocol for the cloud to fully monitor the addition, existence, or revocation of such offline key. 

As a result, when the August/Yale device owner removes the owner invitee from the cloud, she could not track any offline keys left by the owner invitee or identify
any inconsistent policy states between the cloud and the lock.

# CVE Number
CVE-2022-26262

# Credits
Xin'an Zhou, UC Riverside; Jiale Guan, Indiana University Bloomington; Luyi Xing, Indiana University Bloomington; Zhiyun Qian, UC Riverside.
