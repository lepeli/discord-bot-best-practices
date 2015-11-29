# Best practices for Discord bots

*NB: These will probably only apply for bots on large servers and/or on a large
number of servers. If your bot is specific to a small server, it doesn't at all
matter what you do.* If you have an idea for something that should be added,
please make a PR with your change! We can then discuss it there.

1. **Don't make scraping bots**. Scraping bots are bots that look for invites
   inside every message and then follow every invite they find, creating a sort
   of virus that spreads across servers. The head Discord dev (Stanislav) has
   stated that these bots are officially discouraged and there may be measures
   added to prevent them.

2. Consider **using highly unique prefixes** to trigger the bot. Common prefixes
   used include `!`, `$` and `.` (avoid these especially). Examples of unique
   prefixes are short words (`owl`), obscure Unicode characters not usually
   found on keyboards (`¨`), and, perhaps the most unique, @mentions specific
   to your bot. Additionally, if your bot is mainly a command-style bot, avoid
   making it respond to things that aren't commands.
