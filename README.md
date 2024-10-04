# WebWidgets
A collection of Tools for more interaction with your Twitch chat. The tools can be embedded very easily in OBS as a browser source. No login or account required.
1. [ChatSurvey](#chatsurvey)
2. [Sublist](#sublist)

## ChatSurvey
Reads the chat of a Twitch channel and interprets messages consisting of numbers (e.g. “1”, “2”, “3”) as votes. The voting result is displayed as a bar chart. Only the first number of each user is accepted until a new vote is started. 
![Example Chart for a vote between a,b,c and d.](Examples/Xanthograph.png)

### Config via URL-Parameters:
- `channel`: Name of Twich Channel you want to listen
- `min`: lowest accepted value for vote [default=1]
- `max`: highest accepted value for vote [default=5]
- `bg`: r,g,b,a value  for the background-color (0-255) and alpha (0-1). Default is transparent (0,0,0,0)
- `hidden`: 0: Not hidden or 1: hidden when loading the page. Visibility can be changed by chat commands.

You can click on the plot to open/close the config editor or edit the values manually. Embed the link like: `https://xanthognarh.github.io/WebWidgets/ChatSurvey.htm?channel=Channelname&min=1&max=5&bg=50,70,100,0.3`


### Chat Commands:
- `!newvote`: Resets votes and user blocklist, shows the chart
- `!newvote min-max`: Resets votes and user blocklist, shows the chart and set range. Example for negative values: `!newvote -3--1`; Min/Max can be letters (case-insensitive)
- `!stopvote`: Disables new entries (freeze the current view)
- `!continuevote`: Allows new entries, old votes are still valid and the old user blocklist will be used. 
- `!voteagain`: Allows all users to submit new votes. These votes are added to the old votes.
- `!hidevote`: Changes the visibility of the chart. Votes will be still counted.
- `!showvote`: Changes the visibility of the chart. Votes will be still counted.

### Feature Ideas
- `!vote Text` e.g. Names

## Sublist
Shows a list of Subs/Bits for future interaction. The listet users can display a message using `!pick message`. After a timeout or `!RemoveUser username` this entry is removed. If there are multiple entries of one user, only the first entry will be removed.
![Example table of Subs](Examples/Xanthosub.png)

### Config via URL-Parameters:
- `channel`: Name of Twich Channel you want to listen
- `len`: max Number of Entries displayed [default=5]
- `bitprice`: Amount of Bits that equals 1 [default=300]
- `subprice`: Amount of Subs that equals 1 [default=1]
- `maxmessage`: max length of Message to be displayed [default=30]

Embed the link like: `https://xanthognarh.github.io/WebWidgets/sublist.htm?channel=channelname&len=3` 
If you want a background-color add this custom CSS in OBS: `table{background-color:rgba(255,255,255,0.4)}`
### Chat Commands:
- `!pick message`: Command for the person shown in table to send a Message
- `!pick username message`: Mod command to send a message instead
- `!AddUser username [amount][type]`: Add username to the queue, amount and type can be empty
- `!RemoveUser username [Pos=0]`: Removes the pos-th entry of the given user

### Feature Ideas
- `!Purgeuser`: Remove all entries of this user
- Sub Tiers have different value
- Localization
