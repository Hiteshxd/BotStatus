[![Issues](https://img.shields.io/github/issues/Hiteshxd/BotStatus?style=for-the-badge&color=green)](https://github.com/Hiteshxd/BotStatus/issues)
[![Forks](https://img.shields.io/github/forks/Hiteshxd/BotStatus?style=for-the-badge&color=green)](https://github.com/Hiteshxd/BotStatus/fork)
[![Stars](https://img.shields.io/github/stars/Hiteshxd/BotStatus?style=for-the-badge&color=green)](https://github.com/Hiteshxd/BotStatus)
[![LICENSE](https://img.shields.io/github/license/Hiteshxd/BotStatus?color=green&style=for-the-badge)](https://github.com/Hiteshxd/BotStatus)
[![Size](https://img.shields.io/github/repo-size/Hiteshxd/BotStatus?style=for-the-badge&color=green)](https://github.com/Hiteshxd/BotStatus)
[![Contributors](https://img.shields.io/github/contributors/Hiteshxd/BotStatus?style=for-the-badge&color=green)](https://github.com/Hiteshxd/BotStatus)



## BotStatus ~ 

A simple, short, mostly customisable GitHub Action to show your bot's status in your GitHub MarkDown file as well as in your Telegram. 

---
### How to use this ?
- **Star** this repo. ⭐
- Go to the repository where you want to display the status of the bots. 🤖
- Go to environment variables ([Settings ⇢ Secrets ⇢ New Repository Secret.](https://docs.github.com/en/actions/reference/encrypted-secrets)) 🚶
- Fill all Environment variables there. 🤭
- Copy [this](./example.yml) snippet in `./github/workflows/main.yml` in your repository. 📁
- The workflow will automatically run at interval of 3 hours. 🏃 

**⚠️ You'll need a valid JSON with all your bots with some additional information. Example is given in example.json, But the link shuld point to raw data like [here](https://raw.githubusercontent.com/Hiteshxd/BotStatus/main/example.json). You can use [npoint.io](https://npoint.io), [gist.github.com](https://gist.github.com), [pastebin.com](https://pastebin.com), [JSONKeeper.com](https://jsonkeeper.com) etc...**

**You can also use `${{ steps.bot-status.outputs.STATUS }}` for using the JSON data (containing the name of bot, username and status) wherever you want to use them.**

> 3rd and 4th steps are not mandatory, It's just to keep your secrets completely secret and not let anyone peep into them. You can also define them directly in `.yml` file.


---

<details>
  <summary><b>🤫&nbsp;Environment variables</b></summary>
  <br/>

<b>⌲ These are mandatory variables and should be kept secret. (use [Environment variables](https://docs.github.com/en/actions/reference/encrypted-secrets))</b>

| 🔒 Secret 🔒 | 🏷 Description 🏷 | ⚙️ Default ⚙️ | 📇 Example 📇 |
| :-: | :-: | :-: | :-: |
| `API_HASH` | Get it from [my.telegram.org](https://my.telegram.org) | `None` | `782xxxx` |
| `APP_ID` | Get it from [my.telegram.org](https://my.telegram.org) | `None` | `a1bbfb767fd59812bxxxxxxxxxxxxxxx` |
| `IDS` | IDs of the Messgage followed with `chat id` | `None` | `-100153418xxxx:3 -100225478xxxx:16` |
| `SESSION` | [![Run on Repl.it](https://replit.com/badge/github/jainamoswal/SessionString)](https://replit.com/@jainamoswal/SessionString) | `None` | `xxxxxxxxxxxxxxxx.....` |
| `BOTS` | Raw link of JSON file of bots. | [🔗 Link 🔗](https://raw.githubusercontent.com/Hiteshxd/BotStatus/main/example.json) | [JSON format](/example.json) ║ [Raw link](https://raw.githubusercontent.com/Hiteshxd/BotStatus/main/example.json) |


**Format of chat IDs » `chat id`:`message id` 
Eg, `-100123456xxx:1x` where `100123456xxx` is `chat id` and `1x` is `message id`.**

<details><summary><b>Optional variables</b></summary>
<br>

<b>⌲ These are optional values and can be omitted. Default values will be used. (can use directly in `.yml` instead of messing Environment variables.)</b> 
| 🧾 Values 🧾 | 🏷 Description 🏷 | ⚙️ Default ⚙️ | 📇 Example 📇 |
| :-: | :-: | :-: | :-: |
| `FILE_NAME` | Name of the file to edit.  | `README.md` | `STATUS.md` |
| `EDIT_IN_REPO` | `True` for editing status in repository, `False` for else. | `True` | `True` |
| `EDIT_IN_TELEGRAM` | True for editing status in Telegram. | `True` | `True` |
| `START_MESSAGE` | Message to be shown in starting of the Text in Telegram. | _Read [main.py](./main.py)_ | _Read [main.py](./main.py)_ |
| `END_MESSAGE` | Message to be shown in ending of the Text in Telegram. | _Read [main.py](./main.py)_ | _Read [main.py](./main.py)_ |
| `COMMIT_MESSAGE` | Message while commit. | `✨ auto-updated bot status. ✨` | `Updated bot status [Bot]` |
| `BULLET` | The bullet use to separate bots in Telegram. | `◪` | `◍` |
| `TIME_ZONE` | The Time zone of your locale. | `Asia/Kolkata` | `Europe/London` |
| `TIME_FORMAT` | Format of your time to be shown everwhere. | `%H:%M %d/%m` | `%Y-%m-%d %H:%M:%S` |
| `UP_GITHUB` | Emoji or Text when the status is up. (on GitHub MarkDown file) | `✔️` | `✅` |
| `DOWN_GITHUB` | Emoji or Text when the status is down. (on GitHub MarkDown file) | `❌` | `❎` |
| `UP_TELEGRAM` | Emoji or Text when the status is up. (in Telegram chat) | `🚀` | `☑️` |
| `DOWN_TELEGRAM` | Emoji or Text when the status is down. (in Telegram chat) | `❌` | `💤` |

</details>

</details>

## License 
### [BotStatus](https://github.com/Hiteshxd/BotStatus) is licensed under [GNU Affero General Public License v3](https://www.gnu.org/) or later.

[![License](https://www.gnu.org/graphics/gplv3-or-later.png)](LICENSE)

`The GNU General Public License (GNU GPL or simply GPL) is a series of widely-used free software licenses that guarantee end users the freedom to run, study, share, and modify the software.[8] The licenses were originally written by Richard Stallman, founder of the Free Software Foundation (FSF), for the GNU Project, and grant the recipients of a computer program the rights of the Free Software Definition.[9] The GPL series are all copyleft licenses, which means that any derivative work must be distributed under the same or equivalent license terms. This is in distinction to permissive software licenses, of which the BSD licenses and the MIT License are widely used, less restrictive examples. GPL was the first copyleft license for general use.`
