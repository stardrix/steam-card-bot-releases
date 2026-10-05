# Steam Card Bot

[![Latest Release](https://img.shields.io/github/v/release/stardrix/steam-card-bot-releases?label=Latest%20Release&style=for-the-badge)](https://github.com/stardrix/steam-card-bot-releases/releases/latest)

> The ultimate **Steam card bot for a level up profile**. An automated Steam card set trading bot with a full desktop dashboard - supports multiple bots, live rate management, per-game withdrawals, and bot-initiated-only trade flow. Fully integrated with the #1 **Steam bot listing** directory.

**[Get a license](https://www.steamtradebots.com/) · [Join Discord](https://discord.gg/XCtgnPsZFU) · [Report an issue](https://github.com/stardrix/steam-card-bot-releases/issues)**

---

## Overview

Steam Card Bot is a Windows / Linux desktop application built on Electron. It connects one or more Steam bot accounts, manages your card set inventory automatically, and executes trades via Steam chat commands - the bot always sends the trade offer, keeping you in full control of every transaction.

### What it trades

| Item | Buy | Sell |
|---|---|---|
| Normal card sets | ✅ | ✅ |
| Foil card sets | ✅ | ✅ |
| Event card sets | ✅ | ✅ |
| TF2 Keys | ✅ | ✅ |
| Tour of Duty Tickets | ✅ | ✅ |
| CS2 Keys | ✅ | ✅ |
| Hydra Keys | ✅ | ✅ |
| Gems (Sack of Gems) | ✅ | ✅ |

---

## 🌐 The SteamTradeBots Ecosystem

To get the most out of your bot and build trust with your users, take advantage of our full ecosystem:

- **📈 Get Traffic (Bot Directory):** Don't just run a bot get customers! Submit your account to our official **[Steam Bot Listing](https://www.steamtradebots.com/)** to display your live stock and rates to thousands of users looking to level up their profiles.
- **🛡️ Build Trust (Chrome Extension):** Tell your customers to install the **[SteamTradeBots Verified Extension](https://chromewebstore.google.com/detail/steamtradebots-verified-b/ifbjmpaibhdfjemngaajlmijgopcaopk)**. It places a green "Verified Bot" banner directly on your bot's Steam profile, proving your legitimacy and protecting your users from impersonation scams.

---

## Key Features

**Chat Bridge (new in 3.0.0)** - let traders use your bots from Discord or Telegram, with one Discord bot for all of them, a channel per bot, and Steam chat quietened to a signpost.

- **Multi-bot support**:
run and manage multiple Steam bot accounts from one dashboard, each with its own credentials, rates, and inventory

- **Bot Overview**:
live grid showing every bot's status, trade count, uptime, and username at a glance; start or stop individual bots directly from the grid

- **Start All / Stop All**:
launch or shut down all configured bots in one click; failed bots are highlighted in red with the specific reason displayed

- **Bot-initiated trade flow**:
users interact via Steam chat commands; the bot always sends the trade offer so no unsolicited incoming offers are processed

- **Badge-aware set selection**:
the bot checks a user's Steam badge level before sending sets, so it only sends sets the user can still craft (respects the 5-level cap per game; 1-level cap for foil)

- **Verified complete sets**:
set sizes are validated against a daily-updated Steam badge database covering 15,000+ games, so buyers always receive full, craftable sets — partial stock is never sold as a set

- **Steam rate-limit resilience**:
smart inventory caching, spaced retries, serialized mobile confirmations with shared backoff, and a minimal background traffic profile keep trades flowing even when Steam throttles busy IPs — built with VPS hosting in mind

- **Safe with concurrent buyers**:
items in unaccepted outgoing offers are reserved, so two users buying at the same moment always receive different items — the second buyer never hits "items no longer available", and is politely asked to retry when reserved stock is the bottleneck

- **One active trade per user**:
a user with an open offer who orders again gets their existing offer link back instead of a duplicate offer — no trade-offer spam (admins are exempt)

- **Custom friend-list status**:
design the bot's "Now Playing" text with live placeholders like `{sets} sets - TF2 {buy_tf2}/{sell_tf2}` — stock and rates update in real time

- **One-click Support Report**:
a button in the Logs tab bundles version, OS, bot state, and recent logs (secrets always redacted) into a single report for fast support — errors carry short reference codes with plain-language explanations

- **SteamApis support**:
optionally route inventory loading through SteamApis.com (free tier available) to bypass Steam's per-IP rate limits entirely

- **Per-game withdraw**:
withdraw card sets from a specific game by AppID, with a searchable in-app game list so you never have to look up an AppID manually

- **Rate Simulator**:
preview exactly what the bot will send for any currency and quantity before going live; includes stock warnings if the bot doesn't have enough inventory

- **Live rate editing**:
change buy/sell rates and they apply to the running bot instantly, no restart needed

- **Listing integrations**:
automatic sync to SteamTradeBots.com, Steam.supply, and Steambot.info whenever rates change

- **Supply Feed**:
place your rates on the market ladder (undercut, low, mid, high, overcut) and let the bot keep them there automatically, inside a safety net of hard limits, a step limiter, feed sanity checks and a spread guard; per-currency follow, own bots never undercut each other

- **Steam browser version keeps itself current**:
Steam rejects trade confirmations from bots that claim an outdated browser version; the bot now checks the current Chrome version daily and tells you when a restart will apply a newer one, so this never silently breaks months after a release

- **Persistent trade history**:
full log of every accepted and declined trade, filterable by Today / 7 Days / 30 Days, survives restarts

- **Profit tracking**:
net profit per currency tracked per bot

- **Maintenance**:
auto-manage friend lists, spam protection, ban detection, and cleanup schedules

- **Sack of Gems auto-unpack**:
when a gem trade requires fewer than 1,000 gems, the bot automatically unpacks only the minimum number of Sack of Gems needed to cover the exact amount - no manual unpacking required

- **Auto-update**:
new releases are downloaded and installed silently in the background

---

## How It Works

1. Install the app and activate your license
2. Add your Steam bot account credentials (username, password, shared secret, identity secret)
3. Set your buy and sell rates in the Rates tab
4. Start the bot - it logs into Steam, fetches inventory, and posts your listing
5. Users send a chat command like `!BUYTF2 2`; the bot calculates the sets, checks their badge level, and sends them a trade offer

Users **cannot** push trade offers directly to the bot. All trades originate from the bot, giving you complete control over what gets sent and when.

---

## Dashboard

Live overview of the active bot: status dot, card set stock, TF2 key and gem count, trades completed, uptime, last inventory sync, and active rates. Updates every 20 seconds while the bot is running.

![Dashboard](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Dashboard.png)

---

## Bot Overview

A live grid of all your configured bots. Each card shows:

- Status indicator (Online / Offline / Starting / Error)
- Trade count and uptime
- Steam username
- Start / Stop button for that individual bot

Errors are highlighted in red for 12 seconds so you can see at a glance which bot failed and why (missing credentials, wrong password, etc.) before the status resets to Offline.

![Bot Overview](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Overview.png)

---

## Bot Account

Configure per-bot Steam credentials and access settings:

| Field | Description |
|---|---|
| Steam Username | The bot account's login name |
| Steam Password | Account password (stored encrypted) |
| Steam Web API Key | Required for trade offer processing |
| Shared Secret | 2FA - the bot generates codes automatically |
| Identity Secret | Auto-confirms trades, no phone needed |
| Admin Steam IDs | These accounts bypass all rate checks |
| Owner Profile URL | Shown when users type `!OWNER` |

All secret fields are hidden behind a reveal toggle. Each bot stores its own copy of these settings independently.

![Bot Account](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Account.png)

---

## Bot Settings

Fine-tune how the bot behaves: card mode (normal, foil, or event cards), persona name, custom friend-list status text (live `{placeholder}` template for stock and rates), trade size limits, donation acceptance, inventory fetch method, advanced timing, blocked games, and per-game stock limits.

![Bot Settings](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Settings%20First%20haf.png)

![Bot Settings (continued)](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Settings%20sec%20haf.png)

---

## Commands

Enable or disable individual currencies and chat commands without restarting the bot. Toggle a currency off to fully disable it - the bot won't trade or respond to commands for it. Toggle individual commands off to block just that action while keeping the currency active.

![Commands](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Commands.png)

---

## Rates

Set how many card sets the bot gives or requires per unit of currency. Four key types supported: TF2 Keys, Tour of Duty Tickets, CS2 Keys, and Hydra Keys. Gems use a separate rate (gems per set).

| Direction | What it means |
|---|---|
| **BUY** (sets/unit) | Sets the bot sends to the user per currency unit the user gives |
| **SELL** (sets/unit) | Sets the user must give per currency unit the bot sends back |

Rate changes apply to the running bot instantly - no restart required.

### Rate Simulator

A built-in calculator at the bottom of the Rates tab lets you preview trade outcomes before going live:

1. Pick a currency (TF2, ToD, CS2, Hydra, or Gems)
2. Pick a direction (BUY or SELL)
3. Enter a quantity
4. Click **Simulate** - see exactly how many sets or keys the bot would send, with a warning if current stock is too low

![Rates](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Rates.png)

---

## Listings

Connect API keys for up to three listing services. Rates and stock sync automatically whenever you save changes.

| Service | What it does |
|---|---|
| SteamTradeBots.com | **(Recommended)** The #1 verified **Steam bot listing**. Posts bot status, all buy/sell rates, total card set stock, key/gem counts, and a full per-game set breakdown. Integrates with the STB Chrome Extension for verified profile banners. |
| Steam.supply | Posts buy/sell rates for TF2, CS2, Hydra, ToD keys and gems, current key/gem stock, and per-game set counts |
| Steambot.info | Posts buy/sell rates for TF2, CS2, Hydra, ToD keys and gems, and a full per-game set breakdown so buyers can see exactly which games you stock |

![Listings](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Listings.png)

---

## Supply Feed

Fetches live rates from the other card bots listed on SteamTradeBots.com and places your rates where you want them on the market. Apply by hand, or let the bot keep you there automatically, inside a safety net.

### Price Mode - a position on the market ladder

The market is tiered: cheap sets and premium sets sit side by side. Rather than a formula, you pick where to sit:

| Position | Where your rates land |
|---|---|
| **Off** | Manage rates by hand |
| **Undercut the cheapest bot** | Cheaper than everyone, by your offset |
| **Low** | Among the cheapest bots |
| **Mid-Low** | Between the cheap end and the middle |
| **Mid** | The middle of the market |
| **Mid-High** | Between the middle and the expensive end |
| **High** | Among the most expensive bots |
| **Overcut the most expensive bot** | Dearer than everyone, by your offset |

Your price side is placed at that point in the market, and the other side is set at the spread the bots around that point actually run. No position can ever cross (give more than you take back).

- **Adjust**: move both sides, only what you give, or only what you take.
- **Follow the market for**: tick the currencies the feed may touch (TF2, ToD and gems). Unticked currencies keep the rates you set by hand.
- **Offsets**: one per currency, used only by the two "cut" positions.

### Automatic updates

A per-bot switch, **off by default**. Switched on, the bot re-fetches the market on your interval while it is running and applies the suggestion itself, with the dashboard open or closed. Fetch Now and Apply keep working as before.

### The safety net

Every automatic run passes through these, so a market spike or a competitor's typo can never empty your bot:

| Net | What it does | Your control |
|---|---|---|
| **Hard limits** | Per currency: the most you will ever give and the least you will ever take | See *Hard limits* below |
| **Max change per update** | One run moves a rate at most this much | 1 to 50%, default 10; cannot be switched off |
| **Minimum bots to trust a rate** | A "market" of one bot is where typos live | 1 to 10, default 2 |
| **Ignore extreme rates** | Quotes far above or below the market median are dropped | On or off, default on |
| **Spread guard** | The bot will never give more per key than it takes back; a trader could loop that until you are empty | Always on, not a setting |

Anything the safety net stops is held, not applied: the rate stays where it was and the Supply page says why. Every run is logged.

### Hard limits

A wall automatic updates never cross, per currency and per side: the most the bot will ever give, and the least it will ever take. **There is always a wall from day one.** Every bot ships with these defaults, chosen from the live market so they sit outside it by a margin (the most generous bot today gives about 9 sets per key and the most premium one takes 4): they never touch a bot that is pricing normally, and they stop a runaway in either direction, including a crowd of bots on Undercut ratcheting each other down.

| Currency | Max the bot gives | Min the bot takes |
|---|---|---|
| TF2 | 13 sets per key | 4 sets per key |
| ToD | 5 sets per ticket | 1.5 sets per ticket |
| Gems | 1000 gems per set (what the bot pays) | 300 gems per set (what the bot charges) |

On the Supply page each box comes filled in with its default. You can:

- **Move a wall**: type your own number. It saves on its own; the **Save limits** button confirms it with a timestamp if you want to be sure.
- **Remove a wall**: clear the box. The moment you start editing, a yellow notice explains what clearing does. Once a box is blank it turns red, and a red notice names every side that now has no wall, because nothing then stops a runaway there. Put a number back in and it clears.

A side you never touched keeps its default, so an owner who never opens the page is still protected. A side you cleared stays cleared across restarts; that is your choice, and the red notice stays until you change it. The same walls apply when you click Apply by hand.

**All of your own bots are excluded from the market**, running or stopped, so your bots never undercut each other.

**Fetch Now is a true preview.** It shows each suggestion with its verdict (applied, capped at your limit, or held), plus what the next automatic run would change. If the feed cannot be fetched, the message tells you what happened and what to do; a rejected key means your Supplier subscription on steamtradebots.com needs checking.

![Supply Feed](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Supply%20Feed.png)

---

## Withdraw

Send items from the bot's inventory to any Steam account. Admin only.

**Supported items:** card sets, TF2 Keys, Tour of Duty Tickets, CS2 Keys, Hydra Keys, Gems.

### Per-game withdrawal

The Card Sets field includes an optional **Game** search input. Type a game name or AppID and select from the dropdown - the bot will only withdraw sets from that specific game. A scrollable game list on the right shows every game in the bot's inventory sorted by set count, with AppID and name visible. Click any row to fill the field automatically.

Leave the field empty to withdraw sets from across all games (default behaviour).

![Withdraw](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Withdraw.png)

---

## Deposit

Displays the bot's trade URL so you can send items to it directly from another Steam account. The bot auto-accepts any trade where the sender gives items and takes nothing back (donations must be enabled in settings).

![Deposit](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Deposit.png)

---

## Trade History

Persistent trade log - survives bot restarts. Filter by **Today**, **7 Days**, or **30 Days**. Summary cards show:

- Accepted and declined trade counts
- Net card sets received vs sent
- Net TF2 Keys, Tour of Duty Tickets, CS2 Keys, Hydra Keys
- Net Gems

Each bot has its own trade history. History from before multi-bot was added is attributed to the first bot.

![Trade History](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Trade%20History.png)

---

## Chat Commands

> **With the Chat Bridge running these move to Discord or Telegram**, and Steam chat becomes a short signpost instead. See [Chat Bridge](#chat-bridge-discord--telegram). Everything below is how Steam chat behaves with no bridge configured.

Users interact with the bot directly via Steam chat. The bot processes the request, checks the user's badge progress, and sends a trade offer to them.

| Steam chat | Discord / Telegram | What it does | Needs |
|---|---|---|---|
| `!HELP` / `!COMMANDS` | `/help` | List everything I can do | anyone |
| `!PRICES` | `/rates` | My current buy and sell rates | anyone |
| `!STOCK` | `/stock` | What I have in stock right now | anyone |
| `!KEYLIST` | `/keylist` | Which keys I accept | anyone |
| `!OWNER` | `/owner` | My owner Steam profile | anyone |
| `!BOTS` | `/bots` | Other bots run by my owner | anyone |
| `!TUTORIAL` | `/tutorial` | How trading with me works | anyone |
| `!DONATE` | `/donate` | How to donate items to me | anyone |
| `!IMABOT` | **Steam only** | Stop replying to unknown commands | anyone |
| `!CHECK` | `/check` | Your level, badges, and how many sets you can buy | SteamID |
| `!SELLCHECK` | `/sellcheck` | Which of your card sets I can buy | SteamID |
| `!RANK` | `/rank` | Your trading rank with me | SteamID |
| `!LEVEL <level>` | `/level <level>` | How many sets to reach a level | SteamID |
| `!SUPPORT <msg>` | `/support <msg>` | Send a message to my owner | SteamID |
| `!CHECKTF <n>` | `/quote tf2 <n>` | What an amount would get you (no offer sent) (TF2 keys) | SteamID |
| `!CHECKTOD <n>` | `/quote tod <n>` | What an amount would get you (no offer sent) (ToD tickets) | SteamID |
| `!CHECKCS <n>` | `/quote cs2 <n>` | What an amount would get you (no offer sent) (CS2 keys) | SteamID |
| `!CHECKHYDRA <n>` | `/quote hydra <n>` | What an amount would get you (no offer sent) (Hydra keys) | SteamID |
| `!CHECKGEMS <n>` | `/quote gems <n>` | What an amount would get you (no offer sent) (Gems) | SteamID |
| `!BUYTF <n>` | `/buy tf2 <n>` | Buy card sets, I send you a trade offer (TF2 keys) | linked |
| `!BUYTOD <n>` | `/buy tod <n>` | Buy card sets, I send you a trade offer (ToD tickets) | linked |
| `!BUYCS <n>` | `/buy cs2 <n>` | Buy card sets, I send you a trade offer (CS2 keys) | linked |
| `!BUYHYDRA <n>` | `/buy hydra <n>` | Buy card sets, I send you a trade offer (Hydra keys) | linked |
| `!BUYGEMS <n>` | `/buy gems <n>` | Buy card sets, I send you a trade offer (Gems) | linked |
| `!SELLTF <n>` | `/sell tf2 <n>` | Sell me card sets, I send you a trade offer (TF2 keys) | linked |
| `!SELLTOD <n>` | `/sell tod <n>` | Sell me card sets, I send you a trade offer (ToD tickets) | linked |
| `!SELLCS <n>` | `/sell cs2 <n>` | Sell me card sets, I send you a trade offer (CS2 keys) | linked |
| `!SELLHYDRA <n>` | `/sell hydra <n>` | Sell me card sets, I send you a trade offer (Hydra keys) | linked |
| `!SELLGEMS <n>` | `/sell gems <n>` | Sell me card sets, I send you a trade offer (Gems) | linked |

**Needs:** `anyone` works with no identity at all. `SteamID` means the bot has to know which Steam
account you are, either because you linked one or because you passed it. `linked` means a verified
linked account, because the command sends a real trade offer and the bot will not aim one at an
unproven account.

The two spellings are the same command. With the Chat Bridge running the bot rewrites its own
replies as well, so a usage hint that reads `!BUYTF 5` on Steam reads `/buy tf2 5` on Discord. A trader is never shown a command they cannot type.


**On Telegram with more than one bot, name the one you want:** `/rates bot:Low`, `/check bot:Low`.
Discord does not need this, because the channel already says which bot you are talking to. Telegram
has no channels, so the name goes on the command. It can sit anywhere in the line and is never
treated as an argument. A bot called "Gem Trader" also answers to `bot:gem-trader`. With only one
bot running you can leave it off entirely.
**Discord and Telegram only.** These are about the bridge itself, so they have no Steam chat

`/botlist` on Telegram shows every bot, whether it is online, and exactly what to type for each.
It is a Telegram command only: on Discord the channel already tells you which bot you are talking
to, so there is nothing to list.
spelling. A trader runs them in the bot's channel or in a direct message.

| Command | What it does |
|---|---|
| `/link <steamid> [tradeurl]` | Link your Steam account so you can trade |
| `/verify <code>` | Finish linking with the code I sent you on Steam |
| `/unlink` | Forget the Steam account linked here |
| `/whoami` | Show which Steam account is linked here |
| `/tradeurl <tradeurl>` | Set your trade URL so any bot can send you offers |

> The user's Steam inventory must be set to **Public** for any command that involves a trade.

### How badge caps work

When the bot selects which sets to send, it checks the user's Steam badge history via the Steam Web API. Sets are only sent for games where the user can still craft a badge:

- Normal badges: up to 5 sets per game (levels 1–5)
- Foil badges: up to 1 set per game
- Event badges: no cap

If a user has badge level 3 for a game, the bot sends at most 2 more sets from that game. Games where the user is already at max level are excluded entirely. This requires a valid Steam Web API Key in the Bot Account settings.


## Chat Bridge (Discord & Telegram)

Let your traders use the bot from **Discord** or **Telegram** instead of Steam chat. Trading still happens through normal Steam trade offers, only the conversation moves.

**Why you might want this.** Steam counts what your account *sends*. A bot that greets every new friend, answers every mistyped command and prints a long help list is producing a lot of outbound messages, and that is what gets an account flagged. The Chat Bridge gives traders a better place to talk, and quietens Steam chat right down.

**One Discord bot runs all of your bots.** These settings are app-wide, not per bot, so you only ever need a single token no matter how many bots you run.

### What traders can do without linking anything

`/rates` `/stock` `/keylist` `/owner` `/help`

These need no setup from the trader at all. Anyone in your server can see your rates.

### What needs a linked Steam account

`/check` `/level` `/sellcheck` `/quote` need to know which Steam account they are asking about. `/buy` and `/sell` need it **verified**, because otherwise someone could point the bot at a stranger and have it send trade offers to people who never asked for them.

Linking is one command and one Steam message, once, forever.

---

## Setting up Discord

### 1. Create the application

1. Go to <https://discord.com/developers/applications> and click **New Application**. Name it whatever you like, this is what traders will see.
2. Open the **Bot** tab, click **Reset Token**, and copy it. Treat it like a password.
3. **Check that "Interactions Endpoint URL" on the General Information page is empty.** If anything is in that box, Discord sends commands there instead of to your bot and nothing will work. This is the single most common setup problem.

> You do **not** need to enable any Privileged Gateway Intents. The bot uses slash commands, which need none of them.

### 2. Invite it to your server

Start the card bot with the token saved, then open the **Logs** page. The bot prints an invite link at startup:

```
[Bridge] Invite this bot with https://discord.com/api/oauth2/authorize?client_id=...
```

Open that link and pick your server. The permissions it asks for are View Channels, Send Messages, Manage Channels, Manage Messages, Embed Links and Read Message History. Manage Channels is what lets it create and tidy the per-bot channels below. Read Message History looks unnecessary, since the bot never reads conversations, but Discord requires it to pin a message and to check whether anyone has posted in a channel before retiring it.

> **If the Chat Bridge page says permissions are missing**, the bot was invited before it asked for all of them. A Discord bot keeps the permissions it was invited with, so open the invite link again and re-authorise. Discord updates the bot you already have rather than adding a second one. Until then channels still work, but the bot cannot pin a message in them or tidy them up.

### 3. Paste the token

**Chat Bridge** page → **Discord Bot Token** → tick **Accept commands on Discord** → **Save**, then **Stop and Start** the bot. The bridge only attaches when a fresh Steam session comes up.

### 4. Server ID (recommended)

In Discord, turn on **Settings → Advanced → Developer Mode**. Right-click your server name → **Copy Server ID**, and paste it into **Server ID**.

Without this, Discord can take up to an hour to publish your commands the first time. With it, they appear immediately. Worth setting even if you only use it while testing.

---

## Bot channels

Each of your bots gets its own channel, named after it, so traders always know which bot they are talking to. **The channel is the bot.**

```
CARD BOTS
  # low          talks to "Low"
  # high         talks to "High"
  # gem-trader   talks to "Gem Trader"
```

A command typed in `#low` goes to Low and nowhere else. No arguments, nothing to remember.

### Setting it up

1. In Discord, create an empty **category** (right-click in the channel list → Create Category). Call it whatever you like.
2. Right-click the **category heading** → **Copy Category ID**. This is a long number, not the name.
3. Paste it into **Bot Channels Category ID** on the Chat Bridge page and **Save**.
4. Click **Create / update bot channels**.

Every bot you have configured gets a channel, including when you only run one, so the category always reads as a complete list. Each channel gets a pinned line saying which bot it belongs to, and its topic shows live rates and stock.

### It keeps itself in order

| You do this | The bot does this |
|---|---|
| Rename a bot | Renames its channel to match |
| Add a bot | Creates a channel for it |
| Drag a channel out of the category | Moves it back |
| Delete a bot | Removes its now-dead channel |
| Click sync again | Nothing, it never makes duplicates |

### What the bot is allowed to change

Two switches on the Chat Bridge page, both on unless you turn them off.

| Switch | On | Off |
|---|---|---|
| **Remove channels for deleted bots** | A dead room is deleted | It is kept and marked as retired |
| **Rename channels when a bot is renamed** | The channel name follows the bot name | Your own channel names are left alone |

Renaming is the only thing a sync does to a name you may have chosen yourself, which is why it
can be switched off. A channel belongs to its bot by id, not by name, so renaming one by hand
never breaks the link and the bot keeps answering there. After a sync the page says how many
names it left alone, so an idle-looking result is never a silent failure.

**Deleting is careful.** A channel is only ever removed if this bot created it *and* nobody has typed in it. Slash replies are private, so a bot channel normally holds nothing but the pinned line. If a real person has posted there, it is kept and simply marked as retired. A retired channel also stops answering: a command typed in it gets a short note saying the bot that lived there was removed, rather than being quietly answered by whichever other bot happens to be running. You can switch removal off entirely with **Remove channels for deleted bots**.

> Traders can also message the bot directly instead of using a channel. With one bot running that just works. With several, the bot asks which one you meant and lists the channels.

---

## Setting up Telegram

Much shorter, no developer account needed:

1. Open Telegram and message **@BotFather**.
2. Send `/newbot` and follow the two prompts.
3. Copy the token it gives you into **Telegram Bot Token**, tick **Accept commands on Telegram**, **Save**, then Stop and Start the bot.

Traders open your bot in Telegram and type `/` to see every command. The bot's `t.me` link is worked out automatically, you do not need to enter it.

**Running more than one bot?** Discord gives each bot its own channel, which says who you are
talking to. Telegram has no channels, so the trader names the bot on the command itself:

    /rates bot:Low
    /check bot:Low

They do not have to memorise anything. `/botlist` lists every bot with what to type and which
are online, and `/help` repeats it at the bottom whenever more than one bot is running. The name
can go anywhere in the line and is never read as an argument. With a single bot it can be left
off entirely, so a one-bot owner never sees any of this.

A bot whose name contains a space, say "Gem Trader", is reached as `bot:gem-trader`, because the
command line is split on spaces. `/botlist` always shows the form that works.

---

## What changes on Steam

Once a bridge is running, Steam chat stops being a menu and becomes a signpost.

| | Bridge off | Bridge on |
|---|---|---|
| New friend | Full welcome message | Short greeting pointing at Discord or Telegram |
| `!HELP` | The full command list | One line pointing at Discord or Telegram |
| An unknown `!command` | "Unknown command" reply | Silence |
| Someone spamming | Three warnings, then unfriended | Silently timed out, then unfriended |
| Trading commands | All work | Handled on Discord or Telegram instead |

Every message is worded one of **15 different ways**, because sending identical text to everybody is exactly what looks automated. The bot also pauses and shows Steam's typing indicator rather than replying instantly.

**You are exempt.** Admin SteamIDs keep full command access on Steam, so you never lose control of your own bot.

**With no bridge configured, none of this applies.** The bot talks exactly as it always has.

### Telling traders where to go

Two options under **Telling traders where to go**:

- **Point at my profile** (default). The bot says *"the invite is on my Steam profile"* and never types a link. Steam scores accounts that send links, so this is the quieter choice. **Put your invite in your Steam profile summary first**, or traders hit a dead end.
- **Post the actual invite link**. Simpler for traders, at the cost of every message carrying a URL.

Either way, fill in **Server Invite Link** with the `https://discord.gg/...` invite you hand to traders. That field is what arms the whole quiet mode: with nowhere to send people, the bot stays talkative on Steam rather than pointing at nothing.

> The friend-list status line on the **Bot Settings** page now understands `{discord}` and `{telegram}` too, so you can advertise your invite there without the bot sending anything at all.

---

### Offering a Steam group invite

Off by default. Switch on **Offer a Steam group invite** and give it a group ID, and the signpost
gains one closing line:

> Nearly everything runs through Discord now, nicer for everybody trading. The invite is on my
> Steam profile whenever you fancy it.
>
> There is a link on my profile, and I can send you a Steam group invite if you say yes.

**The invite is sent only when that trader replies yes.** Not after a trade, not on a timer, and
never to anybody who has not asked. That last part matters: an invite nobody asked for is what
Steam treats as spam, and it is the bot account that gets reported for it. An earlier version of
this bot invited every trading partner automatically and that is exactly why it was removed.

What counts as yes is deliberately narrow: a short reply such as *yes*, *ok*, *sure*, *invite me*.
A sentence is not a yes, so "yes but only the good ones" gets nothing. A no gets silence rather
than another message. One invite per person, and a yes only counts for 15 minutes after the offer.

The offer line comes in 15 phrasings and the confirmation in another 15, so the pair never repeats.
Leave the switch off and the bot never mentions a group at all.

## How a trader links their Steam account

1. They add your bot on Steam as normal. **The bot only links accounts it is already friends with**, which is what stops it being used to message strangers.
2. They run `/link 7656...` with their SteamID64.
3. Your bot sends them **one** Steam message containing a 6-character code.
4. They reply `/verify ABC123`. That is the only Steam message they will ever get.
5. `/buy` and `/sell` now work, with **every** bot you run, not just the one they used.

### Trade URLs

A trader who also runs `/tradeurl <their Steam trade URL>` can be sent offers by **any** of your bots without adding each one as a friend. Worth suggesting if you run several.

The bot checks the trade URL actually belongs to the account they verified, so nobody can point your offers at somebody else. If they later regenerate their trade URL, the bot notices, forgets the old one, and tells them to run `/tradeurl` again.

---

## Chat Bridge troubleshooting

| What you see | What it means |
|---|---|
| *"That kind of interaction is not handled here"* | **Interactions Endpoint URL is set** in the Discord developer portal. Clear it. |
| *"This command is outdated"* | Discord is still publishing your commands. Set the **Server ID** for instant registration, and press Ctrl+R in Discord. |
| Commands do not appear at all | The bot was invited without the `applications.commands` scope. Re-invite using the link in your Logs. |
| Channels are not created | The bot is missing **Manage Channels** on that category, or the Category ID is a name rather than an id. |
| Duplicate channels | Give the bot **View Channels** on the category. It cannot see what it already made. |

The **Logs** page shows a line the moment any command arrives:

```
discord: interaction received: rates
```

If a trader reports a problem and that line is missing, Discord never reached the bot, so the cause is one of the first three rows above. If it is there, the log will say what happened next.

---

## Chat Monitor

Live feed of all Steam chat messages and incoming support requests. Each entry shows the user's Steam ID, their message, and the bot's response.

![Chat Monitor](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Chat%20Monitor.png)

---

## Maintenance

Automated friend list management:

| Setting | Description |
|---|---|
| Auto-accept friends | Accept all incoming friend requests automatically |
| Reject group invites | Silently reject Steam group invitations |
| Auto-cleanup | Remove friends who haven't traded in N days |
| Max friend list size | Trigger cleanup when list exceeds this number |
| Ban detection | Skip or flag trading partners with VAC/game bans |
| Spam protection | Rate-limit users who send excessive commands |

![Maintenance](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Maintenance.png)

---

## Logs

Raw bot log output with INFO, WARN, and ERROR entries. One-click clear. Each bot's log is separate.

The **🛟 Support Report** button gathers everything support needs — app version, OS, bot state, and the recent log — into one report, copied to your clipboard and saved as a file. Passwords, secrets, and API keys are never included. If something goes wrong, send that one paste instead of screenshots.

![Logs](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Logs.png)

---

## Getting a License

Visit **[steamtradebots.com](https://www.steamtradebots.com/)** to purchase and activate a license. The license is tied to your machine and validated on startup.

---

## Support & Community

Questions, bugs, or feature requests:

- **Discord:** [discord.gg/XCtgnPsZFU](https://discord.gg/XCtgnPsZFU)
- **Issues:** [github.com/stardrix/steam-card-bot-releases/issues](https://github.com/stardrix/steam-card-bot-releases/issues)
- **Email:** support@steamtradebots.com

---

## Running on a VPS

The bot works on datacenter/VPS hosting out of the box: inventory requests retry patiently through Steam's per-IP rate limits, recently fetched inventories are cached and reused, and background Steam traffic is kept to a minimum.

### Choosing a VPS provider

Steam rate-limits by IP address, and an IP's history matters: ranges belonging to popular budget hosts are shared with many other Steam bots, so they often arrive pre-throttled. For the smoothest experience we recommend a **premium VPS provider with a clean, dedicated IP** over the cheapest option — the few extra euros per month buy you an IP reputation that Steam treats far better.

Before committing to a provider (or after receiving a new IP), you can test it in seconds: open `https://steamcommunity.com/inventory/<your-bot-steamid64>/753/6` in a browser on the VPS (any public inventory works — your bot's own is ideal). A JSON response means the IP is fine; an immediate error on the very first request means the IP range is throttled — ask your host for a different IP or pick another provider.

### If your IP is still rate-limited

If buyers frequently see "Steam seems busy", switch **Bot Settings → Inventory Method** to **SteamApis** and paste an API key from [steamapis.com](https://steamapis.com) — inventory loading then bypasses Steam's limits entirely, on any hosting. Their free tier (500 requests/month) covers a typical small bot thanks to the built-in caching.

---

## Requirements

- Windows 10/11 (x64)
- Linux (x64)
- A Steam account dedicated to being the bot
- Steam Web API Key ([get one here](https://steamcommunity.com/dev/apikey))
- Shared Secret and Identity Secret from your Steam authenticator (SteamDesktopAuthenticator or WinAuth)
- A valid Steam Card Bot license

---

*This repository contains release builds only. New versions are detected and installed silently by the app via GitHub Releases.*
