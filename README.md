# Mum's Care Checklist 💚

A shared, live-updating care checklist for coordinating mum's daily care across family members and carers. Everyone with the link sees the same live checklist — tick a box on one phone and it appears ticked on everyone else's within seconds.

No apps to install. No accounts needed. No payments, ever. Works on any phone, tablet, or computer with internet.

---

## What this is, in plain English

Caring for someone at home usually involves multiple people — family, visiting carers, night staff — each doing a handful of tasks at set times throughout the day. Keeping track of *who did what, when* matters, both for continuity of care and for the medical record.

This is essentially a paper care sheet, but digital and shared. When the morning carer ticks "9:30 AM – Feed mum", everyone else can see it's done. When someone writes "Ate half a banana, 150ml water" in the Daily Record, everyone sees the note. If someone hasn't done their shift's tasks, it's visible at a glance.

The checklist covers:

- **Day shifts** at 9:30 AM, 11 AM, 1:30 PM, 3:30 PM, and 6 PM
- **Night shifts** at 9:30 PM, 11 PM, 2 AM, 5 AM, and the 7:30 AM morning freshen-up
- A **Trolley Ready Check** (pad, wipes, gloves etc.) pinned to the top
- A **Daily Record** for writing notes on food eaten, fluids taken, and nappy contents
- An **Activity feed** showing who ticked what, who wrote in the record, and who reset the day

---

## For carers and family — how to use it (dummies guide)

### First time opening the link

1. Tap the link you were sent on WhatsApp (or however you received it)
2. It opens in your browser — no downloads, no sign-up
3. Type your **first name** (e.g. "Sarah") and tap **Open Checklist**
4. That's it — you're in. You'll only need to type your name once per device.

> 💡 **Bookmark the link** so you can get back to it quickly. On iPhone: tap the share icon → Add to Home Screen. It then works like an app.

### Using it during a shift

**At the top of every shift:**

1. Tap today's day at the top (**Mon**, **Tue**, etc.)
2. Choose **☀️ Day Shifts** or **🌙 Night Shifts**
3. Glance at the **Trolley Ready Check** — make sure all items are present before starting
4. Glance at the **Activity feed** to see what's already been done

**As you do each task:**

- Tap the checkbox next to a task the moment you finish it
- The tick immediately syncs to everyone else's phone
- Under each ticked task you'll see *"Sarah ticked @ 09:42"* so everyone knows who did it and when
- If you tick something by mistake, just tap it again to untick

**Throughout the day:**

- Open the **Daily Record** section at the bottom
- Jot down what mum ate, how much she drank, and nappy contents
- Your notes save automatically about a second after you stop typing
- Each new note you write appears in the activity feed once

### Understanding the sync indicator

Top right of the screen:

| What you see | What it means |
|---|---|
| 🟢 Green dot + "Synced 09:42" | Everything's saved, screen is up to date |
| 🟡 Yellow dot + "Saving…" | Saving in progress — normal, takes ~1 second |
| 🔴 Red dot + "Connection issue" | Lost internet — ticks will sync when back online |

If the red dot appears, your local ticks are safe on your screen, but won't be visible to others until your connection comes back. Avoid ticking new things in the meantime if possible.

---

## Do ✅ and Don't ❌

### ✅ DO

- **Tick tasks in real time** — as you do them, not at the end of the shift
- **Use your real first name** so others can see who did what
- **Write in the Daily Record** whenever you notice anything worth recording (appetite, fluid intake, any concerns)
- **Check the Activity feed** at the start of your shift to see what's already been done
- **Pull down to refresh** or hard-refresh (hold reload button → Reload) if something looks out of date
- **Bookmark the link** on your home screen for quick access
- **Tell the main person** if you notice the sync isn't working so they can fix it

### ❌ DON'T

- **Don't tap the big red Reset button** unless you're deliberately starting a fresh day — it wipes ALL ticks, ALL trolley items, AND all notes in the Daily Record for that whole day. Everyone will see it cleared.
- **Don't tick tasks you haven't actually done.** Other carers rely on the record to know what still needs doing. A false tick could mean mum misses a meal or medication.
- **Don't untick someone else's tick** unless you know for certain it wasn't done
- **Don't share the link outside the trusted family/carer group.** Anyone with the link can edit everything.
- **Don't have two people type in the same Daily Record box at the same time** — one person's save may overwrite the other. Coordinate, or wait for the other person to finish.
- **Don't worry if your phone goes to sleep** — the checklist is still there when you wake it up, though you might want to hard-refresh to get the latest ticks.

