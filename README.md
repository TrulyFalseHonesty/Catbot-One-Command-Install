# Catbots-All-In-One-Install
## Installation
Open console and paste this:
```dep=""; [ ! -x $(command -v npm) ] && dep="npm $dep"; [ ! -x $(command -v firejail) ] && dep="firejail $dep"; [ ! -x $(command -v route) ] && dep="net-tools $dep"; [ ! -x $(command -v xhost) ] && dep="xorg-xhost $dep"; [ $dep != ""] && sudo pacman -S $dep && git clone https://github.com/nullworks/catbot-setup && cd catbot-setup && bash <(wget -qO- https://raw.githubusercontent.com/nullworks/One-in-all-cathook-install/master/install-all) && ./install-catbots && cd ~/.steam/steam/steamapps/common/Team\ Fortress\ 2/tf/maps && git clone --recursive https://github.com/nullworks/catbot-database && sudo chmod 755 -R . && mv catbot-database/nav\ meshes/* . && rm -rf catbot-database && cd - && sed -i '1!d' convert.js && 
echo "const fs = require("fs"); const DEST = "account-generator/accounts.cg.json"; var accounts = fs.readFileSync("accounts.txt").toString().split("\n"); fs.writeFileSync(DEST, "{\"array\":[", "utf8"); var parsedAccs = ""; var processedAccs = 0; parse(accounts[0]); parsedAccs = parsedAccs.substring(1); const l = accounts.length; for (let i = 1; i < l; i++) { parse(accounts[i]); if (processedAccs > 666) { processedAccs = 0; appendToDest(parsedAccs); parsedAccs = ""; } } if (parsedAccs) appendToDest(parsedAccs); appendToDest("],\"used\":0}"); function parse(auth) { let i = auth.indexOf(":"); if (i === -1) return; auth = [ auth.substring(0, i), auth.substring(i + 1) ]; parsedAccs += `,{"login":"${auth[0]}","password":"${auth[1]}","email":"${auth[0].toLowerCase()}@inboxkitten.com","community":true,"privacy":{"profile":3,"comments":3,"inventory":3,"gameDetails":3},"avatar":"https://i.imgur.com/avatar.png","summary":"summary","username":"${auth[0]}","created":1533672324,"steamID":"1234567891234567"}`; processedAccs++; }; function appendToDest(data) { fs.appendFileSync(DEST, data, "utf8"); }" >> convert.js && echo username:password >> accounts.js && echo EnJoY HaX Ya LiL CaT!```
## Cathook
To use the cheat, all you have to do is run:
```sudo ./attach```
## Catbots
The bots are a trickier to use, you first need a list of steam accounts.
Put them on the accounts.js file following the username:password format.
type ```./start``` to start the bots and ```./stop``` to stop them.
