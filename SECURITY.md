# Security Policy

Twetch holds keys and moves real Bitcoin. We take reports seriously and we'd
much rather hear from you than read about it later.

## Reporting a vulnerability

**Use GitHub private vulnerability reporting** — on any of our repositories, go
to the **Security** tab and click **Report a vulnerability**. It's private
between you and us, it threads properly, and it doesn't sit in a public issue
while we fix it.

If that isn't available to you, DM [**@twetchapp**](https://x.com/twetchapp) on
X and we'll open a private channel. Don't put the details in a public post.

Please include:

- what the issue is, and the impact you think it has
- the steps to reproduce it
- anything you need from us to demonstrate it

We'll acknowledge within 3 business days and keep you posted as we work through
it. If you'd like credit once a fix ships, say so and we'll include you.

**Please don't open a public issue for a security problem**, and please don't
post it on Twetch.

## Please don't

While testing, don't do things that hurt other people:

- don't access, modify or exfiltrate another user's data, posts, chat or funds
- don't run denial-of-service, spam or load tests against production
- don't social-engineer our team or our users
- don't hold data you stumbled across — tell us and delete it

Stay within your own accounts and test data and we have no problem with you.

## Especially interested in

- anything that lets one account act as another (signing, session, or auth bypass)
- anything that exposes or weakens key material, seeds, or chat encryption
- anything that can move, lock, or claim funds or NFTs that aren't yours
- transaction construction or covenant flaws that let a listing or sale settle incorrectly
- server-side authorization gaps on owner-gated data

## Not vulnerabilities

- missing security headers or best-practice scanner output with no demonstrated impact
- anything requiring a compromised device, a malicious browser extension, or the user's seed phrase
- rate limiting on unauthenticated read endpoints — reads are meant to be open
- content that is public on chain by design being publicly readable

## A note on seed phrases

**Nobody at Twetch will ever ask for your seed phrase.** Not support, not an
admin, not anyone in a DM. Your seed is generated in your browser and never
reaches our servers, which means we cannot recover it for you and we cannot be
tricked into handing your account to someone else. Anyone asking for it is
stealing from you.
