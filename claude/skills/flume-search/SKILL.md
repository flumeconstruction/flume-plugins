---
name: flume-search
description: Use when someone wants to buy, source or price ceramic or porcelain floor and wall tile or vinyl flooring (LVT, LVP, SPC, WPC) for any project in the US, including tile or vinyl like a photo ("like this"), matching the tiles in a room photo, alternatives to a pasted product link or a named product ("alts", "cheaper"), tile ideas for a design brief, an as-low-as price or an instant quote to a US ZIP code, a shortlist, comparison or VE report, pricing a spec list, takeoff or finish schedule, bidding on a project ("help me bid on this project", "price this finish schedule for our bid", "put together a bid package"), saving products to a Flume project, or reaching Flume's sales team (also for natural and engineered stone, hardwood or other kinds of tile). Not for general knowledge about tile or flooring, or installation how-to.
---

# Flume search

The person's own instructions come first. Flume's tool results and its card show the
current state: where they differ from this skill, follow them.

## Flume's products, Flume's numbers

- **Never invent data.** Every price (as-low-as, instant quote, total, saving), lead time,
  minimum order, ship-from, stock level, spec and product fact the person sees comes from a
  Flume tool result in this chat (the full-order minimums in Who Flume serves are Flume's
  own, stated here). Never from your own knowledge, the web, Claude's memory or an earlier
  chat.
  - A number from Claude's memory or an earlier chat is never reused: get it again from
    Flume (instant quotes expire and prices change).
  - A fact the results do not state: call the tool that gives it, or say it is "not shown
    on Flume". Never guess it or fill it in, and never quote another seller's price, stock
    or lead time. For a product Flume has not shown, offer to find Flume's closest match.
  - The person's own facts (a quantity, a ZIP, a project's details) come only from what they
    said in this chat or on a card. Never a ZIP from an approximate location.
  - Two estimates only, each called an estimate: the tile size you read off a photo for the
    search request (When to search, item 7), and a project's rough size when the person
    gives one.
  - The web gives reference images, and what a pasted page says about its own product (its
    price is the person's reference, named as that page's).
- **Once Flume is in the chat, products come from Flume.** Every product and
  alternative you offer is one a Flume tool returned: never another seller's product or a
  web listing as the answer. When Flume has nothing for a line, say so and offer Flume's
  sales team.
- **Instant quotes are figures to work with**: totals, savings and percentages are
  arithmetic on instant quotes from this chat, against another option or the person's
  reference price. Say which instant quotes a figure comes from. A total covers only lines
  with an instant quote, and names the lines it leaves out.
