# NightPI
Based on a Raspberry Pi 3B+ with Kali Linux installed, the "NightPi" is a briefcase that has been specially designed to learn and perform penetration testing, investigation (OSINT) and radio.
This repository contain all usefull explanation about how to make one, so don't hesitate to build for yourself this usefull tool and improve it :D

# Hardware

Here is the hardware that I've used. Feel free to choose them according to your specific needs (dimensions, more powerfull equipments...):

| **Raspberry Pi 3B+** | **64GB SD Card** | **Wired keyboard** | **External Hard Drive** | **Portable screen** |
| :---: | :---: | :---: | :---: | :---: |
|**RFID RC 522** | **RTL-SDR** | **Wireless module** | **Battery** | **USB/Jack cable** |
| **Powered USB hub** | **Fans** |  **Briefcase** | **Foldable headphone** |

**Cost estimated :** around 500 $


# Features
In order to be rapidly deployable, some features has been added :
- Offline database with documentation of many programs
- High security browser (protection against fingerprint + TOR proxy)
- Extra open-source tools installed (OSINT, SDR, etc)

## Offline database
<img src="https://github.com/Sekhan/NightPI/blob/master/HTTrack.jpg" alt="Offline Database" align="right" height="220px">

While Kali Linux come with a incredible amount of software, the issue is that if you want to learn how to use them, you'll need to rely on a internet connection and search for each documentation separately. **Centralizing all these usefull informations in one database by using a open source software like HTTrack is way more convenient :)**

Depending on each site, you may have to change some parameters. 
**Here is what I've modified in the option panel :**

- *Scan rules* (to prevent to download unwanted files) :
`+*.png +*.gif +*.jpg +*.jpeg
+*.css +*.js -ad.doubleclick.net/* -mime:application/foobar
-*.zip -*.tar -*.tgz -*.gz
-*.rar -*.z -*.exe -*.7z -*.pdf -*.xz -*.iso`

- *Build* : activate `No error page` and `No external page`
- *Link* : activate `Attempt to detect all links`, `Get non-html files related to a link`, `Test validity of all links`
and `Get HTML files first`
- *Log, index, cache* : activate `Force to store all files in cache`

To learn how to use it, I strongly recommand to have a look on the website : https://www.httrack.com/html/index.html

## Extra tools
Some interesting tools to perform OSINT and radio exploration has been added :
- <a href="https://github.com/TheYahya/sherlock">Sherlock </a> => A command-line tool that is used to scan many social network (like Facebook, Twitter, Tinder...) to find a user's account. All requests can be made over TOR.
- <a href="https://github.com/csete/gqrx">GQRX </a> => A software-defined radio that allow you to demodulate AM, FM and SSB and is compatible with many hardware (RTL-SDR, HackRF, BladeFR...).
- <a href="https://github.com/twintproject/twint">Twint </a> => This advanced Twitter OSINT tool allow you to scrap a user's Tweet, followers... without any API required.
- <a href="https://github.com/s0md3v/Photon">Photon </a> => A command-line tool that allow you to extract data of a website (subdomain, picture, email adress...).
- <a href="https://github.com/ggerganov/kbd-audio">Keytap </a> => Theses experimental tools can be used for analyzing mechanical keyboard input with microphone capture in order to predict the content of a written text.
- <a href="https://github.com/exiftool/exiftool">Exiftool </a> => A command-line tool that is used to analyze, modify and erase metadata in a wide variety of file (supported format include JPEG, PNG, DOC, MP4...).

## Enhanced security browser
Due to incompatibility of Tor Browser with Raspberry's architecture (ARM), **one possible alternative is to install Mozilla Firefox (ERS) and drastically renforced its security**. 

(1) The following **open-source add-on** has been added : <a href="https://addons.mozilla.org/fr/firefox/addon/ublock-origin/">uBlock Origin</a>, <a href="https://www.eff.org/privacybadger">Privacy Badger</a>, <a href="https://www.eff.org/https-everywhere">HTTPS Everywhere</a>, <a href="https://addons.mozilla.org/fr/firefox/addon/cookie-autodelete/">Cookie Autodelete</a>, <a href="https://decentraleyes.org/">Decentralised</a> and <a href="https://addons.mozilla.org/fr/firefox/addon/noscript/">Noscript</a>.

(2) To use **Firefox over TOR**, you need to set up a proxy in *Connection setting* : 
`SOCKS Host : 127.0.0.1`, `Port : 9050`, `SOCKS v5` and activate `Remote DNS`

(3) Regarding **fingerprint protection**, you'll have to configure `about:config` by your own, depending on the level of protection you need. Remember that theses modifications might break some websites and prevent them to load correctly.

Here are some usefull ressources to help you :
https://github.com/pyllyukko/user.js,
https://spyware.neocities.org/guides/firefox.html and
http://kb.mozillazine.org/Category:Security_and_privacy-related_preferences

Warning ! Fingerprint tracking techniques are very complex and new ones continue to be developped, <a href="https://arstechnica.com/information-technology/2017/02/now-sites-can-fingerprint-you-online-even-when-you-use-multiple-browsers/">as this example clearly illustrate</a> . You have to keep in mind that :
- The fact of non-giving a information (ex: disable `DOM storage`) can also be a information.
- The more you modified your browser, the more you will stick out from the masse
- Your browser value will remain fixed

(4) **By default, your browser trust 100 % of Certificate Authorities (CAs)**, which is <a href="https://blog.torproject.org/life-without-ca">a bad security practice</a> ! In addition to the risk of a MIMT ("Man In The Middle"), <a href="https://www.eff.org/deeplinks/2019/02/cyber-mercenary-groups-shouldnt-be-trusted-your-browser-or-anywhere-else">some shady companies are also seeking to become a top-level CA</a>.

# Further improvements
- [ ] More powerfull computer (Raspberry Pi alternative ?)
- [ ] Better range for WIFI and radio
- [ ] Full-disk encryption
