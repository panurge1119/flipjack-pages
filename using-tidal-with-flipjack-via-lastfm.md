# Using Qobuz with FlipJack via Last.fm

FlipJack displays your currently playing song using **Last.fm scrobbling**. Once Qobuz is connected to Last.fm, FlipJack will automatically show whatever you're listening to — on any of your devices.

This guide walks you through every step, from creating accounts to seeing your first track on the board.

---

## What You'll Need

- An Apple TV with the FlipJack app installed
- A Qobuz account (any plan)
- A free Last.fm account
- The Qobuz **desktop app** (Mac or Windows) **or** access to the Qobuz **web player** — this is required for the one-time setup step

> **Why the desktop app?** Qobuz only allows you to link your Last.fm account through the desktop app or web player. You cannot connect them through the iPhone or iPad app alone. Once linked on desktop/web, scrobbling will also work when you listen on your phone.

---

## Step 1 — Create a Last.fm Account (skip if you already have one)

1. On your phone or computer, open a browser and go to **[last.fm/join](https://www.last.fm/join)**.
2. Enter a username, email address, and password, then click **Create account**.
3. Verify your email address if prompted.
4. Make a note of your **Last.fm username** — you'll need it in Step 3.

> **Important:** Your Last.fm profile must be set to **Public**. If it is private, FlipJack cannot read your scrobbles.
>
> To check: go to [last.fm/settings/privacy](https://www.last.fm/settings/privacy) and make sure **"Hide recent listening information"** is turned **off**.

---

## Step 2 — Connect Qobuz to Last.fm

### Option A — Using the Qobuz Desktop App (Mac or Windows)

1. Open the **Qobuz** desktop app and sign in.
2. Click your **profile name or avatar** in the top-right corner.
3. Click **My Account** or **Account Settings**.
4. Look for a section called **Linked Accounts**, **Connected Services**, or **Integrations**.
5. Find the **Last.fm** logo and click **Configure** or **Connect**.
6. A browser window (or pop-up) will open asking you to sign in to Last.fm.
7. Sign in and click **Allow access** when asked.
8. Return to Qobuz — you should see a confirmation that Last.fm is connected.

### Option B — Using the Qobuz Web Player

1. Open a browser and go to **[play.qobuz.com](https://play.qobuz.com)**.
2. Sign in to your Qobuz account.
3. Click your **profile name or avatar** (top-right corner).
4. Click **My Account** or **Settings**.
5. Look for a **Linked Accounts** or **Integrations** section.
6. Click the **Last.fm** logo or **Configure**.
7. Sign in to Last.fm and click **Allow access**.
8. You should see a confirmation that the accounts are now linked.

### Verify it's working

1. Play any song in Qobuz (desktop or web player).
2. After 30–60 seconds, go to **[last.fm/home](https://www.last.fm/home)** and check your **Recent Tracks**.
3. If your song appears there, scrobbling is working correctly.

---

## Step 3 — Set Up Last.fm in FlipJack

1. On your Apple TV, open **FlipJack**.
2. From the Main Menu, select **Settings**.
3. Select **Music Source**.
4. Select **Last.fm**.
5. A setup screen will appear. Using the on-screen keyboard, enter your **Last.fm username** (the one you created in Step 1).
6. Select **Test & Save**.
   - If you see **"✓ Connected!"** — you're all set. FlipJack will return to the Main Menu automatically.
   - If you see an error, see the [Troubleshooting](#troubleshooting) section below.

---

## Step 4 — Launch the Display

1. From the Main Menu, select **Launch**.
2. Play a song in Qobuz on any of your devices.
3. Within **5–30 seconds**, the song title, artist, and album will appear on the split-flap board.

> **Why the delay?** Last.fm typically takes 5–30 seconds to reflect a new track after Qobuz starts playing it. This is a Last.fm server delay, not a FlipJack issue. Once the track registers, FlipJack will pick it up on its next 3-second poll.

---

## Listening on iPhone or iPad

Once you've completed the one-time setup in the desktop app or web player (Step 2), **scrobbling will also work when you listen on your iPhone or iPad** — no additional setup needed.

However, be aware of a known Qobuz mobile limitation:

> **Qobuz on iPhone may only scrobble every 10 minutes or so**, rather than in real-time. This means FlipJack could continue showing a previous track for longer than usual. This is a known Qobuz iOS limitation and is not something FlipJack can work around.

### Workaround for more reliable iPhone scrobbling

If you primarily listen on iPhone and want more accurate real-time scrobbling:

1. Install **[Web Scrobbler](https://apps.apple.com/app/web-scrobbler/id1460810357)** from the App Store (free).
2. Open Safari on your iPhone and go to **[play.qobuz.com](https://play.qobuz.com)**.
3. Enable Web Scrobbler for the Qobuz web player by following the in-app instructions.
4. Listen via Safari instead of the native Qobuz app for more reliable scrobbling.

---

## Troubleshooting

### "Username not found or profile is private"
- Double-check that you typed your Last.fm username correctly.
- Make sure your profile is **public**: [last.fm/settings/privacy](https://www.last.fm/settings/privacy) → turn off **"Hide recent listening information"**.

### FlipJack shows the wrong song or a previous song
- Last.fm has a 5–30 second reporting delay. Wait a moment — the display will update on the next poll.
- If you're listening on iPhone, the delay may be longer due to Qobuz's infrequent mobile scrobbling (see [Listening on iPhone or iPad](#listening-on-iphone-or-ipad) above).

### FlipJack shows nothing even though Qobuz is playing
1. Confirm Qobuz is linked to Last.fm (go back through Step 2 and verify the connection is still shown as active).
2. Go to **[last.fm/home](https://www.last.fm/home)** and check **Recent Tracks** — if your song isn't appearing there, the issue is with Qobuz's scrobbling, not FlipJack.
3. Some tracks (very short clips, previews) may not be scrobbled. Try a full-length album track.
4. Make sure you've played the song for at least **30 seconds** — Last.fm only scrobbles a track after you've listened to a meaningful portion of it.
5. The Qobuz–Last.fm link can occasionally disconnect after a Qobuz or Last.fm password change. Go back to Step 2 to reconnect.

### FlipJack shows "nothing playing" after I stop Qobuz
- This is expected behavior. Last.fm only marks a track as "now playing" while it's actively being scrobbled. Once you pause or stop, FlipJack will return to the idle animation within a few seconds.

### I changed my Last.fm username
- In FlipJack, go to **Settings → Music Source → Last.fm** and select **Change Username** to update it.

### I already use Last.fm with another app — will I get duplicate scrobbles?
- If you're also scrobbling Qobuz through a third-party app (like Roon or Pano Scrobbler), you may see duplicate entries in your Last.fm history. To avoid this, disable scrobbling in the other app and leave it enabled only in Qobuz directly.

---

## Notes for Other Streaming Services

Last.fm scrobbling works the same way for many other services. If you use a different streaming app, see the relevant guide:

| Service | Guide |
|---------|-------|
| **Tidal** | [setup-tidal-lastfm.md](setup-tidal-lastfm.md) |
| **Spotify** | Settings → Social → Connect to Last.fm |
| **Apple Music** | Use the [Scrobbler for Last.fm](https://apps.apple.com/app/scrobbler-for-last-fm/id1299887439) app on iPhone |
| **Deezer** | Settings → Connected Apps → Last.fm |

Once any of these services is connected to Last.fm and scrobbling, FlipJack will display your now-playing track automatically — no additional setup needed.
