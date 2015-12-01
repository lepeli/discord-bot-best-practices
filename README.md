# Best practices for Discord bots


*NB: These guidelines are intended for bots running on public servers. If your bot is restricted to private ones, this document likely doesn't apply to you.*

1. **Commands should be explicitly invoked**. Bots should not activate on normal chat. Instead, use a command prefix or only respond when your bot is directly @mentioned.
2. **Use unique prefixes**. Single-character prefixes such as `!`, `$` and `.` are commonplace for activating commands and lead to overlaps with other bots. Should you opt to use a prefix for your bot, consider using words (`owl`) or unique Unicode characters (`¨`).
3. **Don't be greedy**. Restrict yourself to a small number of prefixes to reduce the risk of collision with others.
4. **Don't scrape for invites**. Invite scraping, where a bot searches for invites and blindly joins other servers is officially discouraged by Discord. Should a bot be reported, it may be banned or otherwise restricted.

If you have an idea for an addition or change to this document, please make a pull request and we can discuss it.
