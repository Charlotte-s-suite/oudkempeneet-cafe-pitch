# Going live: moving oudkempeneetcafe.nl to your new site

**Prepared by Merritt Digital.** This is the whole procedure, in order, in plain language.
Nothing here is urgent, your email cannot break, and the last section puts everything back exactly
as it was in one step if you ever want that.

> **Do not start yet.** Merritt will confirm in writing when your new site has passed our quality
> checks and the new hosting is ready. This document is so you can read the whole plan first.

---

## What we checked on your setup

We looked all of this up on your live domain rather than assuming it:

| Thing | What we found | What it means |
|---|---|---|
| Who you rent the domain from | **Key-Systems GmbH** (a German registrar) | This does **not** change. You keep your domain exactly where it is. |
| Who currently answers "where does this name point" | **Google** (`ns-cloud-e1…e4.googledomains.com`) | This is the part that changes. |
| Who serves the website today | **Squarespace** | This is what we are replacing. |
| Email on the domain | **None at all** — there are no mail records | **Your Gmail cannot be affected by any of this.** It is completely separate from the domain. |

Note the useful surprise: **Squarespace only hosts your website.** It does not hold your domain
name. There is no "release", no transfer, no unlock code and no waiting period to get your domain
away from them.

---

## What actually changes

One thing: **which company answers DNS questions for your domain.** Today that is Google. It
becomes Cloudflare, which is where your new site is hosted.

You might expect to edit the individual records inside Google instead. That does not work for a
bare domain like `oudkempeneetcafe.nl` (with no `www`) — the technology simply does not allow it,
and your address must work with and without the `www`. Moving the whole zone is the supported way,
and it is genuinely less work for you: **one change at your registrar instead of editing records.**

---

## Step 1 — Merritt does this first (nothing for you to do)

We create the hosting, add your domain, and **copy your existing DNS records across exactly as
they are** so nothing else about your domain changes. Your zone today is small and we have already
inventoried it, so this is quick and low risk.

We will then send you **two nameserver addresses**. They look like `something.ns.cloudflare.com`.

## Step 2 — Change the nameservers at your registrar (your part)

Log in wherever you manage the domain — Key-Systems, or whichever company you bought
`oudkempeneetcafe.nl` through, since many resellers sit on top of Key-Systems. Look for a setting
called **Nameservers**, **DNS servers**, or **NS records**.

**Replace these four:**

```
ns-cloud-e1.googledomains.com
ns-cloud-e2.googledomains.com
ns-cloud-e3.googledomains.com
ns-cloud-e4.googledomains.com
```

**with the two Cloudflare addresses we send you in Step 1.** Save. That is your entire job.

If you cannot find the setting, send us a screenshot of the control panel you can reach and we
will point at the exact box. **Do not guess** — changing the wrong field usually does nothing,
which is confusing but harmless.

## Step 3 — Wait, then check together

Nameserver changes typically take under an hour and can occasionally take longer. Then the padlock
(HTTPS certificate) is issued automatically — usually minutes, sometimes a few hours.

Check both `https://oudkempeneetcafe.nl` and `https://www.oudkempeneetcafe.nl`. Both should show
the new site with a padlock. Please also try it on your phone and send a test reservation through.

**Tell us when you see it.** We verify from our side too before you touch Step 4.

## Step 4 — Only now, cancel Squarespace

Do not cancel anything until Step 3 checks out on both addresses. When it does:

1. **Export your old content first**, as a keepsake: Squarespace → Settings → Import/Export →
   Export. You are unlikely to ever need it; it costs nothing to keep.
2. **Save copies of any photos** on the old site that we do not already have.
3. **Then cancel the Squarespace subscription.**

Because your domain is registered at Key-Systems and not at Squarespace, cancelling their
subscription **cannot** take your domain name with it. That is the one genuinely serious risk in a
move like this, and your setup does not have it.

---

## Putting it back (your safety net)

Set your nameservers at the registrar back to these four values and everything returns to exactly
how it is today, usually within the hour:

```
ns-cloud-e1.googledomains.com
ns-cloud-e2.googledomains.com
ns-cloud-e3.googledomains.com
ns-cloud-e4.googledomains.com
```

This works for as long as your Squarespace subscription is still active — which is exactly why
cancelling it is the last step and not the first.

---

## Questions people usually have

- **Will my Google listing or Maps pin change?** No. Those belong to your business listing, not
  your website host. Your address and reviews are untouched.
- **Will my email break?** No. There is no email attached to this domain — your Gmail is separate
  and nothing in this procedure touches it.
- **Will old links to my pages still work?** Tell us any addresses that matter to you (a menu page,
  a reservations link) and we will make sure they still lead somewhere sensible.
- **Something looks wrong an hour in — what do I do?** Call us before changing anything back. Most
  things that look broken early are just the change still spreading across the internet.

_Merritt Digital · Alameda_
