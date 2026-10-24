# CCRP Handbook

A free website for **Clementine County RP (CCRP)** with two guides in one:

- **Staff Handbook (ER:LC):** rules, punishment ladders, priority requests, `:h` hints, appeals, training and more for in-game moderators.
- **Discord Mod Guide:** Discord rules, mod tools, incidents, tickets, safety and raids, conduct and practice for Discord moderators.

It is a plain static site, so it runs on GitHub Pages with no build step.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole site: pages, styles and code. The logo is inside this file. |
| `sw.js` | Lets the site open offline. It always tries the internet first, so updates show up right away. |
| `manifest.webmanifest` | Lets people install the site as an app. |
| `icon-192.png`, `icon-512.png` | The app icons. |
| `404.html` | The page shown when a link is wrong. |
| `og-image.png`, `favicon.ico` | The preview picture when the link is shared, and the tab icon. |
| `robots.txt`, `sitemap.xml` | Help search engines find the site. |
| `CHANGELOG.md` | A short list of what changed. |
| `README.md` | This guide. |

Upload all of them to the top level of the repo. The site still works with only `index.html`, but install and offline use need the others.

## Put it online (GitHub Pages)

1. Create a GitHub repository and upload the files above.
2. Open **Settings > Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
3. Wait a minute or two. The site appears at `https://YOURNAME.github.io/REPONAME/`.
4. After every upload, hard refresh with **Ctrl+Shift+R**. Because the site works offline, an old copy can stick, so reload twice if needed.

## How it works

- **Tabs are pages.** Each tab has its own link, like `#/punishments` or `#/drules`. Opening a link shows that page. The Back and Next buttons, search, number keys and menu all use the same links.
- **Two guides.** The bar under the top bar switches between them. Each guide has its own tabs, accent colors and Home.
- **One list, many places.** Most content lives in lists near the bottom of `index.html`. Edit a list once and every page that uses it updates. For example, the ER:LC `RULES` list feeds the punishment guide, the cheat sheet, the lookup, the log builder, the search and the rule of the day.
- **Three views.** The site picks **PC**, **Mobile** or **Console** for each device. Anyone can change it with **View** in the footer (or in the **Menu** on phones). The choice is saved on that device.
- **Light effects.** The **Effects** dropdown in the footer turns off heavy animation for slow devices.

## Where to edit what

Open `index.html` in a text editor and search for the name.

| To change | Search for |
|---|---|
| ER:LC rules and punishment ladders | `const RULES` |
| Rule explanations (example, not a violation, tip) | `const RX` |
| Discord rules and action ladders | `const DR` |
| Replies to player questions | `const QA` |
| Staff scenario quiz | `const SC` |
| Discord scenario quiz | `const DQ` |
| R/A checklist | `const CK` |
| Glossary | `const GL` |
| Ready-made `:h` hints | `const HT` |
| Levels and badges | `const LV` and `const BD` |
| Role paths on the Home page | `const PATHS` |
| Colors | `:root {` near the top (and the lines starting `[data-v=` for each tab) |
| The "Last updated" date | `Last updated` in the footer |

Anything in `[square brackets]`, like `[server code]` or `[appeals channel]`, is a placeholder. Search for `[` and replace them with your real details.

## Features

- Punishment lookup, cheat sheet, search with autofill (press **Tab**) and pinned rules
- Log builders for ER:LC and Discord, with copy buttons
- Priority checker, hint builder, ready replies and DM templates
- Levels, badges, rule of the day, role paths and scenario quizzes
- Case log, shift checklists and timer, mod exam with a printable certificate, daily challenge, quick replies, rule compare and an announcement builder
- Spanish for menus, Home and settings (the rules stay in English)
- Light and dark mode, three views, controller support and offline install

## Feedback

Visitors can give feedback from the **Feedback** button in the footer, the search (Ctrl K), or the occasional small prompt. The prompt only shows to returning visitors who allowed Settings saving, after about five page views, at most every two weeks, and never again after **Do not ask again**.

Feedback needs no account. By default a visitor can **Copy** it or **Open on GitHub** (a prefilled issue in your repo). To also get a **Send feedback** button that posts to a Discord channel, search `index.html` for `const FEEDBACK` and paste a Discord webhook URL into `discordWebhook`. Anyone who reads the page source can see that URL, so use a channel only your team can see and delete the webhook if it is ever abused.

## Discord invite

The animated Discord buttons open `https://discord.gg/UHQd6TMrEy`. To change the invite, search `index.html` for `discord.gg` and replace all four links.

## Shortcuts

- Keys `1` to `0` open the first ten tabs of the current guide.
- `/` or `Ctrl K` opens search.
- On a console or with a controller: D-pad moves, **A** selects, **LB / RB** change tab, **B** goes Home, **Start** opens search.

## Cookies and settings

The site has no accounts, no tracking and no ads, and nothing is ever sent anywhere. On a first visit a small banner asks what may be saved on the visitor's device:

- **Essential:** only the visitor's cookie choice. Always on. It is saved as a cookie (`ccrp_consent`) and in browser storage.
- **Settings:** theme, text size, view, effects and reduce motion.
- **Progress:** XP, levels, badges, pinned rules, role path and the R/A checklist.

Until the visitor chooses, nothing is saved. They can change their mind any time with the sliders button in the top bar, the **Cookies and settings** button in the footer, or the **Menu** on phones. The settings panel also has theme (match device, dark or light), text size, view, effects and reduce motion, a list of exactly what is saved, **Download my data**, **Reset progress**, **Clear offline copy** and **Delete everything**.

To add a new saved item, add its key to `CKCAT` near the top of the script so it follows the visitor's choices.

## Troubleshooting

- **Old version or blank page:** hard refresh with Ctrl+Shift+R, or open the site in a private window.
- **Changes not showing on GitHub:** check that the commit finished and that Pages says "Your site is live".
- **Phone shows the wrong layout:** open the **Menu** and change **View** to Auto.
- **Tabs missing from the top bar:** the ones that do not fit are under **More**.
- **Something looks stuck:** set **Effects** in the footer to Light.
