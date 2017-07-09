# Best practices for Discord bots


*NB: These guidelines are intended for bots running on public servers. If your
bot is restricted to private ones, this document likely doesn't apply to you.*

1. **Commands should be explicitly invoked**. Bots should not activate on
normal chat. Instead, use a command prefix or only respond when your bot is
directly @mentioned.
2. **Use unique prefixes**. Single-character prefixes such as `!`, `$` and `.`
are commonplace for activating commands and lead to overlaps with other bots.
Should you opt to use a prefix for your bot, consider using words (`owl`) or
unique Unicode characters (`¨`). Also, you should avoid using `#` or `@` as
prefixes since they can be used to mention a channel or a member.
Ideally, your bot's prefix should be configurable on a server-by-server
basis, so that the server owners can ensure every bot has its own unique
prefix of their choice.
3. **Don't be greedy**. Restrict yourself to a small number of prefixes to
reduce the risk of collision with others.
4. **Don't overuse mentions**. If you reply directly to a command, don't use a
mention, they can lead to bot reply loops. Mentions are fine if a long running
command is executed, but private messages are a good alternative.
5. **Have an `info` command**. It should provide information about the bot
such as what framework it is using and the used version, `help` commands and,
most importantly, who made it.
6. **Don't reply with "invalid command"**. If a user uses a command that does
not exist, then let it fail silently. Do not have it reply with something like
"invalid command". Though if the command is correct, but arguments are wrong
then it's okay to reply with "invalid args". If there is more than one bot in
a server that share a prefix, this can result in very obnoxious usage.
If your bot's prefix is configurable, this rule can probably be safely disregarded.
7. **Be respectful of Discord's API**. Bots that abuse and misuse the Discord
API ruin things for everyone. Make sure to factor in rate-limiting and backoff
in your bot code, and be intelligent about using the API. Make sure to ask for
help if you're unsure about the right way to implement things.
8. **Ignore both your own and other bots' messages**. This helps prevent infinite
self-loops and potential security exploits. Using a zero width space such as `\u200B`
and `\u180E` in the beginning of each message also prevents your bot from
triggering other bots' commands. The Discord API also tells you if a user is a bot
(`bot` property on `User` objects -
[see the reference](https://discordapp.com/developers/docs/resources/user#user-object)).
9. **Keep NSFW features locked to NSFW channels**.
All NSFW commands/features should only work in (Discord) NSFW-marked channels.
10. **Don't make a public eval command**.
Don't let people run code freely on your machine. Peoples can exploit and do everything on your machine.
If you have an idea for an addition or change to this document, please make a
pull request and we can discuss it.
