# dyi-adblocker
An ad blocking chrome extension that blocks content based on domain names

# Installation
- Go to chrome://extensions/
- Enable Developer Mode
- Click Load upacked extension and navigate to the repo folder

# Updating the Blacklist
- Download a blacklist from  [github.com/StevenBlack/hosts](https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts) or create your own

- Convert the list into a javascript array:
  - $ `grep -v "0\.0\.0\.0 0\.0\.0\.0$" hosts | awk 'BEGIN{print "var blocked_domains = ["}/^0\.0\.0\.0/{printf "\"*://*.%s/*\",\n", $2
}END{print "];"}' > blocked_domains.js`
  - blocked_domains.js should be a valid JavaScript array that looks like this:
    ```
	var blocked_domains = [
	"*://*.01mspmd5yalky8.com/*",
	"*://*.0byv9mgbn0.com/*",
    ...
    ...
	"*://*.zukxd6fkxqn.com/*",
	"*://*.zy16eoat1w.com/*",
	];
    ```
  - Note: JavaScript allows a trailing comma for the last element of an array
 - Reload the extension

# Credits
The blacklist is from [github.com/StevenBlack/hosts](https://github.com/StevenBlack/hosts)
