# Post Stats
Here are examples of posting bot stats to the RBL API.

---

## Finding Your Bot API Token

(*REMEMBER:* your bot's API token is different from your bot's TOKEN, API token helps your bot to interact with RBL, while your bot's token interacts with Discord's servers)

Go to **Dashboard** -> **Your Bot** -> **API**
or go to: `https://bots.rovelstars.ga/dashboard/bots/[yourBotId]/api`
and replace `yourBotId` with your 18 character Discord Bot ID. 

---

## Bot Stats

Property  | Type
:---------|:------------
guildCount | Number

---

### JavaScript
`Browser`

```
const botId = '1345678910'; // your bot Snowflake ID
const botAPIToken = 'b344b2d1-8fd0-4ef7-b7d8-1567d4e337c7'; // your bot API token

fetch(`https://bots.rovelstars.ga/api/v1/bots/${botId}/stats`, {
  body: JSON.stringify({ guildCount: '100' }),
  headers: {
    'Authorization': botAPIToken,
    'Content-Type': 'application/json'
  },
  method: 'POST',
});
```
Make sure to update the code's guild count by recieving guild count from your discord api/module like **discord.js** or **Eris**.

---

### NodeJS

```
const fetch = require('node-fetch');
```

See [JavaScript Implementation](docs/post-stats/#javascript) above.

---

### Python

```
import requests

url = "https://bots.rovelstars.ga/api/v1/bots/[bot-id]/stats"
stat = {'guildCount': len(bot.guilds)}

x = requests.post(url, json = stat, headers = {
    "Authorization": "[code]"
})
print(x.status_code)

```
Please note that you need to change **[bot-id]** to your bot id, and **[code]** to your bot api token that you had got from RBL Dashboard.

Make sure to update the code's guild count by recieving guild count from your discord api/module like **discord.py**.

---

*If your code doesn't posts stats to our RBL api, feel free to inform us in our [Discord server](https://discord.gg/Rf3xPMm)*
---
*If you have any more examples to contribute, please join the [Discord Server](https://discord.gg/Rf3xPMm) and them to any of the ADMINS, MODS or APPROVERS*