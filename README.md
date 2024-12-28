# <p align=center>syno-ddns-gandi</p>
This is a fork of the very useful native Synology Gandi DDNS integration synology-ddns-gandi (https://github.com/EmixamPP/synology-ddns-gandi) by https://gitlab.gnome.org/emixampp 
This fork was intended to reuse the native approach but to add more than the root entry but also the mail and spf entries for mail smtp purpose.

## Installation
1. Connect to the NAS using ssh
2. Switch to root user: `sudo -s`
3. Install the module: 
   1. IPv4 only: `curl -w "\n" https://raw.githubusercontent.com/pmeves/syno-ddns-gandi/main/gandi.php > /usr/syno/bin/ddns/gandi.php`
   2. IPv4 + IPv6: `curl -w "\n" https://raw.githubusercontent.com/pmeves/syno-ddns-gandi/main/gandi_ipv6.php > /usr/syno/bin/ddns/gandi.php`
4. Update file permissions: `chmod 755 /usr/syno/bin/ddns/gandi.php`
5. Add it to the provider list: `curl -w "\n" https://raw.githubusercontent.com/pmeves/syno-ddns-gandi/main/ddns_provider.conf >> /etc.defaults/ddns_provider.conf`

## Setup
1. Obtain your Gandi personal access token (pat) from your Gandi account ([see doc](https://api.gandi.net/docs/authentication/)).
2. For example, if your your fully qualified domain name (fqdn) is: example.com 
3. And the subdomain that you want to redirect is all: @
4. Then fill the Synology DDNS configuration as follows:
      ![](.github/screenshots/example.png)

## :heart: Thanks to
* [Pinpin31](https://github.com/Pinpin31) for migrating the deprecated Api Key authentication to Personal Access Token.
* [EmixamPP](https://github.com/EmixamPP) for creating the original Gandi DDNS integration 
