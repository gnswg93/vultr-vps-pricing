# Buy Cheap VPS: Is Vultr's $2.50 Plan Real, What Does the $300 Credit Cover, and Which Instance Should You Order? (Entry Prices, Region Rules, and the Add-Ons That Raise the Bill)

Vultr's cheapest instance with a normal IPv4 address is **$3.50/month**, and it comes with 512 MB of RAM. The $2.50 number that shows up in comparison tables is a real listing, but it is the IPv6-only build and it is sold in a couple of locations. The $300 credit is a separate offer entirely: a promotional balance for new accounts, not a discount applied to whichever plan you pick.

This page covers the entry configurations worth looking at, the region and IPv4 rules that decide what you can actually order, what Vultr publishes about the $300 code and what it leaves out, and the add-ons that push a $3.50 server toward $10.

> **Quick pick:** a test box, a bot, a cron job, a small API or a single low-traffic site belongs on the 512 MB Cloud Compute instance at **$3.50/month**. A WordPress install with MySQL and a control panel does not: 512 MB is not enough once the database and PHP are running, so budget for the 1–2 GB tier instead.
>
> 👉 [Check the current price of the 512 MB Cloud Compute instance](https://www.vultr.com/pricing/?ref=9738262-9J)

## The entry points, and what each one is for

Vultr's price list is long. A tracker that reads both the pricing page and the public plans API counted more than 120 configurations spread across 36 regions. Most of that is noise when your budget is under $10, so the table below is trimmed to the lines a cheap-VPS buyer would realistically order.

| Plan family | Smallest configuration | Monthly price | Use it for | Order |
| --- | --- | --- | --- | --- |
| Cloud Compute, Regular | 512 MB RAM, shared vCPU, IPv4 included | **$3.50** | bots, cron jobs, test boxes, tiny APIs | [ Order the $3.50 plan](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud Compute, Regular (IPv6-only) | 512 MB RAM, no IPv4 address | **$2.50** | short-lived jobs that never need IPv4 | [ Order the $2.50 IPv6-only plan](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud Compute, 1 GB / 2 GB tiers | 1–2 GB RAM | listed on the pricing page | one small site, a small database | [ See 1–2 GB pricing](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J) |
| High Frequency / High Performance | NVMe storage, faster-clocked CPUs | listed on the pricing page | WordPress, latency-sensitive apps | [ See the high-frequency tiers](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J) |
| Optimized Cloud Compute | dedicated vCPU, split into General Purpose, Memory, Compute and Storage variants | entry tier recorded at $28 | production apps, databases with steady load | [ See Optimized Cloud Compute](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Bare Metal | an entire physical server | entry tier recorded at $120 | heavy or nested workloads | [ See Bare Metal](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Cloud GPU | GPU instances | entry tier recorded at $90 | inference tests, model experiments | [ See Cloud GPU](https://www.vultr.com/pricing/?ref=9738262-9J) |

Two notes on that table. The Optimized Cloud Compute, Bare Metal and Cloud GPU entry figures are the ones G2 records on its Vultr pricing page; treat them as approximate and read the real number off Vultr's pricing page before you commit. And the 1–2 GB and high-frequency rows carry no figure here because the entry tiers I could verify stop at 512 MB. Guessing them would be worse than sending you to the page.

## The $2.50 headline hides two things

**It has no IPv4 address.** The $2.50 instance is IPv6-only. If your ISP, your office network or your monitoring provider is IPv4-only, you can't reach it, and a lot of tooling still assumes an A record. The $3.50 version is the same 512 MB box with an address you can point a domain at.

**Both entry tiers sit in two locations.** The price list carries them in New Jersey, with the IPv6-only variant also available in Atlanta. If your users are in Frankfurt, Tokyo or Sydney, the cheapest thing you can actually buy in that region is a larger plan.

| Region | What changes |
| --- | --- |
| New Jersey | Full list, including the $2.50 and $3.50 tiers |
| Atlanta | Carries the IPv6-only entry tier |
| The other regions on Vultr's list | Larger plans only, same list price as New Jersey |
| São Paulo | Priced at 1.5× the list price |

That São Paulo multiplier is worth flagging before you plan a Latin American deployment around a $3.50 budget. The same configuration costs half again as much there.

👉 [Check which configurations are live in your region](https://www.vultr.com/pricing/?ref=9738262-9J)

## What the $300 credit actually gets you

Vultr's coupon page lists four codes at once:

- **FLY300VULTR**: $300 of free credit
- **250VULTRFLY**: $250 of free credit
- **FLYTWOHUNDRED**: $200 of free credit
- **VULTRMATCH**: dollar-for-dollar match on your first deposit, up to $100

Every one of them carries the same footnote: *promotional credit applies to select products only, cannot be combined with any other offers, restrictions and terms apply, new customers only.*

That is the entire published disclosure, and it tells you more than the banner does. The codes don't stack, so the decision is a single choice rather than a pile-on: $300 in credit or a $100 deposit match, not both. And "new customers only" means an account that has already been billed is out.

What the footnote doesn't say matters just as much. It doesn't publish an expiry window, doesn't list which products count as "select", and doesn't say whether a card is required. Third-party signup guides describe the balance as running for 30 days after you attach a payment method and apply the code in Billing → Promo Codes, but that isn't on Vultr's own page, so verify the expiry in your billing dashboard the day you apply it rather than the week before you need it.

Spending the credit well is the part most people get wrong. A $300 balance covers more than 80 months of the $3.50 box, which wastes the offer. Use the window to run the tier you'd actually buy: stand up the 4 GB or 8 GB instance you're considering for production, put your real workload on it, measure, then size the plan you pay for from those numbers. The credit is also the cheapest way to test latency from several regions before you pick one.

👉 [Open Vultr's coupon page and apply FLY300VULTR before your first deploy](https://www.vultr.com/coupons?ref=9738262-9J)

## The real monthly bill: what sits on top of the headline price

A $3.50 server is not always a $3.50 bill. These are the line items to check before you compare Vultr against anything else.

**IPv4.** The entry-level difference is exactly this: $2.50 without an address, $3.50 with one. One dollar a month is trivial on its own. It stops being trivial when you're running a dozen instances.

**Backups.** Vultr's backup pricing shows up as a complaint in G2 reviews, where a few reviewers say backups feel expensive relative to the instance. Automatic backups are not baked into the entry price of a cheap cloud plan in general, so decide up front whether you're paying for Vultr's snapshot service or scripting your own dumps to object storage.

**Everything else that attaches to an unmanaged box.** Across budget VPS plans generally, the recurring extras are control-panel licences (cPanel, Plesk and DirectAdmin are billed separately from the server on most providers), additional IPv4 addresses, migration help, managed support, and paid security tooling such as malware scanning or DDoS add-ons. Budget the total, not the sticker.

**Renewal pricing.** This is where the cheap-VPS category usually bites: Hostinger's $4.99 is a first-24-months rate, GoDaddy's $8.99 runs for the first three years, and Hostwinds' $4.99 applies to the first billing cycle only. None of those providers publishes what the bill looks like afterwards. Vultr's Cloud Compute list prices don't behave that way; the tracker reading them daily had recorded no change between early October and mid-November 2026. You're comparing a list price against other companies' teaser prices, so adjust accordingly.

## Which size fits which job

The thresholds below are industry rule-of-thumb figures, not Vultr's recommendations, but they map well onto a cheap-VPS decision.

- **512 MB, 1 vCPU**: throwaway compute, a monitoring agent, a scheduled scraper, a tiny JSON API, a WireGuard endpoint. It runs a static site comfortably. It does not run WordPress with a database.
- **1–2 GB**: one small WordPress site, a lightweight Node or Django app, a small Postgres instance. 2 GB is the usual floor once a database and a web server share the box.
- **4 GB and up**: multiple sites, WooCommerce, a CI runner, anything doing real builds or holding a working dataset. As a rough capacity guide, a 1–2 GB single-core box handles 5–10 lightweight sites, 4–8 GB with 2–4 cores handles 20–50, and beyond that you're into multi-core territory with caching doing the heavy lifting.

Most readers never need the top of Vultr's list. An 8 GB or 16 GB instance purchased "to be safe" is idle RAM you're renting by the month, and moving up later is a plan change, not a migration project.

## How the price compares with other cheap VPS options

| Provider | Published entry price | Billing caveat |
| --- | --- | --- |
| Netcup | €3.35/mo (2 vCore, 2 GB RAM, 64 GB SSD) | list price |
| Hetzner Cloud | €4.35/mo | list price, NVMe + AMD EPYC |
| DigitalOcean | $4/mo | no refunds |
| OVHcloud | ~$5/mo | list price, unlimited traffic up to 500 Mbps |
| Hostwinds | $4.99/mo | first billing cycle only, 3-day refund window |
| Hostinger | $4.99/mo | first 24 months |
| GoDaddy | $8.99/mo | first three years |
| IONOS | $2–$90/mo range | entry tier is entry-spec |

Three of those rows are intro-term prices with no published renewal figure, which makes a straight comparison against Vultr's list price misleading in Vultr's favour or against it depending on which row you read. The other thing the table can't show: none of these prices include backups or a control-panel licence either, so the floor is the floor everywhere.

Vultr's own argument is footprint. It lists more data-centre locations than most of the providers above, which matters if latency to a specific city is your binding constraint rather than price. The trade-off is thinner documentation and a support operation built for people who already know their way around a broken kernel, which is worth knowing before you buy.

## Who shouldn't buy this

Skip Vultr's unmanaged tiers if any of these describe you:

- You want to click through a WordPress installer and never open a terminal.
- You need cPanel or Plesk included. The licence is an extra line on the bill, and you'll still be the one administering it.
- You need a support ticket to fix your application stack. Support on an unmanaged instance covers the infrastructure, not your config.
- You're running something critical and have nobody who can debug it at 2 a.m.

In those cases the honest answer is a managed plan that costs more per month and less per incident. That's a budget decision, not a technical one.

## The final rules

Match the plan to the job and stop there:

- A disposable job that never touches IPv4, running in New Jersey or Atlanta → **the $2.50 IPv6-only instance**.
- Anything you'll SSH into from a home or office connection → **the $3.50 instance with IPv4**. The extra dollar buys reachability.
- One small site with a database → **the 1–2 GB tier**, not 512 MB.
- Multiple sites, a CI runner, or a database that matters → **4 GB and up, or Optimized Cloud Compute** for a dedicated vCPU.

Three things to confirm before you pay: that your region actually carries the plan you picked, that you applied one promo code (they don't stack) on a genuinely new account, and that you've seen the credit's expiry date in the billing dashboard rather than assuming it.

👉 [Start on the $3.50 Cloud Compute instance and resize once you have real numbers](https://bit.ly/VuLtr)
