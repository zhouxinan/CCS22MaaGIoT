# CCS22MaaGIoT
Does your IoT device suffer from MaaG IoT attacks? Check out!

# Introduction
In the year of 2022, we found novel attacks for MaaG IoT devices. MaaG IoT devices (e.g., Bluetooth smart locks and Bluetooth item trackers) do NOT DIRECTLY connect to their respective IoT servers on the internet. Instead, they connect first to a user's mobile device using Bluetooth. Then, their respective companion apps dial SSL/TLS connections to the IoT servers to receive access control commands. We call this unique network architecture "Mobile-as-a-Gateway IoT". 

# Affected Vendors/Products
[Chipolo ONE](https://chipolo.net/en-us/products/chipolo-one) [[writeup]](https://github.com/zhouxinan/CCS22MaaGIoT/blob/main/ChipoloONE.md)

More products to come...

# Q&A
## Is my IoT device affected by the vulnerabilities?
IoT devices mentioned in the paper are affected. More generally, for IoT devices not mentioned in the paper, if their companion app dials TLS connections to their IoT servers and dials Bluetooth connections to the IoT device, your IoT device is likely to be affected. 

## How widespread are these vulnerabilities?
In our paper's Table 2, we record Google Play installation counts of the companion apps as of the publication date of the paper. Every researched app has around 10k+ to 5M+ installations, and the sum is more than 8 million installations. We did not count in Apple App Store installation numbers, and we could not enumerate all MaaG IoT devices on the market, so these vulnerabilities actually impact significantly more people/families than expected. 
