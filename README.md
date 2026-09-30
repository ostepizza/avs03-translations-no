# Translating Antivirus Survivors 2003 Professional to Norwegian
> ❗ **_NOTE:_** \
> This repo focuses on translating AVS03 to Norwegian. Any help with translations and/or improvements are welcome through a PR.

Thanks for helping. You do not need the source code.

- Game: https://store.steampowered.com/app/3832490/
- Discord: https://discord.gg/avs03
- Translations: https://github.com/shbsltd/avs03-translations

Sending a change here means we can use your translation in the game.

## What you need

- The game (latest build). Ask in Discord if you need it.
- [Poedit](https://poedit.com/download/), or any gettext editor.

## Your locales folder

The first time you run the game it creates:

```
locales/
  messages.pot      template for new translations
  TRANSLATING.txt   this guide
  locale_names.csv  language names in the settings menu
  official/         game-provided translations (refreshed each update)
  custom/           your work. The game never overwrites this.
```

- Windows: `%APPDATA%\AntivirusSurvivors\locales\`
- macOS: `~/Library/Application Support/AntivirusSurvivors/locales/`
- Linux: `~/.local/share/AntivirusSurvivors/locales/`

Put your `xx.po` in `custom/`. If official and custom both have the same language, both show up in Settings. The custom one has a * next to its name.

Missing lines fall back to the official translation, then to English. You do not need to re-export every time the game updates.

To name your language in Settings, add a line to `locale_names.csv`:

```
xx,Your Language Name
```

## Make your language file

1. Open Poedit. Create new translation. Pick `messages.pot` from your locales folder.
2. Choose your language. Save as `xx.po` using the 2-letter code (`de`, `es`, `ja`, ...).
3. Translate each entry:
   - Most entries show a key like `UI.shop_title`. The English is in the notes panel on a line starting with `source:`. Type your translation in the bottom box.
   - If the notes say to keep placeholders unchanged, copy those tokens exactly (`%.2f`, `{percent}`) and only move them where they fit.
   - Some entries show the English as the source. Translate those normally.
4. Save `xx.po` into `custom/`.

When English changes, open your `xx.po` in Poedit and use **Translation > Update from POT file**. Pick `messages.pot`. Fix anything marked Needs work (orange).

Keep these as they are:

- `%d`, `%s`, `%.2f` and similar. Move them, do not delete them. `Reroll: %.2f Coin` becomes `Relancer : %.2f Coin`
- `{percent}`, `{m}`, `{s}` and other `{...}` placeholders
- Numbers and fake filenames in English. Change KB/s only if you need to.

## Test it in the game

1. Put `xx.po` in `custom/`.
2. Start the game, open Settings, pick your language.
3. Edit, save in Poedit, relaunch to see changes.

If text overflows, stretches the UI, or cuts off with `...` in a way that hurts gameplay, say so in Discord or open a GitHub issue.

## Send your file

Do the work in Poedit, then upload the saved `xx.po`. Do not edit `messages.pot` or `en.po`.

1. Sign in and open https://github.com/shbsltd/avs03-translations
2. Click **Fork** (top right). Wait until you are on your copy of the repo.
3. Click **Add file**, then **Upload files** (next to the green **Code** button) and drop your `xx.po`.
4. **Commit changes**, then **Contribute**, then **Open pull request**.

## Questions

- Discord: https://discord.gg/avs03
- GitHub issues: https://github.com/shbsltd/avs03-translations/issues
