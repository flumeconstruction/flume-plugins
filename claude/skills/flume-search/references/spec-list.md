# Two or more items into Flume calls

The steps for a spec list, a schedule, a takeoff, several photos or rooms, a comparison or
a design brief. SKILL.md's rules hold throughout; this file adds only the steps and the
worked cases.

## 1. Read the list

- Read every line: the product name or code, material, size, finish, where it goes, and
  quantity.
- Sort each line:

| The line | What happens |
|---|---|
| Ceramic or porcelain tile | `find_products` with `category` tile |
| Vinyl flooring (LVT, LVP, SPC, WPC, rigid core, glue down or click lock planks and tiles) | `find_products` with `category` vinyl |
| Real stone (a line naming marble, travertine or another natural material gets SKILL.md's look question first), quartz, countertops, hardwood, carpet, laminate, trims and trim pieces, tile that is not ceramic or porcelain | Not searched. Its row reads "Flume's sales team", and SKILL.md's sales offer covers it |
| A line that names no product and has no photo | Its row reads "needs a photo" until it has one; go on to the next line |

## 2. Find each line's photo

In this order:

1. The person's photo of that line, or a photo already searched (its `photo_ref`).
2. A line that names a product (a brand, collection, color or product name): a web photo
   of that exact product, as SKILL.md's Photos says.
3. A line that names no product: SKILL.md's photo offer.

When a room photo was searched, carry the header's line on the searched area into the
table.

## 3. Search each line

- One `find_products` per line, all in one reply, whatever the line's quantity: each row
  states its own minimum.
- `request`: the line's facts in plain words, as relaxed as the line states them ("3 x 6
  glossy white ceramic subway tile for a bathroom wall").
- `detail` full for a comparison or a document (each row gets the product page's
  At-a-glance facts); concise for a quick count. `limit`: 8 by default, 24 at most.
- Read the header: the status line, the Applied line (what ran), the `photo_ref`, the
  minimum notice and the terms line.

## 4. Pick

- Flume's ranking is a guide, not an order: any row, strong or other, may be the pick when
  you can say why in one line.
- `get_product` gives the strongest options' specs (labels as the product page prints
  them), and with `images` true up to 8 labeled pictures.
- Judge each option on the facts alone: the line as stated, the full rows and
  `get_product`. Never on a brand's reputation or a picture you have no label for.
- Check a figure the line states (wear layer, slip rating, PEI, thickness) as printed, and
  name a shortfall.
- One recommended pick per line, with its one-line reason that names the facts: "closest
  look, same size, ships from a US warehouse". An alternate says in plain words why it is
  offered: "same slip rating, cheaper per SF, longer lead time from overseas".
- Say which price each pick rests on: "as low as" per SF, full load, before tax, for a
  row's figure; "instant quote" for a delivered figure.

## 5. Price

- `quote_products` for the options SKILL.md's pricing rule names, each at its line's
  quantity, to one ZIP, with the `project_uuid` when the person wants them in a project.
- A line still pricing: call again with the same lines (a repeat reuses the instant
  quotes), or `check_quote` for one. A refused line says why and what would fix it.

## 6. Show

- The table or document carries, per line: the reference as stated, then each option's
  name, instant quote (or the called-out as-low-as), lead time, ships from with its flag,
  minimum, reason and link.
- Then one card, as SKILL.md's "How to show several products" says.
- On the card path, when the person wants each line's full results: one `search_products`
  per reply, then one line naming the next ("Next: CT-1, guest bath walls"), searched when
  the person replies.

## A worked example (an invented line)

The line reads "WT-2, guest bath walls: 3 x 6 glossy ceramic subway, white, a named
product, 1,800 SF". The person gave ZIP 30318 and wants prices.

1. Tile. The line names a product and the chat has no photo of it, so take that product's
   direct image link from the web.
2. `find_products` with `category` tile, `photo_url` the image link, `request` "3 x 6
   glossy white ceramic subway tile for a bathroom wall", `quantity_sqft` 1800,
   `destination_zip` 30318, `detail` full. `filters` carry the stated size and finish only;
   the look comes from the photo, so nothing about color.
3. The header gives the match count, the Applied line (wall, size, finish) and the terms
   line.
4. Row 1 is the closest look and ships from a US warehouse; row 4 is cheaper per SF with
   the same finish and a longer lead time. Row 1 is the base pick, row 4 the cheaper
   alternate, each with its one-line reason.
5. `get_product` on both with `images` true.
6. `quote_products` with both at 1,800 SF to 30318. One comes back ready, one still
   pricing: call again with the same lines to collect it.
7. The table row: the reference, then both options with reason, instant quote total with
   tax, lead time, ships from with its flag, minimum and link. Then one card:
   `show_shortlist` with the group "WT-2, guest bath walls" (the base pick first), or, when
   the person wants the picks kept, `find_project` and `save_to_project` with both
   `sku_uuids`. One sentence under the card.

## Worked cases

Each maps to exactly one path.

- "This is my living room and this is my bathroom. Find tile options for both" (two
  photos): `find_products` twice, each with its photo (`photo_focus` from the person's
  words, or a `crop_box` when the tile area is clear), then `show_shortlist` with the
  groups "Living room" and "Bathroom".
- "Find matching floor and wall tiles for this bathroom" (one photo, two items):
  `find_products` twice with the same photo, `photo_focus` "the floor tile" and "the wall
  tile" (or two `crop_box` values), then `show_shortlist` with the groups "Bathroom floor"
  and "Bathroom wall".
- "I'm a designer, need tile ideas for a multifamily bathroom, with pictures in the doc"
  (a brief, no photo): the ideas are Flume's products. Make SKILL.md's photo offer once,
  for 2 or 3 reference images. On "find them", pick 2 or 3 directions with a web image
  each, `find_products` per direction (its link in `photo_url`), then `show_shortlist`
  grouped by direction, naming each image. Pictures in the document mean the HTML file of
  SKILL.md's Documents rule (a Word file cannot embed them); never a drawn picture in place
  of a Flume product.
