# dyi-adblocker
An ad blocking chrome extension that blocks content based on domain names

# Installation
- go to chrome://extensions/
- enable Developer Mode
- click Load upacked extension and navigate to the repo folder

# Updating the Blacklist
- download a blacklist from  [github.com/StevenBlack/hosts](https://github.com/StevenBlack/hosts/blob/master/hosts.zip) or create your own
- convert the list into a Javascript Array.

- for the Steven's blacklist:
  - $ `grep "^0\.0\.0\.0" hosts | cut -d ' ' -f2 | sed 's/\([^\n]*\)/"*:\/\/*.\1\/*",/' > blocked_domains.js`
  - Now edit the first and last lines of blocked_domains.js so that it is a valid JavaScript array that looks like this:
    ```
    var blocked_domains = [
    "*://*.lb.usemaxserver.de/*",
    "*://*.tracking.klickthru.com/*",
    ...
    ...
    "*://*.zmedia.com/*",
    "*://*.zv1.november-lax.com/*"];
    ```
 - reload the extension

# Credits
The blacklist is from [github.com/StevenBlack/hosts](https://github.com/StevenBlack/hosts/blob/master/hosts.zip)
