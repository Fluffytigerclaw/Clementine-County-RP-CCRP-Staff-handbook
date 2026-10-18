# CCRP Staff Handbook

Staff guide website for **Clementine County RP (CCRP)**. It is a plain static site, so it runs on GitHub Pages with no build step.

## Put it online (GitHub Pages)

1. Create a GitHub repository (for example `ccrp-handbook`).
2. Upload `index.html` to the top level of the repo. The logo is already inside `index.html`, so no other file is needed.
3. Open **Settings > Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. Wait a minute or two. Your site will be at `https://YOURNAME.github.io/REPONAME/`.
5. After you upload a new version, hard refresh with **Ctrl+Shift+R** to skip the browser cache.

## Edit the content

Open `index.html` in any text editor.

- **Punishment rules:** find `const RULES = [` near the bottom. Each rule is one entry: name, severity (`minor`, `moderate`, `major` or `severe`), description, and the ladder. The ladder is a list of steps for the 1st to 5th offense. The lookup, cheat sheet, search and log builder all read this one list.
- **Rule explanations (example, not a violation, staff tip):** find `const RX = {`. Add an entry with the same name as the rule.
- **R/A checklist:** find `const CK = [`.
- **Scenario quiz:** find `const SC = [`.
- **Glossary:** find `const GL = [`.
- **Ready-made hints:** find `const HT = [`.
- **Colors:** find `:root {` at the top of the style block. Each tab's accent color is in the lines that start with `[data-v=`.
- **Ranks, conduct, appeals and FAQ text:** search for the heading, then edit the text next to it.

## Two guides in one site

The site holds two guides. Use the **Guide** dropdown in the top bar (inside the **Menu** on phones) to switch between the **Staff Handbook** (ER:LC moderators) and the **Discord Mod Guide** (Discord moderators). Each guide has its own tabs, and each tab has its own link, like `#/drules`.

- **Staff Handbook:** the original handbook for ER:LC staff.
- **Discord Mod Guide:** Welcome, Server Rules, Mod Tools, Incidents (with a mod log builder and DM templates), Tickets (with ready replies), Safety and Raids, Mod Conduct, Practice scenarios and FAQ.
- **Edit the Discord rules:** find `const DR = [` in `index.html`. Each rule has a name, a severity, a description, the action ladder and an example. The rule list, lookup and log builder all read this one list.
- **Fill in the [brackets]:** the Discord pages use placeholders like `[bot prefix]`, `[rules channel]` and `[appeals channel]`. Search `index.html` for `[` and replace them with your real server details.

## View modes (PC, Mobile, Console)

The site picks a view for each device automatically, and anyone can change it with the **View** dropdown in the top bar (inside the **Menu** on phones). The choice is saved on that device.

- **PC:** full tab row across the top, wide layout.
- **Mobile:** one-column layout, a **Menu** button with every tab, bigger tap targets.
- **Console:** bigger text, bold focus outlines, and a controller hint bar. Use the D-pad or left stick to move, **A** to select, **LB / RB** to switch tabs, **B** to go Home and **Start** to search. Arrow keys and Enter work too. Controller support depends on the console's browser, so the View dropdown also works as a fallback.

## Progress, levels and badges

The Home tab tracks each staff member's progress on their own device: tabs visited, quiz results, logs copied and R/A checklist items. It turns them into XP and levels (Rookie, Patroller, Veteran, Chief, Legend) and a row of badges. Nothing is sent anywhere, and **Reset progress** clears it. Level names and XP amounts are in `const LV`, `const BD` and the `xp` function.

## Install as an app and offline use

Upload all of these files to the top level of the repo, not just `index.html`: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png` and `icon-512.png`. After that, phones and computers can install the site like an app (an **Install as an app** button appears in the footer, or use your browser's menu), and it keeps working when the internet drops. Updates still show up as soon as you are online.

## Shortcuts

- Keys `1` to `0` open the first ten tabs.
- `/` or `Ctrl K` opens search. Press `Tab` to autofill a suggestion.
- The cheat sheet has a print button for a clean paper copy.

## Troubleshooting

- **Blank page or old version:** hard refresh with Ctrl+Shift+R.
- **Tabs do nothing:** make sure you uploaded the newest `index.html`.
- **Changes not showing on GitHub:** check that the commit finished and that Pages shows "Your site is live".
