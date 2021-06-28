<div align="center">

  <p>
    <a href="https://www.npmjs.com/package/discord-inline"><img src="https://img.shields.io/npm/v/discord-inline?maxAge=3600" alt="NPM version" /></a>
<a href="https://www.npmjs.com/package/discord-inline"><img src="https://img.shields.io/npm/dt/discord-inline?maxAge=3600" alt="NPM downloads" /></a>
  </p>

  <p>
    <a href="https://www.npmjs.com/package/discord-inline"><img src="https://nodei.co/npm/discord-inline.png?downloads=true&stars=true" alt="NPM Banner"></a>
  </p>
</div>

## Install
```sh
$ npm i discord-inline
```

**This Package is under the** [MIT LICENSE](https://opensource.org/licenses/MIT)

## Setup
```js
const discord = require('discord.js');
require('discord-inline'); //☣️ IMPORTANT: put this before your discord.Client()
const client = new discord.Client();
```

<h1>Discord.js</h2>

## Example
```js
const discord = require('discord.js');
require('discord-inline'); //☣️ IMPORTANT: put this before your discord.Client()
const client = new discord.Client();

client.on('ready', () => {
  console.log(client.user.tag)
});

client.on('message', async message => {
  if (message.content.startsWith('!reply')) {
    message.lineReply('Hey'); //Line (Inline) Reply with mention

    message.lineReplyNoMention(`My name is ${client.user.username}`); //Line (Inline) Reply without mention
  }
});

client.login('TOKEN');
```

## Embed
```js
if (message.content.startsWith('!reply')) {
  let embed = new discord.MessageEmbed()
  .setDescription(`Reply to ${message.author}`);

  message.lineReply(embed); //Line (Inline) Reply with mention or just like messenger app

  //or

  message.lineReplyNoMention(embed); //Line (Inline) Reply without mention
}
```

<h2 style="display:inline;">Edit</h2> <h4 style="display:inline;">(Async Function)</h4>

```js
if (message.content.startsWith('+ping')) {

  let m = await message.lineReply('Ping');

  let ping = (m.createdTimestamp - message.createdTimestamp);

  m.edit(`${ping}ms`)
}
```

## Command Handler
```js
/**
 * No need to define or put it
 * */
module.exports = {
  name: 'reply',
  category: 'Test',
  run: (client, message, args) => {
    message.lineReply('This is reply with mention');
  }
}
```

<hr>

## Donation

[PAYPAL](https://paypal.me/spikiie)