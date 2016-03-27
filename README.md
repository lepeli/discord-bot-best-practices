# Best practices for Discord bots


*NB: These guidelines are intended for bots running on public servers. If your
bot is restricted to private ones, this document likely doesn't apply to you.*

1. **Commands should be explicitly invoked**. Bots should not activate on
normal chat. Instead, use a command prefix or only respond when your bot is
directly @mentioned.
2. **Use unique prefixes**. Single-character prefixes such as `!`, `$` and `.`
are commonplace for activating commands and lead to overlaps with other bots.
Should you opt to use a prefix for your bot, consider using words (`owl`) or
unique Unicode characters (`¨`).
3. **Don't be greedy**. Restrict yourself to a small number of prefixes to
reduce the risk of collision with others.
4. **Don't scrape for invites**. Invite scraping, where a bot searches for
invites and blindly joins other servers, is officially discouraged by Discord.
Should a bot be reported, it may be banned or otherwise restricted. (An
alternative could be having a specific command that joins invites.)
5. **Don't overuse mentions**. If you reply directly to a command, don't use a
mention, they can lead to bot reply loops. Mentions are fine if a long running
command is executed, but private messages are a good alternative.
6. **Don't make the bot listen to its own messages**. If a bot has a command
that allows arbitrary output, and then somebody uses that command to trigger
itself again, an infinite loop can be created, which is unnecessary and
spammy.
7. **Have an `info` command**. It should provide information about the bot
such as what framework it is using and the used version, `help` commands and,
most importantly, who made it.
8. **Don't reply with "invalid command"**. If a user uses a command that does
not exist, then let it fail silently. Do not have it reply with something like
"invalid command". Though if the command is correct, but arguments are wrong
then it's okay to reply with "invalid args". The reason for this is if the bot
is in more than 1 server and there's another bot and they have conflicting
prefixes it becomes a problem as it's annoying.
9. **Be respectful of Discord's API**. Bots that abuse and misuse the Discord
API ruin things for everyone. Make sure to factor in rate-limiting and backoff
in your bot code, and be intelligent about using the API. Make sure to ask for
help if you're unsure about the right way to implement things.

If you have an idea for an addition or change to this document, please make a
pull request and we can discuss it.
