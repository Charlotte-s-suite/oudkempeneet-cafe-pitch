# Going live: moving oudkempeneetcafe.nl from Squarespace to your new site

**Prepared by Merritt Digital.** This is the whole procedure, in order, in plain language.
Nothing here is urgent and nothing here is irreversible — the last section tells you exactly how
to put everything back the way it was, in about two minutes, if you ever want to.

> **Do not start yet.** Merritt will confirm in writing when your new site has passed our quality
> checks. This document is so you can read the whole plan before anything moves.

---

## What we checked on your setup (so you can trust the steps below)

We looked at your live domain before writing this, rather than assuming:

| Thing | What we found | What it means for you |
|---|---|---|
| Website host | Squarespace (`ext-sq.squarespace.com`) | This is what we are replacing. |
| **Who controls your DNS** | **Google** (`ns-cloud-e1…e4.googledomains.com`) | **Important: your DNS is _not_ managed inside Squarespace.** The change happens in your Google account, not the Squarespace panel. |
| Email on the domain | **None** — no MX records at all | **Your email cannot break.** Your `@gmail.com` address is completely separate from this domain and is untouched by everything below. |
| Anti-spam record | `v=spf1 -all` | Leave it alone. It says "no mail is sent from this domain", which is correct. |

The only records that change are the ones that say *where the website lives*. Everything else in
your DNS stays exactly as it is.

---

## Step 1 — Merritt does this first (nothing for you to do)

We attach your domain name to your new site and prepare its security certificate. **This must
happen before you change any DNS**, otherwise there is a window where someone else could claim
your address. We will tell you when it is done.

---

## Step 2 — Find where you manage your domain

Your nameservers point at Google, so one of these is true:

- **You have a Google Cloud DNS zone** (console.cloud.google.com → Network Services → Cloud DNS), or
- **Your domain came from Google Domains**, which was sold to Squarespace in 2023. If yours moved
  across in that sale, you will find it at account.squarespace.com → Domains — but note it will
  still be *using the Google nameservers above*, so you edit the records wherever those live.

If you are not sure which, send us a screenshot of the DNS page you can reach and we will point at
the right box. **Do not guess** — editing the wrong zone does nothing, which is confusing but
harmless.

## Step 3 — Change the two website records

In that DNS zone you will find records pointing at Squarespace. Replace them as follows.

**The four `A` records on the bare domain (`oudkempeneetcafe.nl`)** — replace these values:

| Remove (Squarespace) | Add (your new site) |
|---|---|
| `198.185.159.144` | `185.199.108.153` |
| `198.185.159.145` | `185.199.109.153` |
| `198.49.23.144` | `185.199.110.153` |
| `198.49.23.145` | `185.199.111.153` |

**The `CNAME` record on `www`** — change its target:

| Remove | Add |
|---|---|
| `ext-sq.squarespace.com` | `charlotte-s-suite.github.io` |

That is the entire change. Leave every other record exactly as it is.

## Step 4 — Wait, then check

DNS changes spread across the internet gradually: usually minutes, occasionally a few hours.
Then your browser padlock (the HTTPS certificate) is issued automatically, which **can take up to
24 hours** after the records are correct. During that window you may briefly see a security
warning — that is expected and it resolves itself.

Check `https://www.oudkempeneetcafe.nl` and `https://oudkempeneetcafe.nl`. Both should show the new
site with a padlock. Test on a phone as well as a computer, and try making a test reservation.

**Tell us when you see it.** We verify from our side too before you do anything in Step 5.

## Step 5 — Only now, deal with Squarespace

Do not cancel anything before Step 4 checks out. When it does:

1. **Export your old content first**, as an archive: Squarespace → Settings → Import/Export →
   Export. Keep the file. You are unlikely to need it, but it costs nothing to have.
2. **Save copies of your photos** from the old site if they are not already with us.
3. **Then, and only then, cancel the Squarespace subscription.**

> ### One trap to avoid
> If your domain was included **free with your Squarespace plan**, cancelling the plan can put the
> domain itself at risk. Before you cancel, check whether you are paying for the domain separately.
> If it is bundled, tell us — we will sort out moving the registration somewhere safe *before* the
> subscription ends. Losing the domain is the only genuinely serious mistake available here, and
> this is how you avoid it.

---

## Putting it back (if you ever want to)

Restore these values in the same DNS zone and your Squarespace site returns exactly as it was,
usually within minutes. Keep this section — it is your safety net.

- Bare domain `A` records: `198.185.159.144`, `198.185.159.145`, `198.49.23.144`, `198.49.23.145`
- `www` `CNAME`: `ext-sq.squarespace.com`

This works for as long as your Squarespace subscription is active, which is exactly why Step 5
comes last.

---

## Questions worth asking us

- *Will my Google reviews / Google Maps listing change?* No. Those are attached to your business
  listing, not your website host. Your address stays the same, so nothing there moves.
- *Will people lose my old page links?* Tell us the addresses that matter (a menu page, a
  reservations page) and we will make sure they still lead somewhere sensible.
- *Who do I call if something looks wrong?* Us, first, before changing anything back. Most of what
  looks broken in the first hour is just DNS still spreading.

_Merritt Digital · Alameda_
