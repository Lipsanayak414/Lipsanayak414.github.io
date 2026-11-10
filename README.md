# Lipsa's Café: personal site

The site is one page, `index.html`, plus the `covers/` folder (book covers) and two photos:
- `me.png`: the hero cut-out.
- `copenhagen.jpg`: used on the corkboard and the About page.
- `photos/`: your trip photos for the Travel journal, resized, with location and camera data removed.
- `sounds/woof.mp3`: Kaas's bark, "Barking of a dog" by Amada44 (CC BY-SA 3.0, Wikimedia Commons). Keep the credit line in the footer if you keep the sound.

It needs no build step and no framework. Keep everything in this folder together.

## How it works

The **hero** shows your name across the top and your cut-out photo in front of a striped arch, with luggage-tag labels around it. Click the photo for a greeting.

The **café room** is the navigation. Hover over an object to see a label; click it to open something.

| Object | Hover label | Click |
|---|---|---|
| Laptop | My projects | Opens the **Projects** page (`#work`). A row on the screen jumps straight to that project. |
| Bookshelf | Recent reads | Opens the **Recent reads** page (`#reads`): wooden bookcases you can browse. Click a book to turn it over and see your review and links. |
| Chalkboard menu | About me: experience and skills | Opens the **About** page (`#about`) with your photo, intro, resume and links. |
| Corkboard | Travel journal | Opens the **Travel journal** page (`#travel`): postcards for recent trips, passport stamps for every country, and your wish list. A postcard opens its post (with its own link, e.g. `#trip-amsterdam`) once it has a story or photos. |
| Coffee cup | Coffee, always | Opens a card linking to your Bookstagram. |
| Puzzle boxes | Puzzle box · five pictures | Opens the puzzle box: pick Canal at golden hour, Copenhagen (your photo), Lipsa's café (the room itself), Island sunset or City lights, at 12 or 24 pieces. Best times are saved in each visitor's browser. |
| Record player | Play some music | Plays lo-fi music made live in the browser. The "Music off" button bottom-left of the room does the same. |
| Window | Turn it into evening | Switches between day and night. |
| Lamp | Switch the lamp off | Switches the lamp off and on. |
| Clock | Amsterdam time | Label only. |
| Cash register | Visit count | Label only. |
| Dog (Kaas, a brown cocker spaniel) | Kaas is napping | Barks (a real recording in `sounds/woof.mp3`) and wags. |
| Espresso machine | Pull a shot | Steams and hisses. |

Each page has a top bar with "← Back to the café", the other pages, and a music button.

## Fill in your details

All personal content is in the `<script>` block at the bottom of `index.html`, under `EDIT ME`:

| Block | What to change |
|---|---|
| `SITE` | Your name, photo and links. `where` adds an optional line at the top right of the hero (empty = hidden). Clear a link to hide it everywhere. Add `email` if you want it shown. |
| `PROJECTS` | Set each `status` (`live` / `done` / `building` / `next`) and add real URLs to `links`; empty links stay hidden. Add `hidden:true` to keep a project off the site (four earlier suggestions are hidden this way). |
| `READS` | The bookshelf: your all-time favourites, then your Goodreads Year in Books for 2026, 2025 and 2024. Each book is `[goodreadsId, title, author]` and its cover lives in `covers/<goodreadsId>.jpg`. To add a book, save its cover there and add a line. |
| `REVIEWS` | What shows on the back of a book when it's turned over. Add an entry keyed by the Goodreads id, for example `"57945316": { stars: 5, text: "Two or three sentences.", insta: "https://www.instagram.com/p/…" }`. All fields are optional, and `goodreads` can point to your own review. |
| `TRAVEL` | The travel journal. `trips` are newest first; for each, add `date`, a `cover` photo, `story` paragraphs and `photos` (`["photos/amsterdam/1.jpg", "Caption"]`) when you're ready. Put photos in `photos/<trip id>/`. `countries` are the passport stamps; `wish` is the wish list. |
| `ABOUT` | The About page intro, drafted from your CV. Rewrite it in your own voice. |
| `MENU` | Your resume, filled in from your CV and shown on the About page. Your phone number is left out on purpose. |

Edit the hero tags and intro sentence directly in the HTML. Search for `class="tags"` and `class="intro"`.

### Changing the hero photo

Use a photo with a plain background. Cut it out to a transparent PNG (on a Mac: open it in Preview, choose Tools → Remove Background, then export as PNG). Save it as `me.png`.

## Visitor counter

When `SITE.counterEndpoint` is empty, the register counts **this browser's** visits. For a real counter across all visitors, set it to any URL that returns JSON like `{"count": 123}` and adds one on each request.

## Put it online (free)

- **GitHub Pages:** add `index.html`, `me.png`, `copenhagen.jpg` and the `covers/` folder to a repo, then go to Settings → Pages → Deploy from branch → `main`.
- **Netlify Drop:** drag the `site` folder onto app.netlify.com/drop.
- **Vercel:** run `vercel` in this folder, or import the repo.
