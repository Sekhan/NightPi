<h3 align="center"><img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/Title.jpg" alt="Title" height="70px"></h3>

<img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/Front.jpg" alt="Front" align="right" height="331px">

**Based on a Raspberry Pi 3B+ with <a href="https://docs.kali.org/introduction/what-is-kali-linux">Kali Linux </a> installed, the "NightPi" is a briefcase designed to learn and perform penetration testing, investigation (OSINT) and radio exploration.**

This repository contain usefull informations, in the hope you'll be inspired for a similar project :wink:

<p float="left">
  <img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/Briefcase.jpg" width="285" />
  <img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/Side.jpg" width="285" /> 
</p>

### Offline database

<img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/Features.jpg" alt="Features" align="right" height="215px">

While Kali Linux come with a incredible amount of software, if you want to learn how to use them, you'll need to rely on a internet connection and search for each documentation separately. **Centralizing all these usefull informations in one database by using a open source software like HTTrack is way more convenient :)**

For each site, you may have to change some parameters (especially in `limits` panel, depending on the structure of the website). 
**Here is the general options that you can apply :**

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

### Extra tools
Some interesting tools to perform OSINT and radio exploration has been added :
- <a href="https://github.com/TheYahya/sherlock">Sherlock </a> => A command-line tool used to scan many social network (like Facebook, Twitter, Tinder...) to find a user's account. All requests can be made over TOR.
- <a href="https://github.com/csete/gqrx">GQRX </a> => A software-defined radio that allow you to demodulate AM, FM and SSB and is compatible with many hardware (RTL-SDR, HackRF, BladeFR...).
- <a href="https://github.com/twintproject/twint">Twint </a> => This advanced Twitter OSINT tool allow you to scrap a user's Tweet, followers... without any API required.
- <a href="https://github.com/s0md3v/Photon">Photon </a> => A command-line tool that allow you to extract data of a website (subdomain, picture, email adress...).
- <a href="https://github.com/ggerganov/kbd-audio">Keytap </a> => Theses experimental tools can be used for analyzing mechanical keyboard input with microphone capture to predict the content of a written text.
- <a href="https://github.com/exiftool/exiftool">Exiftool </a> => A command-line tool used to analyze, modify and erase metadata in a wide variety of file (supported format include JPEG, PNG, DOC, MP4...).

Even if I wasn't able to install it, you might also have a look at <a href="https://github.com/martinmarinov/TempestSDR">this last program</a>. **Based on TEMPEST attack, <a href="https://cryptome.org/nsa-tempest.pdf">a technic discovered by the National Security Agency in the 70's</a>, this tool allow you to eavesdrop unintentional electromagnetic emanations** that come from cables carrying video signals and converted back into a live image of what is displayed on the screen.

### Enhanced security browser
Due to incompatibility of Tor Browser with Raspberry's architecture (ARM), **one possible alternative is to install Mozilla Firefox (ERS) and drastically renforced its security**. 

> (1) These **open-source add-on** has been added : <a href="https://addons.mozilla.org/fr/firefox/addon/ublock-origin/">uBlock Origin</a>, <a href="https://www.eff.org/privacybadger">Privacy Badger</a>, <a href="https://www.eff.org/https-everywhere">HTTPS Everywhere</a>, <a href="https://addons.mozilla.org/fr/firefox/addon/cookie-autodelete/">Cookie Autodelete</a>, <a href="https://decentraleyes.org/">Decentralised</a> and <a href="https://addons.mozilla.org/fr/firefox/addon/noscript/">Noscript</a>.

> (2) To use **Firefox over TOR**, you need to install it and set up a proxy in *Connection setting* : 
`SOCKS Host : 127.0.0.1`, `Port : 9050`, `SOCKS v5` and activate `Remote DNS`

> (3) Regarding **fingerprint protection**, you'll have to configure `about:config` by your own, depending on the level of protection you need. Remember that theses modifications might break some websites and prevent them to load correctly.

>> :wrench: Here are <a href="https://github.com/pyllyukko/user.js">some</a> <a href="https://spyware.neocities.org/guides/firefox.html">usefull</a> <a href="http://kb.mozillazine.org/Category:Security_and_privacy-related_preferences">ressources</a> for creating your own settings. Don't hesitate to also use <a href="https://panopticlick.eff.org/">theses</a> <a href="https://browserleaks.com/">tools</a> to test your browser security/fingerprint !

>> :warning: **Fingerprint tracking techniques are very complex** and new ones continue to be developped, <a href="https://arstechnica.com/information-technology/2017/02/now-sites-can-fingerprint-you-online-even-when-you-use-multiple-browsers/">as this example clearly illustrate</a>. **You have to keep in mind that :**
>> - The fact of non-giving an information (ex: disable `media.navigator.enabled`) can also be an information.
>> - The more you modified your browser, the more you will stick out from the masse
>> - Your browser value will remain fixed

> (4) **By default, your browser trust 100 % of Certificate Authorities (CAs)**, which is <a href="https://blog.torproject.org/life-without-ca">a bad security practice</a> ! In addition to <a href="https://www.eff.org/deeplinks/2011/05/syrian-man-middle-against-facebook">the risk of a MIMT</a> ("Man In The Middle")</a>, <a href="https://www.eff.org/deeplinks/2019/02/cyber-mercenary-groups-shouldnt-be-trusted-your-browser-or-anywhere-else">some shady companies are also seeking to be approved as a top-level CA</a>. <a href="http://patrol.psyced.org/">This extension</a> might help you to trust only a restricted number of CAs.

## Hardware
Here is the hardware that I've used. Feel free to choose them according to your needs (dimension, powerfull equipment...). 
**Cost estimated :** around 500 $

| **Raspberry Pi 3B+** | **64GB SD Card** | **Wired keyboard** | **External Hard Drive** | **Portable screen** |
| :---: | :---: | :---: | :---: | :---: |
|**RFID RC 522** | **RTL-SDR** | **Wireless module** | **Battery** | **USB cable** |
| **Powered USB hub** | **Fans** |  **Briefcase** | **Foldable headphone** | **Jack cable** |

<p align="center"><img src="https://github.com/Sekhan/NightPI/blob/master/Pictures/InsideF.jpg" alt="Inside" height="420px">

<p align="center">If you're interested about making one, here are some tips :

- **Try to privilege full-aluminium briefcase** instead of a plastic/aluminium mix (which, in addition, are often made with cardboard inside). It will probably be a bit more expensive, but more resistant and easier to work on.
- **Avoid using low-quality fixer like glue or nails**, prefer screws and nuts. Keep in mind that, if something needs to be fixed, you'll prefer to be able to easily disassembled it and work on it.
- **Check the voltage/amperage of your hardware, they will have an impact on your battery size !**
- **Draw a plan of the inside, including all component's size**. It is very important to make sure that you have enough space before buying everything, because you'll probably need more than expected.

## Further improvements
- [ ] Battery-capacity monitoring
- [ ] Full-disk encryption
- [ ] Better range for WIFI and radio
