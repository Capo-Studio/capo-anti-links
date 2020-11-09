# capo-anti-links

A package for discord anti-links support a lot of websites/domains.

## Installation

    npm install capo-anti-links

## Usage
```
const AntiLinks = require("capo-anti-links"),
  checkDomains = new AntiLinks("domains"),
  checkYouTube = new AntiLinks("youtube");
const Discord = require("discord.js");
const client = new Discord.Client();
client.on("ready", () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

client.on("message", async message => {
  if (!message.guild || !message.content) return;
  if (checkDomains.check(message.content) || checkYouTube.check(message.content)) {
    return message.delete();
  }
});

client.login("token");
   ```

#### Supported Websites/Domains

`discord` - `domains` - `facebook` - `google` - `http` - `youtube`

#### Filter

Filter constructor.

**Parameters**

-    `list` **[array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)** Instantiate filter with custom list
    

##### isProfaneLike

Determine if a single word is profane or looks profane.

**Parameters**

-   `word` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** String to evaluate for profanity.

##### replaceWord

Replace a word with placeHolder characters;

**Parameters**

-   `string` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** String to replace.

##### clean

Evaluate a string for profanity and return an edited version.

**Parameters**

-   `string` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Sentence to filter.

##### count

Count a string for profanity and return the count.

**Parameters**

-   `string` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Sentence to filter.

##### check

Check a string for profanity and return an Boolean value.

**Parameters**

-   `string` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Sentence to filter.



