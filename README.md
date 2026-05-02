# Steam Card Bot

> Automated Steam card set trading bot with a full desktop dashboard — supports multiple bots, live rate management, per-game withdrawals, and bot-initiated-only trade flow.

**[Get a license](https://www.steamtradebots.com/) · [Join Discord](https://discord.gg/XCtgnPsZFU) · [Report an issue](https://github.com/stardrix/steam-card-bot-releases/issues)**

---

## Overview

Steam Card Bot is a Windows / Linux desktop application built on Electron. It connects one or more Steam bot accounts, manages your card set inventory automatically, and executes trades via Steam chat commands — the bot always sends the trade offer, keeping you in full control of every transaction.

### What it trades

| Item | Buy | Sell |
|---|---|---|
| Normal card sets | ✅ | ✅ |
| Foil card sets | ✅ | ✅ |
| TF2 Keys | ✅ | ✅ |
| Tour of Duty Tickets | ✅ | ✅ |
| CS2 Keys | ✅ | ✅ |
| Hydra Keys | ✅ | ✅ |
| Gems (Sack of Gems) | ✅ | ✅ |

---

## Key Features

- **Multi-bot support** — run and manage multiple Steam bot accounts from one dashboard, each with its own credentials, rates, and inventory
- **Bot Overview** — live grid showing every bot's status, trade count, uptime, and username at a glance; start or stop individual bots directly from the grid
- **Start All / Stop All** — launch or shut down all configured bots in one click; failed bots are highlighted in red with the specific reason displayed
- **Bot-initiated trade flow** — users interact via Steam chat commands; the bot always sends the trade offer so no unsolicited incoming offers are processed
- **Badge-aware set selection** — the bot checks a user's Steam badge level before sending sets, so it only sends sets the user can still craft (respects the 5-level cap per game; 1-level cap for foil)
- **Per-game withdraw** — withdraw card sets from a specific game by AppID, with a searchable in-app game list so you never have to look up an AppID manually
- **Rate Simulator** — preview exactly what the bot will send for any currency and quantity before going live; includes stock warnings if the bot doesn't have enough inventory
- **Live rate editing** — change buy/sell rates and they apply to the running bot instantly, no restart needed
- **Listing integrations** — automatic sync to SteamTradeBots.com, Steam.supply, and Steambot.info whenever rates change
- **Supply Feed** — auto-adjust rates based on live competitor prices with six price modes
- **Persistent trade history** — full log of every accepted and declined trade, filterable by Today / 7 Days / 30 Days, survives restarts
- **Profit tracking** — net profit per currency tracked per bot
- **Maintenance** — auto-manage friend lists, spam protection, ban detection, and cleanup schedules
- **Auto-update** — new releases are downloaded and installed silently in the background

---

## How It Works

1. Install the app and activate your license
2. Add your Steam bot account credentials (username, password, shared secret, identity secret)
3. Set your buy and sell rates in the Rates tab
4. Start the bot — it logs into Steam, fetches inventory, and posts your listing
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
| Shared Secret | 2FA — the bot generates codes automatically |
| Identity Secret | Auto-confirms trades, no phone needed |
| Admin Steam IDs | These accounts bypass all rate checks |
| Owner Profile URL | Shown when users type `!OWNER` |

All secret fields are hidden behind a reveal toggle. Each bot stores its own copy of these settings independently.

![Bot Account](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Account.png)

---

## Bot Settings

Fine-tune how the bot behaves: card mode (normal, foil, or event cards), persona name, trade size limits, donation acceptance, post-trade profile comments, Steam group invites, inventory fetch method, advanced timing, blocked games, and per-game stock limits.

![Bot Settings](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Settings%20First%20haf.png)

![Bot Settings (continued)](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Bot%20Settings%20sec%20haf.png)

---

## Commands

Enable or disable individual currencies and chat commands without restarting the bot. Toggle a currency off to fully disable it — the bot won't trade or respond to commands for it. Toggle individual commands off to block just that action while keeping the currency active.

![Commands](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Commands.png)

---

## Rates

Set how many card sets the bot gives or requires per unit of currency. Four key types supported: TF2 Keys, Tour of Duty Tickets, CS2 Keys, and Hydra Keys. Gems use a separate rate (gems per set).

| Direction | What it means |
|---|---|
| **BUY** (sets/unit) | Sets the bot sends to the user per currency unit the user gives |
| **SELL** (sets/unit) | Sets the user must give per currency unit the bot sends back |

Rate changes apply to the running bot instantly — no restart required.

### Rate Simulator

A built-in calculator at the bottom of the Rates tab lets you preview trade outcomes before going live:

1. Pick a currency (TF2, ToD, CS2, Hydra, or Gems)
2. Pick a direction (BUY or SELL)
3. Enter a quantity
4. Click **Simulate** — see exactly how many sets or keys the bot would send, with a warning if current stock is too low

![Rates](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Rates.png)

---

## Listings

Connect API keys for up to three listing services. Rates and stock sync automatically whenever you save changes.

| Service | What it does |
|---|---|
| SteamTradeBots.com | Posts bot status, all buy/sell rates, total card set stock, key/gem counts, and a full per-game set breakdown (how many sets per AppID) |
| Steam.supply | Posts buy/sell rates for TF2, CS2, Hydra, ToD keys and gems, current key/gem stock, and per-game set counts |
| Steambot.info | Posts buy/sell rates for TF2, CS2, Hydra, ToD keys and gems, and a full per-game set breakdown so buyers can see exactly which games you stock |

![Listings](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Listings.png)

---

## Supply Feed

Automatically fetches live competitor rates and adjusts your own rates to stay competitive. Six price modes available:

| Mode | Description |
|---|---|
| **Off** | Manage rates fully manually |
| **Auto Cheap** | Undercut the cheapest competitor by your offset |
| **Match Market** | Match the best available rate exactly |
| **Average Market** | Sit at the market midpoint ± your offset |
| **Buy Side Only** | Auto-adjust buy rates; sell stays manual |
| **Sell Side Only** | Auto-adjust sell rates; buy stays manual |
| **Auto Premium** | Sit above the market average by your offset |

The bot excludes its own listing from the comparison data so it never undercuts itself.

![Supply Feed](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Supply%20Feed.png)

---

## Withdraw

Send items from the bot's inventory to any Steam account. Admin only.

**Supported items:** card sets, TF2 Keys, Tour of Duty Tickets, CS2 Keys, Hydra Keys, Gems.

### Per-game withdrawal

The Card Sets field includes an optional **Game** search input. Type a game name or AppID and select from the dropdown — the bot will only withdraw sets from that specific game. A scrollable game list on the right shows every game in the bot's inventory sorted by set count, with AppID and name visible. Click any row to fill the field automatically.

Leave the field empty to withdraw sets from across all games (default behaviour).

![Withdraw](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Withdraw.png)

---

## Deposit

Displays the bot's trade URL so you can send items to it directly from another Steam account. The bot auto-accepts any trade where the sender gives items and takes nothing back (donations must be enabled in settings).

![Deposit](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Deposit.png)

---

## Trade History

Persistent trade log — survives bot restarts. Filter by **Today**, **7 Days**, or **30 Days**. Summary cards show:

- Accepted and declined trade counts
- Net card sets received vs sent
- Net TF2 Keys, Tour of Duty Tickets, CS2 Keys, Hydra Keys
- Net Gems

Each bot has its own trade history. History from before multi-bot was added is attributed to the first bot.

![Trade History](https://www.steamtradebots.com/assets/images/Bots/SteamCadBot/Trade%20History.png)

---

## Chat Commands

Users interact with the bot directly via Steam chat. The bot processes the request, checks the user's badge progress, and sends a trade offer to them.

| Command | Description |
|---|---|
| `!HELP` / `!COMMANDS` | List all available commands |
| `!PRICES` | Current buy and sell rates for card sets |
| `!FOILPRICES` | Current buy and sell rates for foil sets |
| `!STOCK` | Bot's current card set stock |
| `!FOILSTOCK` | Bot's current foil set stock |
| `!IMABOT` | Confirms the account is a bot |
| `!OWNER` | Owner's Steam profile link |
| `!SUPPORT <msg>` | Send a support message to the owner |
| `!CHECKTF <n>` | How many sets n TF2 Keys are worth |
| `!CHECKTOD <n>` | How many sets n ToD Tickets are worth |
| `!CHECKCS <n>` | How many sets n CS2 Keys are worth |
| `!CHECKHYDRA <n>` | How many sets n Hydra Keys are worth |
| `!BUYTF2 <n>` | Give n TF2 Keys → receive card sets |
| `!BUYTOD <n>` | Give n ToD Tickets → receive card sets |
| `!BUYCS2 <n>` | Give n CS2 Keys → receive card sets |
| `!BUYHYDRA <n>` | Give n Hydra Keys → receive card sets |
| `!BUYGEMS <n>` | Give n Gems → receive card sets |
| `!SELLTF2 <n>` | Give card sets → receive n TF2 Keys |
| `!SELLTOD <n>` | Give card sets → receive n ToD Tickets |
| `!SELLCS2 <n>` | Give card sets → receive n CS2 Keys |
| `!SELLHYDRA <n>` | Give card sets → receive n Hydra Keys |
| `!SELLGEMS <n>` | Give card sets → receive n Gems |

> The user's Steam inventory must be set to **Public** for any command that involves a trade.

### How badge caps work

When the bot selects which sets to send, it checks the user's Steam badge history via the Steam Web API. Sets are only sent for games where the user can still craft a badge:

- Normal badges: up to 5 sets per game (levels 1–5)
- Foil badges: up to 1 set per game
- Event badges: no cap

If a user has badge level 3 for a game, the bot sends at most 2 more sets from that game. Games where the user is already at max level are excluded entirely. This requires a valid Steam Web API Key in the Bot Account settings.

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

## Requirements

- Windows 10/11 (x64) or Linux (x64)
- A Steam account dedicated to being the bot
- Steam Web API Key ([get one here](https://steamcommunity.com/dev/apikey))
- Shared Secret and Identity Secret from your Steam authenticator (SteamDesktopAuthenticator or WinAuth)
- A valid Steam Card Bot license

---

*This repository contains release builds only. New versions are detected and installed silently by the app via GitHub Releases.*
