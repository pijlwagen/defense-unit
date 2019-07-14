# Defense Unit (v3.2+)
**Note: v3 has not been released yet, but a beta version can be invited [here](https://discordapp.com/oauth2/authorize?client_id=576429735337263114&scope=bot&permissions=8)**
### Basic usage for users
Defense Unit is a Discord bot that provides information for ARK: Survival Evolved, from simple item recipes to a knockout calculator or
viewing a server.
### Commands
<> = required
[] = optional
- ,help [command] - Main entry point that shows a list of all commands, or information about a command.
- ,info - Shows information about the bot.
- ,tame <creature> [level], [multiplier] - Calculates and shows the taming stats for a creature.
- ,ko <creature> [level] - Calculates the knockout stats & weapon info to knock a creature out.
- ,map <ark> - Shows an image of the given map.
- ,kibble <type or creature> - Shows information for this kibble, you may use a creature to find the kibble type.
- ,craft <item> - Shows information needed to craft the given item.
- ,saddle <creature> - Shows the information needed to make the given saddle.
- ,ticket <args> - Open or close a ticket.
- ,config <args> - View or edit the server configuration.
- ,server <args> - View a server's information.

### Tickets
**For users**

If a server has tickets enabled, you can create a ticket by typing `,ticket open` in the #ticket-information channel.
A channel will will be created with you and the server staff where you can chat. You can close a ticket by typing `,ticket close` in the ticket channel.
If you close a ticket the bot will send a message with the transcript of the ticket and then delete the channel after 30 seconds.

**For server admins**

By default tickets are disabled in your server. You can enable them via `,config ticket enable` and disable them via `config ticket disable`.
If you enable tickets the bot will create a category with the name tickets, and nest a channel called #ticket-information. It will send a message in this channel with basic usage of the ticket command. **The bot needs Administrator permissions for tickets to work**
A role called `Ticket Manager` will be created too, anyone with this role will be granted access to all ticket channels. If any of these does not get created i recommend disabling the tickets, delte the created channel, category or role and re-enable the tickets.

### Config

The config command is based on the `Manage Server` permissions, so anyone with this permission can edit the server configuration.
To view the server configuration type `,config show`. This will return a list with available options and usage

**Options**
- show
  - Lists all the options and usage of them.
- set
  - Edit the taming level, multiplier or command channel.
    - level 
	  - This will set the default taming level, example: `,config set level 10`.
    - multiplier 
	  - This will set the default taming multiplier, example: `,config set multiplier 5`.
    - command 
	  - This will set the command channel, if set, commands can only be used in channels that start with the given value, example: `,config set command bot-commands`.
 - register
   - This will add the server to the database if it wasn't done automatically already, example: `,config register`.
 - ticket 
   - Enable or disable the ticket system in your server, default this will be disabled, example: `,config ticket enable`
     - enable 
	   - Enable the ticket system.
     - disable 
	   - Disable the ticket system.
 - server
   - Moved to [servers](#servers)

### Servers
The server command has been updated so it is able to support PC Xbox, Switch & Mobile. As server admin (Manage Server) you can add or delete servers.
###### Adding your server
I will explain this for both console and PC, let's start with PC first. If you want to make this 10x easier, you can use the premium server tool on our [dashboard](https://fortbots.xyz).

###### For PC:
First of all you need the server ID found on battlemetrics, head over to their [site](https://battlemetrics.com/servers/ark) and find your server. Open the server's page and check the URL, the URL should end with a few digits, for example ```https://www.battlemetrics.com/servers/ark/123456```. In this case `123456` is the server ID, now go back to discord and type `,config server add pc <The ID> [An optional server name]`. Without the <> and [] of course. If you did everything right it should say Successfully linked this server and you're all done! You can now check your server via `,server <name or id>`.

###### For other platforms:
Find the name of your server (Case-sensitive), type `,config server add <paltform you are on> <name>`, without the <>. Available platforms are: `xbox`, `mobile` and `switch` (Yes, There indeed is no PS4 support as the endpoint has not been found *yet*). Congratulations! You have now linked the server! You can view it via `,server <name>`

###### Deleting your server:
simply type `,config server delete <name or id>`

**Common problems**
1. The command does not work
   - Make sure your server is registered, the bot should do this automatically but if it didn't you can add your server manually by typing `,config register`.

### For developers
Defense Unit uses a public API which can be found [here](http://api.michel3951.com/documentation)
