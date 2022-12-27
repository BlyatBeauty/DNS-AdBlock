# DNS-AdBlock
This is a primarily YouTube-based blacklist for DNS-based adblockers such as pi-hole.

Honestly, I'm really just using this for my personal devices but if happens to help you out, then that's pretty cool!
If you happen to use this or fork this, feel free to let me know over at [@blyatbeauty](https://twitter.com/blyatbeauty) on twitter. 

This should definitely not be your only blocklist, and if this is your first exposure to DNS-based adblocking then my recommendations for good blocklists and regex filters will be placed at the bottom of this readme. If you have no idea what this is but you're interested, start [here](https://www.youtube.com/watch?v=KBXTnrD_Zs4).

This should be obvious but I have no connection to the Pi-Hole project, nor am I really an expert in this. I take no responsibility for your setup, this repo primarily exists for me to be able to quickly set up a pi-hole with my preferred settings.

## Contents of this repo:

The Youtube Blacklist primarily consists of google ad domains that have caused me issues. Unfortunately, due to the nature of YouTube's content delivery setup, blocking YouTube's ad domains is a hopeless endeavor. They keep making new domains, and blocking a specific domain can block actual YouTube content as well as ads, eventually giving me more trouble than it's worth.

If you want to block YouTube ads on your mobile device (iOS, Android), I suggest you look into sideloading a modified or tweaked YouTube app.

The Miscellaneous Blacklist consists of non-google domains that have tried to ruin my browsing experience. It borrows heavily from the default adlists from the Adblock app by Futuremind for iOS, and anything borrowed from there is specified via comments.

Simply copy the direct links to the file into your adblocker's adlists and you're good to go!

The Whitelist is just that, a list of domains I have allowed through my pi-hole. Some of these domains were either blocked by an overexcited regex filter, while some are simply necessary to maintain functionality of certain web services. Copy these to the whitelist section of your pi-hole much like you'd copy an adlist link into your gravity list. And yes, you can copy and paste the entire list in one go. I've seen some debate in forums over some of the domains I've included in my whitelist but my priority is to keep as much functionality of the web as possible while minimizing as many trackers and ads. If you disagree with a certain entry in the whitelist, feel free not to include it.

Similarly enough, Adlists and Barebones Adlists are just all the adlists I use in my setup. Simply copy paste them into the Adlists section of your Pi-Hole install. Barebones is the more relaxed blocklist, only blocking malware and to a lesser extent, Windows Telemetry, and should be used on clients that need a more relaxed blocklist.



## Recommended Blacklists and More
### firebog.net
[An excellent place to start, especially on a fresh pi-hole install.](firebog.net)
Simply copy all the links that have a green tick (✔) into the Adlist group management tab on your pihole.

In case you didn't know, you can paste multiple adlist links at once into the Adlist group management, which will make your life much easier.

### The Blocklist Project
[The Blocklist Project,](https://blocklistproject.github.io/Lists/) mush like firebog.net has a bunch of good adlists, preformatted to work with pretty much every format of DNS adblocker. Can't reccomend it enough.

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

**Even the most recent versions of iOS are able to be targeted!**

The link to the domain list is provided on the line below, simply paste it into your Adlist group management tab like you would any other adlist.

https://raw.githubusercontent.com/AmnestyTech/investigations/master/2021-07-18_nso/domains.txt
