# Best practices for Discord bots

1. **Don't make scraping bots**. Scraping bots are bots that look for invites inside every message and then follow every invite they find, creating a sort of virus that spreads across servers. The head Discord dev (Stanislav) has stated that these bots are officially discouraged and there may be measures added to prevent them.

2. Consider **using highly unique prefixes** to trigger the bot. Common prefixes used include `!`, `$` and `.` (avoid these especially). Examples of unique prefixes are short words (`owl`), obscure Unicode characters not usually found on keyboards (`¨`), and, perhaps the most unique, @mentions specific to your bot. Additionally, if your bot is mainly a command-style bot, avoid making it respond to things that aren't commands.
