# CBD Coffee Roulette ☕

A map of our Auckland CBD coffee spots, with a button that picks one for you.

Everything lives in two files:

- `index.html` is the app. You shouldn't need to touch it.
- `places.json` is the café list. Edit this one.

## Put it online (one-off, about 5 minutes)

1. Create a new **public** repository on GitHub (e.g. `cbd-coffee`).
2. Click **Add file → Upload files**, drag in `index.html`, `places.json`, `README.md`
   and the `.github` folder, then **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, set Source to
   **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then **Save**.
4. After a minute or two the site appears at
   `https://<your-username>.github.io/cbd-coffee/`. Share that link with the group.

To let others edit the list: **Settings → Collaborators → Add people**.

## Add, edit or remove a café

1. Open `places.json` on GitHub and click the ✏️ pencil icon.
2. Make your change (see below), then **Commit changes**.
3. The site updates in about a minute. Refresh the page.

**Adding:** copy an existing `{ … }` block and paste it after the last one.
Every block except the last needs a comma after its closing `}`.

```json
  {
    "id": "new-place",
    "name": "New Place",
    "address": "123 Queen Street, Auckland CBD",
    "lat": -36.8480,
    "lng": 174.7650,
    "notes": "Optional. Anything useful, e.g. weekdays only."
  }
```

**Getting lat/lng:** in Google Maps, right-click the exact spot and click the
numbers at the top of the menu (e.g. `-36.84475, 174.76455`). That copies them.
The first number is `lat`, the second is `lng`. Paste them without quotes.

**Removing:** delete the whole `{ … }` block, and make sure the block before it
doesn't end up with a trailing comma if it's now last.

## If you break it

A JSON typo, usually a comma, stops the list from loading. Two safety nets:

- The site shows a red box saying what's wrong instead of a blank map.
- Each commit runs an automatic check (**Actions** tab). A red ❌ next to your
  commit means `places.json` is broken. Click it to see which line.

To undo a bad edit, open `places.json` → **History**, find the last good
version, and copy its contents back in.

## How "Pick for me" works

- **Anywhere in the list:** picks at random from every café.
- **≤ N min walk from me:** asks for your phone's location and picks only
  from cafés within that straight-line walking distance. Real routes are a bit
  longer, so treat it as a rough guide.
- It never picks the same place twice in a row.

Opening hours aren't tracked on purpose, because they go out of date fast.
Put stable facts like "weekdays only" in `notes`.

## Map data

The map is © OpenStreetMap contributors. It's free to use, with no API key or
billing. Fine for a small group, but it isn't meant for heavy traffic.
