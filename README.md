# WebWidgets
## ChatSurvey
Reads the chat of a Twitch channel and interprets messages consisting of numbers (e.g. “1”, “2”, “3”) as votes. The voting result is displayed as a bar chart. Only the first number of each user is accepted until a new vote is started. 

Config via URL-Parameters:
- `channel`: Name of Twich Channel you want to listen
- `min`: lowest accepted value for vote [default=1]
- `max`: highest accepted value for vote [default=5]
- `bg`: r,g,b,a value  for the background-color (0-255) and alpha (0-1). Default is transparent (0,0,0,0)
- `hidden`: 0: Not hidden or 1: hidden when loading the page. Visibility can be changed by chat commands.

You can click on the plot to open/close the config editor or edit the values manually. Embed the link like: `https://xanthognarh.github.io/WebWidgets/ChatSurvey.htm?channel=Channelname&min=1&max=5&bg=50,70,100,0.3`


Chat Commands:
- `!newvote`: Resets votes and user blacklist, shows the chart
- `!stopvote`: Disables new entries (freeze the current view)
- `!continuevote`: Allows new entries, old votes are still valid and the old user blocklist will be used. 
- `!resetvotingblacklist`: Allows all users to submit new votes. These votes are added to the old votes.
- `!hidevote`: Changes the visibility of the chart. Votes will be still counted.
- `!showvote`: Changes the visibility of the chart. Votes will be still counted.
