# CCS22MaaGIoT
Does your IoT device suffer from MaaG IoT attacks? Check out!

# Introduction
In the year of 2022, we found novel attacks for MaaG IoT devices. MaaG IoT devices (e.g., Bluetooth smart locks and Bluetooth item trackers) do NOT DIRECTLY connect to their respective IoT servers on the internet. Instead, they connect first to a user's mobile device using Bluetooth. Then, their respective companion apps dial SSL/TLS connections to the IoT servers to receive access control commands. We call this unique network architecture "Mobile-as-a-Gateway IoT". 

These devices allow access sharing, which means an owner can possibly invite other users (guests) to control their MaaG IoT device. However, this becomes an attack surface unfortunately. A guest user can thus modify their app logic (through dynamic instrumentation) to modify their MaaG IoT device's access control policies (which decide if a user can access the device), so that the guest user can escalate to owner privilege, maintain access to the device forever, etc.

# Publication
Perils and Mitigation of Security Risks of Cooperation in Mobile-as-a-Gateway IoT [[PDF]](https://www.cs.ucr.edu/%7Ezhiyunq/pub/ccs22_iot.pdf)\
Xin'an Zhou, Jiale Guan, Luyi Xing, Zhiyun Qian\
Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications Security.\
**Pwnie Award Nomination for Most Under-hyped Research**

# Affected Vendors/Products
[Chipolo ONE](https://chipolo.net/en-us/products/chipolo-one) [[writeup]](https://github.com/zhouxinan/CCS22MaaGIoT/blob/main/ChipoloONE.md)

[August](https://august.com/products/august-wifi-smart-lock) and [Yale Assure Lock Touchscreen](https://www.yalehome.com/us/en/products/keypads-and-smart-locks) [[writeup]](https://github.com/zhouxinan/CCS22MaaGIoT/blob/main/August%26Yale.md)

[Level](https://level.co/products/lock) [[writeup]](https://github.com/zhouxinan/CCS22MaaGIoT/blob/main/Level.md)

More products to come...

# Q&A
## Is my IoT device affected by the vulnerabilities?
IoT devices mentioned in the paper are affected. More generally, for IoT devices not mentioned in the paper, if their companion app dials TLS connections to their IoT servers and dials Bluetooth connections to the IoT device, your IoT device is likely to be affected. 

## How widespread are these vulnerabilities?
In our paper's Table 2, we record Google Play installation counts of the companion apps as of the publication date of the paper. Every researched app has around 10k+ to 5M+ installations, and the sum is more than 8 million installations. We did not count in Apple App Store installation numbers, and we could not enumerate all MaaG IoT devices on the market, so these vulnerabilities actually impact significantly more people/families than expected. 

## Can I notice that I was attacked?
No, possibly. The attacks allow surreptitious privilege escalations not noticeable to MaaG IoT device owners. 

## Are they design flaws?
Yes, they are design-level errors not easily patchable. Simply speaking, an MaaG IoT device uses a mobile device as a Bluetooth-to-TLS gateway. Without the protection of cryptographic communication protocols, an MaaG IoT device can suffer from untrusted modification of on-device access policies. 

## Are these vulnerabilities fixable? 
Unfortunately, they can not be easily fixed because MaaG IoT attacks exploit design-level errors. In our paper, we provide a novel cryptographic access control protocol as a more secure prototype design. It is likely that affected vendors have to follow such novel design to improve the security of their products. However, this can be cumbersome and may involve product software/firmware updates and/or recalls. 