---

## Starting a new day

At the beginning of each new day (or whenever the current day's data is no longer needed):

1. Make sure the record is safe to clear (photograph it first if it's going into a medical file)
2. Tap the **🗑️ Reset entire [Day]** button at the bottom
3. A confirmation box will pop up listing exactly what will be cleared
4. Confirm
5. All ticks, trolley items, and record notes for that day are wiped for everyone
6. A note appears in the activity feed: *"🗑️ Sarah Reset everything for Monday — 07:15"*

This reset only affects the day you're currently viewing. Other days stay untouched.

---

## Troubleshooting

### "I ticked something but it unticked itself"

This shouldn't happen anymore, but if it does: hard-refresh the page (hold the reload button → Reload, or swipe down firmly from the top). If it continues, tell the main person — they may need to check the storage.

### "The page is stuck on loading"

Check your internet connection. If the connection is fine, close the browser tab and reopen the link. If still stuck, tell the main person.

### "It's asking for my name again"

You probably cleared your browser data or are on a different device. Just type your name again — no harm done.

### "I accidentally tapped reset"

If nobody else has interacted with the page yet, there's no recovery — the data is cleared. Tell the group immediately so whoever was working the shift can re-tick what they'd already done.

### "Someone else's ticks keep appearing"

That's the feature working — not a bug! The checklist is shared and shows what everyone has done.

---

## For the owner — technical notes

This section is only relevant if you need to make changes or troubleshoot. If everything's working, ignore it.

### How it's built

- **Frontend:** plain HTML, CSS, and JavaScript in a single file (`index.html`). No build step, no framework, no npm.
- **Storage:** [Pantry Cloud](https://getpantry.cloud) — free JSON storage with unlimited free requests for personal use. Data lives in a single "basket" called `mum-care-v1`.
- **Hosting:** GitHub Pages serving the single HTML file from the repo's main branch.

### The Pantry ID

Your Pantry ID is hardcoded in `index.html` on the line:

```javascript
const PANTRY_ID = '17f5db4d-7978-4bbf-8052-45e20a3b4e60';
```

**Keep this reasonably private** — anyone who knows it can read/write your checklist data. It's not a security risk if leaked (it's just a checklist, not health records), but best kept to the trusted group.

### Making changes

To change tasks, times, or anything else:

1. Download `index.html` from your GitHub repo
2. Open it in a text editor (VS Code recommended, or TextEdit in Plain Text mode on Mac)
3. Edit the relevant section — e.g. `DAY_SLOTS`, `NIGHT_SLOTS`, `CARE`, `TROLLEY` arrays near the top
4. Save
5. Upload back to GitHub (delete the old `index.html` first, then upload the new one — or use the pencil edit button on GitHub's file view)
6. Wait ~1 minute for GitHub Pages to update
7. Hard-refresh the live link

### Wiping everything permanently

If you want to completely reset the backing data (e.g. someone misused it and you want a clean slate), run this in a terminal:

```bash
curl -X DELETE "https://getpantry.cloud/apiv1/pantry/YOUR_PANTRY_ID/basket/mum-care-v1"
```

Then recreate it:

```bash
curl -X POST "https://getpantry.cloud/apiv1/pantry/YOUR_PANTRY_ID/basket/mum-care-v1" \
  -H "Content-Type: application/json" \
  -d '{"checks":{},"who":{},"trolley":{},"records":{},"activity":[]}'
```

### If Pantry ever disappears

Pantry is a free community service and could in theory shut down one day. If that happens, any similar free JSON-blob service (JSONBin, npoint, etc.) can replace it with small edits to the `pantryGet`/`pantryPost` functions. The data schema is simple enough that migrating would take about 30 minutes.

### Known limitations

- **No conflict resolution:** if two people tick/edit simultaneously, the last save wins. Practically fine for care coordination where people aren't hammering the same task at once.
- **No history beyond the activity feed:** only the last 20 actions are kept. For long-term records, photograph or export the Daily Record before resetting.
- **No authentication:** anyone with the link can edit. This is the trade-off for "no accounts needed."
- **Browser cache:** GitHub Pages uses aggressive caching. After updating, users may need a hard-refresh to see changes.

---

## Credit and context

Built iteratively with Claude (Anthropic's AI assistant) in April 2026 to solve a real care coordination problem at home. The code is simple enough that anyone with a bit of JavaScript knowledge can extend it. Feel free to fork, adapt, and use for other care situations.

With care. 💚
