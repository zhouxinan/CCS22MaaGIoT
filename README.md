# Mobile-as-a-Gateway IoT Attacks
Do you know your smart lock can be hacked? Check out!

# Introduction
In the year of 2022, we found novel attacks for MaaG IoT devices. MaaG IoT devices (e.g., Bluetooth smart locks and Bluetooth item trackers) do NOT DIRECTLY connect to their respective IoT servers on the internet. Instead, they connect first to a user's mobile device using Bluetooth. Then, their respective companion apps dial SSL/TLS connections to the IoT servers to receive access control commands. We call this unique network architecture "Mobile-as-a-Gateway IoT". 

These devices allow access sharing, which means an owner can possibly invite other users (guests) to control their MaaG IoT device. However, this becomes an attack surface unfortunately. A guest user can thus modify their app logic (through dynamic instrumentation) to modify their MaaG IoT device's access control policies (which decide if a user can access the device), so that the guest user can escalate to owner privilege, maintain access to the device forever, etc.

# Publication
Perils and Mitigation of Security Risks of Cooperation in Mobile-as-a-Gateway IoT [[PDF1]](https://dl.acm.org/doi/10.1145/3548606.3560590) [[PDF2]](https://www.cs.ucr.edu/%7Ezhiyunq/pub/ccs22_iot.pdf)\
Xin'an Zhou, Jiale Guan, Luyi Xing, Zhiyun Qian\
Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications Security.\
**Pwnie Award Nomination for Most Under-hyped Research**

Dilemma in IoT Access Control: Revealing Novel Attacks and Design Challenges in Mobile-as-a-Gateway IoT [[Link]](https://www.blackhat.com/asia-23/briefings/schedule/index.html#dilemma-in-iot-access-control-revealing-novel-attacks-and-design-challenges-in-mobile-as-a-gateway-iot-31040) [[PDF]](http://i.blackhat.com/Asia-23/AS-23-Xing-Dilemma-In-IoT-Access-Control.pdf)\
Luyi Xing, Xin'an Zhou, Jiale Guan, Zhiyun Qian\
Black Hat Asia 2023

# Affected Vendors/Products
[Chipolo ONE](https://chipolo.net/en-us/products/chipolo-one) [[writeup]](https://maag-iot.xinanzhou.com/ChipoloONE)

[August](https://august.com/products/august-wifi-smart-lock) and [Yale Assure Lock Touchscreen](https://www.yalehome.com/us/en/products/keypads-and-smart-locks) [[writeup]](https://maag-iot.xinanzhou.com/August%26Yale)

[Level](https://level.co/products/lock) [[writeup]](https://maag-iot.xinanzhou.com/Level)

[Kwikset Aura](https://www.kwikset.com/aura) [[writeup]](https://maag-iot.xinanzhou.com/KwiksetAura)

[Tile](https://www.tile.com/products/tile-pro) [[writeup]](https://maag-iot.xinanzhou.com/Tile)

More products to come...

# Q&A
## Is my IoT device affected by the vulnerabilities?
IoT devices mentioned in the paper are affected. More generally, for IoT devices not mentioned in the paper, if their companion app dials TLS connections to their IoT servers and dials Bluetooth connections to the IoT device, your IoT device is likely to be affected. 

## How widespread are these vulnerabilities?
In our paper's Table 2, we record Google Play installation counts of the companion apps as of the publication date of the paper. Every researched app has around 10k+ to 5M+ installations, and the sum is more than 8 million installations. We did not count in Apple App Store installation numbers, and we could not enumerate all MaaG IoT devices on the market, so these vulnerabilities actually impact significantly more people/families than expected. 

## Can I notice that I was attacked?
No, possibly. The attacks allow surreptitious privilege escalations not easily noticeable to MaaG IoT device owners. Device owners should be careful not to share any access of their MaaG IoT devices to untrusted people to avoid getting attacked. 

## Are they design flaws?
Yes, they are design-level errors not easily patchable. Simply speaking, an MaaG IoT device uses a mobile device as a Bluetooth-to-TLS gateway. Without the protection of cryptographic communication protocols, an MaaG IoT device can suffer from untrusted modification of on-device access policies. 

## Are these vulnerabilities fixable? 
Unfortunately, they can not be easily fixed because MaaG IoT attacks exploit design-level errors. In our paper, we provide a novel cryptographic access control protocol as a more secure prototype design. It is likely that affected vendors have to follow such novel design to improve the security of their products. However, this can be cumbersome and may involve product software/firmware updates and/or recalls. 

## How did the vendors respond generally?
The vendors all responded very slowly. Almost all vendors spent more than one month for the establishment of a trusted communication channel. Some vendors were willing to collaborate but others were not. Some vendors even denied that the vulnerabilities existed for their products. Generally, the smart lock and the item tracker industry wanted to keep the failed designs a secret and did not want them to affect their fame. 
