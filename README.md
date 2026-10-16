# Good Night Sleep Tight · 作息回正

**English** · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

> Fix a late-night sleep schedule one small step a day, until you're sleeping at **23:00** and waking at **08:00**.

Good Night Sleep Tight (作息回正, "setting your routine straight") is a small web app for people whose body clock has drifted late: falling asleep at 2 a.m., waking at 10:30, and unable to "just go to bed earlier." Instead of asking you to jump straight to the goal, it moves your bedtime and wake time earlier by 15 minutes at a time. It only moves you forward once your body has actually caught up.

No sign-up and no server. It's one HTML file, and your data never leaves your phone.

<p align="center">
  <img src="docs/screenshot-setup.jpg" width="250" alt="First-run setup: enter your usual bedtime and wake time">
  <img src="docs/screenshot-today.jpg" width="250" alt="Today view: tonight's bedtime, tomorrow's wake time, a 24-hour dial and the two-tap check-in">
  <img src="docs/screenshot-log.jpg" width="250" alt="Log view in dark mode: streaks and a chart of planned bedtimes">
</p>

## Try it

- **Live app:** https://claude.ai/artifact/N1Yr1VDgdJAJEbv1AX2Hi7. Open it on your phone. Anyone with the link can use it.
- **GitHub Pages:** once Pages is enabled for this repo, the app is also served at https://f64081169.github.io/GoodNightSleepTight/.
- **Offline:** download `index.html` and open it in any browser.

The app's interface is in Traditional Chinese.

## Why gradual?

Your circadian clock can only shift about 15–30 minutes a day. Jump three hours at once and you get the same thing as jet lag: you lie awake, get frustrated, and give up. This app follows the standard behavioural approach to a delayed sleep schedule:

| Principle | What the app does |
|---|---|
| **Gradual phase advance** | Moves bedtime and wake time earlier by one small step, and only after you've kept up. |
| **Wake time is the anchor** | Wake at the planned time even after a bad night. That builds sleep pressure for the next evening. |
| **Bedtime is the *earliest* time** | Go to bed when you're sleepy, not before. Lying awake in bed is how insomnia gets learned. |
| **Morning light** | 20–30 minutes outdoors right after waking, the strongest signal for shifting the clock earlier. |
| **Dim evenings** | Lights down 2 hours before bed, phone away 45 minutes before. |
| **Caffeine & nap cutoff** | Nothing caffeinated, and no naps, within 8 hours of bedtime. Naps capped at 20 minutes. |
| **Stimulus control (CBT-I)** | Can't sleep after 20 minutes? Get up, do something dull in dim light, and come back when sleepy. |

### When does the plan move forward?

Each morning you answer two questions with two taps:

| How you woke up | Fell asleep within 30 min | Took over 30 min | Went to bed late |
|---|---|---|---|
| **On time** (±15 min) | ✅ Step forward | ⏸ Stay | ⏸ Stay |
| **15–30 min late** | ⏸ Stay | ⏸ Stay | ⏸ Stay |
| **Over 30 min late** | ⏸ Stay (late) | ⏸ Stay (late) | ⏸ Stay (late) |

Falling asleep slowly is the body's way of saying the clock hasn't caught up yet. Pushing forward anyway only means more time awake in bed, so the plan waits.

### Pace

| Pace | Step | Example: 02:00 / 10:30 → 23:00 / 08:00 |
|---|---|---|
| Gentle | 15 min every 2 days | about 24 days |
| **Standard** (recommended) | 15 min a day | about 12 days |
| Fast | 30 min a day | about 6 days |

You can switch pace at any time without losing progress.

## Features

