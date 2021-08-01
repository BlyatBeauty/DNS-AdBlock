# DNS-AdBlock
This is a primarily YouTube-based blacklist for DNS-based adblockers such as pi-hole.

Honestly, I'm really just using this for my personal devices but if happens to help you out, then that's pretty cool!
If you happen to use this or fork this, feel free to let me know over at [@blyatbeauty](https://twitter.com/blyatbeauty) on twitter. 

This should definitely not be your only blocklist, and if this is your first exposure to DNS-based adblocking then my recommendations for good blocklists and regex filters will be placed at the bottom of this readme. If you have no idea what this is but you're interested, start [here](https://www.youtube.com/watch?v=KBXTnrD_Zs4).

## Contents of this repo:

The Youtube Blacklist primarily consists of google domains that have caused me issues. Unfortunately, due to the nature of YouTube's content delivery setup, the domains I blocked are not all of YouTube's ad domains. 
The Miscellaneous Blacklist consists of non-google domains that have tried to ruin my browsing experience. It borrows heavily from the default adlists from the Adblock app by Futuremind for iOS, and anything borrowed from there is specified via comments.



## Recommended Blacklists and More
### firebog.net
[An excellent place to start, especially on a fresh pi-hole install.](firebog.net)
Simply copy all the links that have a green tick (✔) into the Adlist group management tab on your pihole
In case you didn't know, you can paste multiple adlist links at once into the Adlist group management, which will make your life much easier.

### Regular Expressions (RegEx)
RegEx allows pihole to not just rely on your blocklists but also to automatically block websites as long as they meet certain criteria.
I don't do coding or anything on a regular basis so if you want a better explanation, find it on youtube or something.
These are considered the basic RegEx you should have in a fresh pi-hole install.

**You will have to copy these in one-by-one however**

    ^ad([sxv]?[0-9]*|system)[_.-]([^.[:space:]]+\.){1,}|[_.-]ad([sxv]?[0-9]*|system)[_.-]
    ^(.+[_.-])?adse?rv(er?|ice)?s?[0-9]*[_.-]
    ^(.+[_.-])?telemetry[_.-]
    ^adim(age|g)s?[0-9]*[_.-]
    ^adtrack(er|ing)?[0-9]*[_.-]
    ^advert(s|is(ing|ements?))?[0-9]*[_.-]
    ^aff(iliat(es?|ion))?[_.-]
    ^analytics?[_.-]
    ^banners?[_.-]
    ^beacons?[0-9]*[_.-]
    ^count(ers?)?[0-9]*[_.-]
    ^mads\.
    ^pixels?[-.]
    ^stat(s|istics)?[0-9]*[_.-]

### Pegasus Spyware Domains
AmnestyTech recently came out with a list of domains used by the Pegasus spyware that targets iOS devices.

**Even the most recent versions of iOS are able to be targetted!**

The link to the domain list is provided on the line below, simply paste it into your Adlist group management tab like you would any other adlist.

https://raw.githubusercontent.com/AmnestyTech/investigations/master/2021-07-18_nso/domains.txt