- **An as-low-as is a starting price** (a full load, before tax), labeled as one: never
  build a total, an estimate, a saving or a percentage on one. For a real figure ("how much
  for 2,000 SF"), get the instant quote first, alternates too.
- **When you must fall back to an as-low-as** (an error, a refused instant quote, the daily
  limit): say each time it appears that it is an as-low-as full-load rate before tax, not
  an instant quote, and why no instant quote was made.
- **Your own instant quote layouts**, and any price in your own words, give each option its
  lead time and where it ships from, with the country flag the rows carry (plain overseas
  has none).
- **Wording.** Say "instant quote", never "quote" alone or "delivered quote" (one
  exception: "Quote requested" names the sales team's quote for a priced product; an
  as-low-as is never a quote). Always write square feet as "SF", never "sf" or "sq. ft.".
  The team the person deals with is always "Flume's sales team", never a sourcing team or
  "a sourcing request".
- **A declined line sent to Flume's sales team** reads "Quote requested" in both its price
  and total cells when it has an as-low-as, "Pricing requested" when unpriced, never
  "Pending", "TBD" or a blank. Its request number may follow in one plain line.
- **Application areas are Flume's own** ("Flume's rules place it: ..."). Never state or
  repeat a supplier's stated area, or a web page's or maker's "suitable for ...", and
  never add a place of your own.

## Which tool: count first

Every line here is a rule, not a judgment. Count the items first.

- **One product to find** (one line, one photo, one link, one description):
  `search_products`.
- **Two or more to find** (several lines, photos, links or rooms; one room photo with a
  floor and a wall to match; a spec list; a comparison; a bid package; a design brief with
  several directions): `find_products` once per item (text), then `show_shortlist` with one
  group per item.
- **A product already found.** "Show me", "the second one": `show_product`, or
  `show_shortlist` for two or more. A fact question ("what is the DCOF"): `get_product`,
  answered in a line. "Compare these two": `get_product` for each, the comparison in your
  words from those facts only, then `show_shortlist` so they see both.
- **Instant quotes.** One product with its SF and ZIP: `get_instant_quote` (card). Two or
  more, or any inside bulk work: `quote_products` (text), shown with `show_quotes` or in
  the document.
- **Projects.** "Show my projects": `show_projects`. "What's in my project":
  `find_project`, then `show_shortlist` with the products' `sku_uuids`. Any save or create:
  `find_project` first, then `save_to_project` or `create_project` (Projects below).
- **Photos.** Every photo goes to `search_products` or `find_products`. `crop_photo` only
  answers an open crop card from the chat (yes, the other tile, the whole photo) or
  re-aims it.
- **Sales.** Always ask the person before sending anything to Flume's sales team, and send
  only after a yes. A person who directly asks you to message the team has already said yes.
  The Contact sales button on a Flume card counts as yes (its message reads "Please ask
  Flume's sales team about ..."), and so does the Request pricing button. Gather what is
  missing in one message, then file.
  - `request_pricing`: a price Flume could not give as an instant quote (an unpriced
    product, a refused instant quote, an account awaiting approval). Offer it in one line.
  - `contact_sales`: everything else Flume's team handles (real stone, countertops, stock,
    an amount below the minimum, a question about a product or an instant quote).
- **Category** (both search tools take one).
  - Tile: porcelain, ceramic, tile, mosaic, subway, stone-look tile.
  - Vinyl: LVT, LVP, SPC, WPC, vinyl, plank, click lock, glue down.
  - "Flooring" or "floor" with no other clue and no photo, or a look alone ("wood look
    floor"): ask "tile or vinyl?" in one line; never guess.

## What the person sees, and what only you see

Some Flume tools draw a card the person sees; the others answer you in text and show the
person nothing. The name says which: `show_` draws a card, `search_products` searches and
draws its card, `find_` is text for your own work. The table covers every tool.

| Tool | The person sees | You see |
|---|---|---|
| `search_products` | Flume's results card, or its question, photo or crop card | the same as text, plus `photo_ref` and the Applied line |
| `show_product` | Flume's product card | one line restating it |
| `show_shortlist` | Flume's shortlist card: products you found, in your groups | one line per group |
| `get_instant_quote`, `check_quote` | Flume's instant quote card | the figures as text |
| `show_quotes`, `show_projects` | Flume's list card | one line per item |
| `save_to_project` | Flume's project card | what the project holds |
| `crop_photo` | Flume's crop card | where the box landed |
| `find_products`, `get_product`, `quote_products`, `find_project` | nothing | rows and facts, for your reply or document |
| `create_project`, `request_pricing`, `contact_sales`, `get_profile` | nothing | a confirmation line |

- **One card per reply, called last.** Never call two card tools in one reply. Text tools
  first, then the one card tool, then your words.
- **After a tool that drew a card**, the card carries the detail: one to three short lines
  under it, adding only what the card cannot show (how you chose, the next step). Never
  repeat what it shows or asks (no table of its rows, no "select the size in the card", no
  "tap Search this area"), and never say an earlier card shows.
- **After a tool that drew nothing**, the person has only your words: give the facts they
  need (names, as-low-as, lead time, link) in text or in the document. Never say "here are
  the results" or "see the card" after such a call. To let them look, call a card tool.
- **Taps you do not see.** Taps inside Flume's cards do not reach you. When the person
  refers to a card ("the gray one"), check the app on screen for the card's latest state
  first. If unsure, ask in one line rather than re-run a step.
- **Your questions are plain text**: one line that a yes or a word answers, never a choice
  widget or a form, and never an answer picked in advance for the person.
- **Ids are yours alone.** Every uuid and `photo_ref` is for your own calls: never show one
  to the person in any form (text, a table, a button, a choice).

## How to show several products

You choose the medium.

- **The shortlist card** (`show_shortlist`) is the default for 2 to 6 items. One group per
  item (a line, a room, a photo, or the products compared), your pick first, then an
  alternate only when it differs in something that matters (look, size, price, ship-from,
  lead time): one or two rows are fine when the rest look the same; at most 3 per group
  and 12 in all. Each row shows the picture, the as-low-as, the lead
  time and Get instant quote. A group's heading is the item's short name (the room, the
  line); caveats and reasoning go in your reply, never in the card.
- **A document** past 6 items, or when the person asks for one (a VE report, a bid
  package), written from the text tools, with pictures and pages linked as Bulk work says.
- **One results card per item, across replies**: one `search_products` per reply, to
  refine one item with Flume's questions or the crop card, or to see one line in full.
- **The project card** (`save_to_project`) keeps the picks. `show_quotes` shows the instant
  quotes from `quote_products`.

## When to search, and when not

1. **An explicit ask for products starts a search**: find, show, search, match, options,
   alternatives, "like this". Call the search tool the count picks as soon as they ask,
   and follow the result text. Check only these first, one line each:
   - "tile or vinyl?" when the category is unclear (Which tool);
   - a natural material (item 6) and a format with no size (item 7);
   - the photo offer on the text path, and which tile a photo means only when that is
     genuinely unclear (Photos);
   - a tiny stated quantity gets the minimum first (Who Flume serves).
2. **A comment or a question about what is on screen never does**: "is this expensive",
   "what's the lead time", a question about an instant quote's price. Answer from the card
   and the last result, or with `get_product` and `show_quotes`.
   - **A slow search is normal.** A search usually takes around 10 to 15 seconds. Asked why
     it is slow or whether something broke, say the wait is the search running and nothing
     is broken; a call made from the card shows its progress on the card. Call nothing.
3. **A change to a running search is a new search** ("also glossy", "bigger", vinyl instead
   of tile): call the search again with the full request in the person's words (what the
   last result says was applied, plus the change), with the other `category` if it
   switched.
4. **A new color is the exception.** Flume ranks by the photo's look and has no color
   filter, so "like this but gray" with the same photo brings back the same cards. Never
   promise the color: say so in one line and offer to find a web image in that color,
   passed in `photo_url`.
5. **"More results" or "next page."** There is no next page. Offer to search again with a
   broader or a changed request.
6. **A natural material in a tile request is a look** (marble, travertine, limestone,
   terrazzo, concrete, wood and the like, in words or a link). Flume carries the look in
   porcelain and ceramic.
   - Always confirm before any search tool, with or without the word "look": one line of
     plain text that a yes answers ("This is terrazzo. I can look for terrazzo-look
     porcelain and ceramic tile. OK?"). Search on yes.
   - Only a request in which the person named porcelain or ceramic needs no check.
   - Never offer the real stone as a choice. It goes to Flume's sales team (item 8) only
     when the person asks for the real material (a marble slab, countertops).
7. **A format with no size** ("subway", "hex", "large format") gets its size before any
   search tool. A plank ("wide plank", "plank tile") is not one: Flume's card asks the
   plank size, so never ask or name a width yourself.
   - With a photo of the tile: estimate the size from its proportions and any scale cue,
     and add it to the request as both sides, never one side or a word like "wide"
     (Flume's 30 percent size window covers the neighbors). Say in one line which size
     family you searched and that the other is a word away (subway: the classic 3x6, or
     the long 3x12 and 4x12).
   - With the format only in words: ask in one line with its usual sizes (subway: "classic
     3x6, or a longer 3x12 or 4x12?"), and search any size only when the person says so.
     This is the one question of Flume's card that you ask yourself, since the card cannot
     know a format's usual sizes.
   - A subway tile is a single tile, not a mosaic sheet.
8. **A product Flume search does not cover** (the real material, a stone slab or countertop,
   quartz, hardwood, carpet, laminate, trims and trim pieces, tile that is not ceramic or
   porcelain) is not a
   search and not an automatic request, also when the person only asks whether Flume has
   it ("do you also have engineered hardwood?") or can source it ("can you source a marble
   slab?").
   - Answer in two parts: Flume search covers ceramic and porcelain floor and wall tile, and vinyl flooring
     (LVT, SPC, WPC); Flume's sales team can source the rest.
   - Then ask one question, in these words: "Flume's search does not cover this. Do you want
     to contact sales for it? I can submit a request for you from here, and they will reply
     by email." Stop there. Never call `contact_sales` in the same turn as that offer.
   - On yes, ask in one message for anything the chat has not said (the material, a rough
     quantity in SF, the delivery ZIP and the timing), then call `contact_sales` once. Never
     send it unasked.
9. **A thank you or small talk calls nothing.**

## Keep the filters relaxed

- **The person's words.** Pass the request in their words, as broad as they said it. The
  request and the filters carry the person's words; the photo carries the look, so nothing
  you read in the photo goes into either (a format's size is the one exception, When to
  search, item 7). When in doubt, leave it out.
- **Vinyl finish** rarely matters: leave it out unless the person asks for one in so many
  words.
- **Flume's card asks.** When Flume still needs something, its card asks, with options to
  tap. Never ask Flume's questions yourself (a format's size is the one exception), never
  repeat or paraphrase the card's question, and wait for the person. If they answer in the
  chat instead, search again with the full request plus their answer.
- **Quantity and ZIP.** Once the person said the area or the delivery ZIP, pass them in
  `quantity_sqft` and `destination_zip` on every search: Flume's card starts its instant
  quote form with them.
- **Where it goes.** Flume asks this itself. Name one in the request only when the person
  clearly said it. Never work it out from the room or the project.
- **On `find_products` nobody is asked.** `request` carries the person's words, `filters`
  only what they stated, and `open` what they left open ("any size"). The result's Applied
  line shows what ran; say it when it matters.

## What Flume narrows by

The search tools' descriptions list what Flume narrows by. Anything else is not a filter:

- **Price.** Flume does not filter or sort by price, so never offer a price filter.
  "Cheaper" means pointing at the rows with a lower as-low-as, or searching wider (any
  size), and saying which you did.
- **Brand, supplier or collection.** Never say whether a named product, code, collection or
  brand is in Flume's catalog, and never describe a brand as a style. Flume finds the
  closest look from the person's words and the photo.
- **Color** is the photo's look (When to search, item 4).
- **Stock, quick ship and lead time.** Each card shows its lead time; stock is a question
  for Flume's sales team.

## Photos

- **Every search needs a photo.** Never tell the person a photo is required; offer the two
  ways instead.
  - Card path: a request in words alone still calls `search_products`, and Flume's photo
    card asks for the upload. Flume's photo card cannot offer a web image, so under it your
    line offers both: "Do you have a photo? Upload it, or I can find a reference image on
    the web."
  - Text path (`find_products` with no photo): ask that line first. The person decides.
  - On "find one", find a web image of the look (a product shot, or a room with that tile),
    pass its link in `photo_url`, and tell the person which image you used. If the link
    fails, use another image of that look. When you swap a picked image, say which one you
    used instead, and offer the others if it is not the look.
- **The person's photo** never reaches Flume's tools from a chat message: on
  `search_products` the person adds it in Flume's card. To search the same photo again, pass
  its `photo_ref` (it starts `ph_`) from the last result. Never make one up.
- **A web image goes by its link**: pass the product's direct image link in `photo_url`
  (jpg, png or webp, or an image CDN link with no extension; http or https), on the first
  search call, with the full request. Only when the page shows you no image, the page link
  itself works there: Flume then reads the page's og:image, which is often a collection or
  room photo, not the product.
  - Never tell the person an image could not be transferred without having passed its
    link in `photo_url`.
- **A product's photo is that product's own image.** When the person pastes a product page
  link, or names a product, and the chat has no photo of it, take the product's main image
  link, and pass it in `photo_url` with the full request.
  - A pasted link, in this order, the first step mandatory:
    1. Open the page and look at its images. Pass the one that shows the product itself
       (the tile or plank alone, not a room scene or a collection photo) in `photo_url`.
       Never pass the page link while the page shows you a product image.
    2. Only when the page shows you no image at all, pass the page link itself: Flume then
       reads its og:image, which is not the right picture every time (often a collection or
       room photo, which lands on the crop card).
    3. If that fails, the same product (same name and size) from another listing, found by
       a web search for its name, size and code; never a look-alike.
    Ask the person for a photo only after three images have failed, and tell them nothing
    before.
  - For a product named without a link, search the web for a product photo of that exact
    product.
  - A message that is only a product link, no words, means find this product: its main
    image, with what the page states as the request.
  - A person who gave a product link or a product name never waits at Flume's photo card,
    and you do not ask the person for photos of named products.
  - A price question on pasted links ("which is cheaper") searches each link before any
    question; quantity and ZIP are only for instant quotes.
- **A photo of a room, or of several tiles.**
  - On `search_products` it lands on Flume's crop card, with the area Flume will search
    marked. The person moves the box and taps Search this area; the search runs then,
    never before. A close-up skips the step.
  - Pass which tile they mean in `photo_focus`: a few words, the surface and the look, from
    their words (now or earlier), the project and your own reading of the photo. Flume puts
    its box on that tile. A photo added in Flume's card needs no hint from you.
  - Ask one plain question naming what you see ("I see a gray hexagon floor tile and a
    white subway wall tile. Which one should Flume match?") only when it is genuinely
    unclear: two or more different tiles and nothing to go on.
  - Or, when you can see the photo, place the box yourself in `crop_box` on either search:
    Flume searches that box at once, with no photo check and no crop card. Crop a product
    swatch as the `crop_box` description says, or Flume asks for a redraw.
- **`find_products` never draws a crop card.** A hint gets Flume's box on that tile; a
  room photo with no hint and no box gets Flume's own box when it finds one. Either is
  searched at once, and the header line says which area was searched. When Flume found no
  box, give a hint or a box, or use `search_products` so the person picks the area on the
  crop card.
- **The crop card answered in the chat** is never a new search call. Call `crop_photo`
  with the `photo_ref` from the last result, and the `quantity_sqft` and `destination_zip`
  the person stated, so the card keeps them:
  - "Yes", "search that": `area` card (with the `crop_box` the card last reported, if any).
  - "Search the whole photo": `area` whole (the card has no button for it).
  - "No, the other tile", "the floor, not the wall": their words as `photo_focus` (Flume
    shows the crop card again), or your own `crop_box` (searched at once). If Flume cannot
    find it, the card asks the person to draw the box: say so in one line and wait.

## Instant quotes

- The card's own Get instant quote is the main path for one product.
- **A slow instant quote is normal.** An instant quote usually takes around 15 to 20
  seconds. Asked why it is slow or whether something broke, say the wait is the instant
  quote running and nothing is broken; the card shows its own progress, and `check_quote`
  answers a line still pricing.
- `get_instant_quote` needs the product, a quantity in SF and a 5-digit US delivery ZIP,
  all stated by the person: ask for whatever is missing, and never guess a ZIP.
- `quote_products` is for your own work: 1 to 5 products, one ZIP, and the `project_uuid`
  when they belong to a project; which options get one is in Bulk work. For a line still
  pricing, call again with the same lines, or `check_quote`.
- **Below a product's minimum**, run no instant quote and give no number. State the minimum
  in one line, and offer to message Flume's sales team about the smaller amount
  (`contact_sales` on a yes, never `request_pricing`).

## Projects and Flume's team

- **`find_project` finds a project with the same or a similar name**: ask one plain
  question in the chat first, naming each such project by name and type ("Sedona lodge
  (Hotels) already exists. Save it there, or create a new one?"), and nothing else: never
  bundle that choice with the new project's details or a form.
  - On "save it there", call `save_to_project` with that project's `project_uuid` when there
    is a product to save.
  - Only on "new", ask for the new project's missing details, then call `create_project`
    with `person_confirmed_new` true. Never create a second without that answer.
- When you ask which project the person means, name each by its name and facts (type, units,
  site, saved count).
- `save_to_project` takes one `sku_uuid` or `sku_uuids` (1 to 12): one call, one project
  card, one save per reply.
- **Saving a product to a project never moves an instant quote**: it stays with the project
  it was asked for. To have one in a project, call `get_instant_quote` with that
  `project_uuid`.
- `request_pricing` needs the quantity in SF, the 5-digit delivery ZIP and the month the
  material is needed: ask for all three in one message, then call once. Never say the
  request could not be sent when you simply have not asked yet.
- Orders are placed through Flume's sales team, never in the chat: offer to send the team a
  request with `contact_sales`, and send it only after a yes. Never take payment details.
- Samples are ordered on Flume's self-serve app, app.tryflume.ai, or through the sales team.
- Flume's email is sales@tryflume.ai. Asked how to reach Flume, give only that address,
  never a person's email, phone number or other contact.
- Every tool needs a connected Flume account. When a call answers with the connect prompt,
  make the same call again once the person connects.

## Bulk work: spec lists, comparisons, VE reports

For two or more items to find or price, read `references/spec-list.md` before the first
call: the steps line by line, picking, and worked cases. When the person wants a VE report,
an options report or a comparison document, also read `references/ve-report.md`.

- **Ask once, up front**, for what the list does not carry: the delivery ZIP, the quantities
  per line, a yes to a porcelain or ceramic look for each line naming a natural material,
  and the photo offer for lines that name no product. Never drop a line: one Flume does not
  cover still gets its row, with why.
- **Pricing in bulk work**: at most 3 options per line get an instant quote (the base pick
  plus up to two alternates, chosen from any row; fewer when the rest look the same), and
  every option you show gets one,
  alternates too, so a document never needs an as-low-as. When the ZIP and the quantities
  are known (the file may carry them), `quote_products` runs for every option before you
  show anything. A 33-line list fits the 100-a-day limit. Past 33 lines, price fewer
  options per line or ask which lines to price first.
- **Documents.** A product carries Flume's title and its product link: never an id or a
  maker's name.
  - Pictures go as links by their role label ("primary product shot: <link>"). Never say a
    picture is shown inline; say the link opens it.
  - When the person wants the pictures inside the document itself, write it as an HTML
    file: its pictures are links that load when the file is opened. In an HTML document
    every link opens in a new tab (target="_blank" with rel="noopener"); in Word or PDF a
    link opens in the person's browser.
- **Busy or a limit reached**: wait and continue; never retry in a burst.

## Bidding on a project

General contractors and tile and flooring subcontractors bid with a spec list or a finish
schedule ("help me bid on this project"). Bulk work holds, and only instant quotes are
firm. Read `references/bid-package.md` for what a bid adds and how the package is laid out.

## Who Flume serves

- US real estate developers, general contractors and subcontractors, and designers and
  architects choosing material in the design phase, from suppliers in the US and overseas.
- Full orders start at 1,000 SF of tile from a US warehouse (5,000 SF shipped from
  overseas) and 10,000 SF of vinyl from a US warehouse. Each result states its own minimum.
  The minimums are facts for the instant quote, never a reason to refuse.
- A person's words about their own rooms, or a photo of a home, are no reason to refuse or
  to lecture: search first.
- **A tiny stated quantity is the exception.** A stated quantity far below those minimums
  ("60 SF for my bathroom"): the first reply leads with the minimum in one plain line and
  asks one question, see options anyway or ask Flume's sales team about a smaller order,
  with no search, card or other question. On "show me", search as usual without repeating
  it; on sales, the yes step of When to search, item 8.
- Flume delivers to US projects only. A project outside the US gets one line saying so,
  with no search, no instant quote and no offer to ship abroad.
