# Flume

Flume helps US real estate developers, general contractors and subcontractors source tile,
flooring and stone for their projects, from suppliers in the US and overseas, such as Europe.
Designers and architects use it in the design phase to pick the right material for the
project's budget.

In Claude, search Flume's ceramic and porcelain floor and wall tile and vinyl flooring in your
own words, with a photo, a pasted product link or a product name: tile that looks like a
photo, the floor and wall in a room photo, alternatives to a product you have. Flume finds
matching products, narrowed by where they go, size, finish and other specs, each with an
as-low-as price per square foot. Compare several products in one shortlist, open a product for
its specs and where it can go, get an instant quote for delivery to a ZIP code in the
contiguous US, and save products and instant quotes to a Flume project. For a spec list,
finish schedule, takeoff or bid package, Flume matches each line to products and gets instant
quotes for your picks.

For natural and engineered stone, hardwood and other flooring, trims, or other kinds of tile,
ask in the chat: Flume's sales team sources them and follows up by email.

Flume delivers to projects in the US only. Full orders start at 1,000 sq. ft. of tile from a
US warehouse and 10,000 sq. ft. of vinyl flooring, and each product states its own minimum.
Orders are placed through Flume's sales team; samples on Flume's self-serve app or through
the team. You need a Flume account.

## What the plugin adds

- **The `flume-search` skill.** How Claude works with Flume: when to search, how to use a
  photo, a product link or a product name, how to show several products, how instant quotes
  and pricing requests work, and how to price a spec list, a VE report or a bid package.
  Claude reads it when a request is about sourcing or pricing tile or vinyl flooring, or when
  you pick it from the `/` menu.
- **Flume's connector** at `https://mcp.tryflume.ai/claude/mcp`: Flume's tools, and Flume's
  cards in the chat.

## How to use it

1. Add the plugin, open its **Connectors** tab and connect Flume. Sign in with your Flume
   account, free to create at https://app.tryflume.ai. On Team and Enterprise plans, an
   Owner adds the connector for the organization.
2. Skills need **Code execution and file creation** turned on in Claude's settings.
3. Ask in your own words. For example:
   - Using Flume, find 24" × 24" porcelain tile like this photo for a living room floor.
   - Using Flume, get an instant quote for the third option, 5,500 sq. ft. to 94103.
   - Using Flume, price this finish schedule for our bid.

In Claude Code:

```text
/plugin marketplace add flumeconstruction/flume-plugins
/plugin install flume@flume-plugins
```

## What it sends, and where

- The plugin runs no code and stores nothing. The skill is text that Claude reads.
- When Claude uses Flume's tools, the details of your request go to Flume's server at
  `mcp.tryflume.ai`, under your Flume account: what you are looking for, photos you add in
  Flume's card, image and product links, quantities, delivery ZIP codes, when the material is
  needed, project names, and messages you send to Flume's sales team.
- To find a reference image of a look or a product, the skill may ask Claude to use its own
  web search. Nothing else goes to any other service.
- Privacy policy: https://tryflume.ai/privacy-policy
- Terms of service: https://tryflume.ai/terms-of-service

## Support

Write to support@tryflume.ai, or visit https://tryflume.ai/support.