- **Tonight at a glance.** Tonight's earliest bedtime and tomorrow's wake time in big type, plus a 24-hour dial showing your sleep window against the goal.
- **Daily timeline.** Wake, morning light, breakfast, caffeine/nap cutoff, exercise cutoff, dim the lights, wind down, bed. Every time is calculated from tonight's plan. Tap an item to tick it off.
- **"Next up" countdown.** There are no push notifications, so the top of the page always shows the next thing to do and how long until it.
- **Two-tap morning check-in.** Pick a wake-up answer, then a sleep answer, and it submits on its own. You get a 5-second undo, and you can edit the answer later that day.
- **A "sleep day" that matches night owls.** The day rolls over 3 hours before your planned wake time, so opening the app at 00:30 still shows *tonight*, not tomorrow.
- **Forgiving by design.** Three late mornings in a row suggest stepping back one stage. After a break of 3 or more days you get a "welcome back" card that suggests warming up again. After you reach the goal, the app watches for your schedule creeping late again.
- **Safety checks.** It warns about likely AM/PM mix-ups on 12-hour phones, flags daytime sleep schedules (often shift work, which this plan doesn't suit), and points you to a sleep specialist when the gap is very large. It also reminds you not to drive when drowsy.
- **Delaying works too.** If your goal is *later* than your current schedule, the light advice flips: avoid morning light and get light in the evening.
- **Progress & history.** On-time streak, 7-day on-time rate, current stage, a chart of planned bedtimes coloured by result, and a table of recent check-ins.
- **Goal reached.** A card you can screenshot, with ready-made text to send to a friend.
- **Backup code.** Copy one string to move your data to a new phone or browser. The app nudges you to back up weekly, because some browsers (iPhone Safari, for example) clear data for sites you haven't opened in a while.
- **Light and dark mode**, phone-first layout, keyboard navigation and visible focus.

## How to use it

1. **Day 1.** Enter the time you usually go to bed and wake up. The target (23:00 / 08:00) and pace are pre-filled; tap **修改** ("Edit") to change them. Sleep at your usual time tonight.
2. **Every morning.** Open the app and tap twice: how you woke up, and how you fell asleep. If you kept up, tonight's times move one step earlier.
3. **During the day.** Follow the timeline. The most important items are morning light and the caffeine cutoff.
4. **Every evening.** The countdown tells you when to dim the lights and when you can go to bed. If you're not sleepy yet, wait.
5. **Once a week.** Copy your backup code from the **紀錄** ("Log") tab.

## Privacy

- No account, no analytics, no server. All data stays in your browser's `localStorage` on your own device.
- The person who sent you the link can't see your data, and you can't see theirs.
- The only external request is to Google Fonts for typefaces. If fonts are blocked, the app falls back to your system fonts.

## Self-hosting

It's a single static file with no build step and no dependencies.

- **GitHub Pages:** go to *Settings → Pages → Build and deployment*, set Source to *Deploy from a branch*, pick `main` and `/ (root)`, then save. A minute later the app is at `https://<user>.github.io/GoodNightSleepTight/`.
- **Anywhere else:** upload `index.html` to any static host (Netlify, Cloudflare Pages, Vercel, your own server), or open it straight from disk.

## Under the hood

- One `index.html`: HTML, CSS and vanilla JavaScript. No framework, no bundler.
- **Position-based model:** `origin` (where you started), `pos` (tonight's bed / tomorrow's wake) and `tgt` (the goal). Moving forward moves `pos` one step toward `tgt`; stepping back moves it toward `origin`. Because of this, changing pace never resets your progress.
- Every check-in stores the state from before it, so edits and undo are exact.
- Saved data is validated on load and on restore. If something is corrupted, the app offers a clean reset instead of a blank screen.

## How it was built

The app was designed and built with Claude (Anthropic) in Claude Code. It then went through three review rounds with two AI agents. One played a UX researcher: a friend opening the link on a phone for the first time, and later someone two weeks into the plan. The other played a sleep educator familiar with CBT-I and circadian science. In each round the two agents debated the current version, agreed on a prioritized list of changes, and the changes were implemented and tested at phone width.

## Disclaimer

This is a general sleep-hygiene tool, **not medical advice**, and it is not a substitute for diagnosis or treatment.

Please see a sleep specialist if any of these apply:
- You've had insomnia 3+ nights a week for over 3 months.
- Someone has noticed loud snoring or pauses in your breathing.
- Daytime sleepiness affects driving or work.
- Your schedule keeps drifting later no matter what you try.
- Your mood has been low for a long time.

Melatonin can help shift the clock, but it is prescription-only in some countries (including Taiwan). Ask a doctor about the dose and timing.
