## Messenger Integration
#### Installation
The easiest way to install this integration is to use KPM.
```sh
/kpm install messenger
```

#### Configuration
To add a configuration, execute each of the following commands (replace each of the angle bracketed strings with the respective information):
```sh
/kpm config messenger commandPrefix "/"
/kpm config messenger key "<path to TLS key, eg key.pem>"
/kpm config messenger cert "<path to TLS cert, eg cert.pem>"
/kpm config messenger ca "<path to TLS ca cert, eg cert.pem - note NOT full chain>"
/kpm config messenger token "<messenger API token>"
/kpm config messenger verify "<verify secret message>"
/kpm config messenger port <port number>
```

#### Running
To run Messenger, either run `node main.js messenger` when starting Concierge or run `/kpm start messenger` when Concierge is running.

#### Notes
- To obtain a TLS certificate easily, the Lets Encrypt project has [easy ways of doing this](https://letsencrypt.org/getting-started/).
- Currently messenger bots cannot be run in group chats due to limitations at Facebooks end.
- To obtain a token and verify with a webhook, refer to the messenger section of [http://developer.facebook.com](http://developer.facebook.com).
- Messages the bot send cannot be longer than 320 characters each. So to deal with this we split up messages, this causes commands such as `help` to load really slowly...
