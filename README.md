Shussh
======

Secure HTTP (and everything else) Underpinned by SSH

SHUSSH-PRIVOXY
----

The Shussh-privoxy is intended for use on a system with privoxy installed.  

SETUP

* Specify values for '$TUNNEL_USER', '$TUNNEL_PORT', and '$TUNNEL_HOST'.  
* Confirm that your laptop's wireless adapter is identified as "wlan0" by ifconfig.  If it is named something else, change line 7 to reflect that fact.
* Copy the shussh-privoxy script to </etc/network/if-up.d/>.  Make sure that the script is executable by root.  
* Make sure that Privoxy's config file (/etc/privoxy/config) contains a socks5 forwarding rule pointing to the tunnel established by shussh-privoxy:
* '#        forward-socks5         /       127.0.0.1:<$TUNNEL_PORT in Shussh-privoxy> .'
* Configure all programs (especially web browsers and email clients) to use the proxy 127.0.0.1:<port on which Privoxy is listening>.  
