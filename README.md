# encrypted-dns-configs
Configuration profiles for [DNS over HTTPS](https://en.wikipedia.org/wiki/DNS_over_HTTPS) and [DNS over TLS](https://en.wikipedia.org/wiki/DNS_over_TLS). Check out the article for more info: [paulmillr.com/posts/encrypted-dns/](https://paulmillr.com/posts/encrypted-dns/) and info about [contributing a new profile](#contributing-a-new-profile).

### Caveats

DoH seems to work faster & better than DoT judging from the [Google's article](https://security.googleblog.com/2022/07/dns-over-http3-in-android.html).

Starting from iOS 15.5, [Wi-Fi captive portals](https://en.wikipedia.org/wiki/Captive_portal) in cafes, hotels, airports are exempted by Apple from eDNS rules; to simplify authentication. This is good news. There are still some other issues; we can't fix them, only Apple can:

- eDNS gets disabled: [Little Snitch & Lulu](https://github.com/paulmillr/encrypted-dns/issues/13), [VPN](https://github.com/paulmillr/encrypted-dns/issues/18)
- Some traffic is exempt from eDNS: [Terminal / App Store](https://github.com/paulmillr/encrypted-dns/issues/22), [Chrome](https://github.com/paulmillr/encrypted-dns/issues/19)

## Providers

`Censorship=yes` means the profile will not send true information about `hostname=IP` relation for some hosts.

| Name                      | Country | Censorship | Notes                                                                                                                                   | Install button                                                                                                                                                                                                      |
|---------------------------|---------|------------|-----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AdGuard Default           | 🇷🇺      | Yes          | [Operated](https://adguard-dns.io/kb/general/dns-providers/#default) by AdGuard (Filters ads, tracking & phishing)                                            | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-default-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-default-tls.mobileconfig)                                                                                                                           |
| AdGuard Family            | 🇷🇺      | Yes          | [Operated](https://adguard-dns.io/kb/general/dns-providers/#family-protection) by AdGuard (Filters Default + malware & adult content)                                       | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-family-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-family-tls.mobileconfig)                                                                               |
| AdGuard No Filter         | 🇷🇺      | No          | [Operated](https://adguard-dns.io/kb/general/dns-providers/#non-filtering) by AdGuard (Non-filtering)                                     | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-nofilter-https.mobileconfig),  [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-nofilter-tls.mobileconfig)                                                                                                                    |
| AliDNS                    | 🇨🇳      | Yes          | [Operated](https://www.alidns.com/) by Alibaba in China                                             | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alibaba-https.mobileconfig),  [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alibaba-tls.mobileconfig)                                    |
| Alekberg                  | 🇳🇱      | No          | [Independent](https://alekberg.net) hoster in Netherlands                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alekberg-https.mobileconfig)                                                                                                                          |
| BlahDNS CDN Filtered      | 🇺🇸      | Yes          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-cdn-adblock-doh1.mobileconfig)                                                                                                                          |
| BlahDNS CDN Unfiltered    | 🇺🇸      | No          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-cdn-unfiltered-doh1.mobileconfig)                                                                                                                          |
| BlahDNS Finland Adsblock  | 🇫🇮      | Yes          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-finland-doh.mobileconfig)                                                                                                                          |
| BlahDNS Germany Adsblock  | 🇩🇪      | Yes          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-germany-doh.mobileconfig)                                                                                                                          |
| BlahDNS Japan Adsblock    | 🇯🇵      | Yes          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-japan-doh.mobileconfig)                                                                                                                          |
| BlahDNS Singapore Adsblock| 🇸🇬      | Yes          | [Independent](https://blahdns.com/)                                                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-singapore-doh.mobileconfig)                                                                                                                          |
| BlahDNS Swiss Adsblock    | 🇨🇭      | Yes          | [Independent](https://blahdns.com/)                                                                               | [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-switzerland-dot.mobileconfig)                                                                                                                          |
| Canadian Shield Private   | 🇨🇦      | No          | [Operated](https://www.cira.ca/cybersecurity-services/canadian-shield/configure) by the Canadian Internet Registration Authority (CIRA) | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-private-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-private-tls.mobileconfig)     |
| Canadian Shield Protected | 🇨🇦      | Yes          | [Filters](https://www.cira.ca/cybersecurity-services/canadian-shield/configure) malware                                                 | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-protected-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-protected-tls.mobileconfig) |
| Canadian Shield Family    | 🇨🇦      | Yes          | [Filters](https://www.cira.ca/cybersecurity-services/canadian-shield/configure) malware & adult content                                 | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-family-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-family-tls.mobileconfig)       |
| Cloudflare                | 🇺🇸      | No          | [Operated](https://developers.cloudflare.com/1.1.1.1/dns-over-https) by Cloudflare 1.1.1.1                                              | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-tls.mobileconfig)                             |
| Cloudflare Malware        | 🇺🇸      | Yes          | Filters malware                                                                                                                         | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-malware-https.mobileconfig)                                                                                                                |
| Cloudflare Family         | 🇺🇸      | Yes          | Filters malware & adult content                                                                                                         | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-family-https.mobileconfig)                                                                                                                 |
| DNSPod                    | 🇨🇳      | Yes          | [Operated](https://www.dnspod.cn/Products/publicdns?lang=en) by DNSPod (Tencent) in China                                               | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dnspod-https.mobileconfig),  [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dnspod-tls.mobileconfig)                                                                                                                            |
| Google                    | 🇺🇸      | No          | [Operated](https://developers.google.com/speed/public-dns/docs/secure-transports) by Google                                             | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/google-https.mobileconfig),  [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/google-tls.mobileconfig)                                    |
| OpenDNS                   | 🇺🇸      | No          | [Operated](https://support.opendns.com/hc/en-us/articles/360038086532) by OpenDNS                                                       | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/opendns-https.mobileconfig)                                                                                                                           |
| OpenDNS Family            | 🇺🇸      | Yes          | Filters malware & adult content                                                                                                         | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/opendns-family-https.mobileconfig)                                                                                                                    |
| Quad9                     | 🇨🇭     | Yes          | [Operated](https://www.quad9.net/news/blog/doh-with-quad9-dns-servers/) by CleanerDNS, Inc. Filters malware                             | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-tls.mobileconfig)                                        |
| Quad9 With ECS            | 🇨🇭     | Yes          | [Operated](https://www.quad9.net/news/blog/doh-with-quad9-dns-servers/) by CleanerDNS, Inc. Filters malware                             | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-ECS-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-ECS-tls.mobileconfig)                                        |
| Tiar.app                  | 🇸🇬 🇺🇸    | Yes          | ["Privacy-first DNS provider"](https://doh.tiar.app) from SG, hosted on Digital Ocean. Filters malware                                  | [HTTPS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/tiarapp-https.mobileconfig), [TLS](https://github.com/paulmillr/encrypted-dns/raw/master/profiles/tiarapp-tls.mobileconfig)                                    |

## Installation

To make settings work across all apps in **iOS** & **MacOS**, you’ll need to install configuration profile. This profile would tell operating system to use DOH / DOT. Note: it’s not enough to simply set server IPs in System Preferences — you need to install a profile.

To install, simply open the file in GitHub by using Safari (other browsers will just download the file and won't ask for installation), and then click/tap on install button. The profile should download. On macOS, double click on the downloaded file to open it in settings, and approve instalation. On iOS, go to **System Settings => General => Profile**, select downloaded profile and tap the “Install” button.

## Signed Profiles

In the signed folder, we have *slightly outdated* signed versions of the profiles in this repository. These profiles have been signed by [@Candygoblen123](https://github.com/Candygoblen123) so that when you install the profiles, they will have a verified check box on the installation screen. It also ensures that these profiles have not been tampered with. However, since they were signed by a third party, they may lag behind their unsigned counterparts a little.

[comment]: <> (We recommend that you install a signed profile instead of an unsigned profile because it ensures that it was not modified while it was downloading.)

To verify resolver IPs and hostnames, compare mobileconfig files to their documentation URLs. Internal workings of the profiles are described on [developer.apple.com](https://developer.apple.com/documentation/devicemanagement/dnssettings). In order to verify signed mobileconfigs, you will need to download them to your computer and open them in a text editor, because signing profiles makes GitHub think that they are binary files.

## Contributing a new profile

Profiles are basically text files. Copy an existing one and change its UUID, for example, by generating a new one online. Make sure you update README with new profile's info.
