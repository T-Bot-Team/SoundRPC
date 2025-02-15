# SoundRPC

### Overview
SoundRPC is a fork of the popular [discord-rpc](https://github.com/discordjs/RPC) package, tailored to assist internal projects with a focus on voice-related functions. By removing unwanted features, it reduces bloat and enhances performance.

### [Rich Presence Example](https://github.com/discordjs/RPC/blob/master/example)

### Importing the Package

#### ES5
```javascript
const rpc = require("@t_bot-team/discord-rpc");
const client = new rpc.Client({ transport: "ipc" });
```

#### ES6
```javascript
import rpc from "@t_bot-team/discord-rpc";
const client = new rpc.Client({ transport: "ipc" });
```

### Examples

#### Browser Example
```javascript
const clientId = '287406016902594560';
const scopes = ['rpc', 'messages.read'];

const client = new rpc.Client({ transport: 'websocket' });

client.on('ready', () => {
  console.log('Logged in as', client.application.name);
  console.log('Authed for user', client.user.username);

  client.selectVoiceChannel('81384788862181376');
});

// Log in to RPC with client id
client.login({ clientId, scopes });
```

#### IPC Example
```javascript
const clientId = '287406016902594560';
const scopes = ['rpc']; // For scopes, you will need to specify the clientSecret in the login options

const client = new rpc.Client({ transport: 'ipc' });

client.on('ready', () => {
  console.log('Logged in as', client.application.name);
  console.log('Authed for user', client.user.username);
});

// Log in to RPC with client id
client.login({ clientId, scopes });
```