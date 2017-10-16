# *K*ey *R*einstallation *A*tta*ck*s (KRACK)

From the KRACK <a href="https://www.krackattacks.com/">website</a>:
> In a key reinstallation attack, the adversary tricks a victim into reinstalling an already-in-use key. This is achieved by manipulating and replaying cryptographic handshake messages. When the victim reinstalls the key, associated parameters such as the incremental transmit packet number (i.e. nonce) and receive packet number (i.e. replay counter) are reset to their initial value. Essentially, to guarantee security, a key should only be installed and used once. Unfortunately, we found this is not guaranteed by the WPA2 protocol. By manipulating cryptographic handshakes, we can abuse this weakness in practice.

## Unless a known patch has been applied, assume that all WPA2 enabled Wi-fi devices are attackable.

## Attacks that can be made (できること)
* Adversary can decrypt arbitrary packets.
  * This allows an adversary to obtain the TCP sequence numbers of a connection, and <a href="https://en.wikipedia.org/wiki/TCP_sequence_prediction_attack">hijack TCP connections</a>.
* Adversary can replay broadcast and multicast frames.
* Adversary can both decrypt and inject arbitrary packets. *(TKIP or GCMP ONLY)*
* Adversary can force the client into using a predictable all-zero encryption key. *(ANDROID 6.0+ and LINUX)*

## Attacks that can not be made (できないこと)
* Adversary can not recover WPA password.
* Adversary can not inject packets. *(AES-CCMP ONLY)*


# Vendor Response

| Vendor          | Official Response                                           | Comment                                                                                                                                                                                                                                                                           | Last Checked | Last Updated |
|-----------------|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|--------------|
| Android         | No Known Official Response                                  | Android 6.0 and above affected (Android uses wpa_supplicant and therefore is affected).                                                                                                                                                                                           | 2017-10-16   | 2017-10-16   |
| Apple           | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Buffalo / MELCO | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Cisco           | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Google          | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Huawei          | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Linksys         | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Linux           | No Known Official Response                                  | wpa_supplicant version 2.4 and above is affected. Linux's wpa_supplicant v2.6 is also vulnerable to the installation of an all-zero encryption key in the 4-way handshake.                                                                                                        | 2017-10-16   | 2017-10-16   |
| MediaTek        | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| Microsoft       | No Known Official Response                                  |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
| OpenBSD         | https://marc.info/?l=openbsd-announce&m=148839684520133&w=2 | This problem only affects OpenBSD clients. OpenBSD access points are unaffected. The problem has been fixed in -current. For 5.9 and 6.0 the following errata patches are available.                                                                                              | 2017-10-16   | 2017-10-16   |
| Ubiquiti        | No Known Official Response                                  | Ubiquiti has released 3.9.3.7537 in beta to mitigate these vulnerabilities.                                                                                                                                                                                                       | 2017-10-16   | 2017-10-16   |
| WiFi Alliance   | https://www.wi-fi.org/security-update-october-2017          | "Users should refer to their Wi-Fi device vendor’s website or security advisories to determine if their device has been affected and has an update available. As always, Wi-Fi users should ensure they have installed the latest recommended updates from device manufacturers." | 2017-10-16   | 2017-10-16   |
| Yamaha          | No Known Response                                           |                                                                                                                                                                                                                                                                                   | 2017-10-16   | 2017-10-16   |
