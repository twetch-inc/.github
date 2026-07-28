# .github

Organization-wide defaults for [@twetch-inc](https://github.com/twetch-inc).

Nothing here is a product. It's the boilerplate GitHub reads to render our
public face and to fill in the files individual repositories don't define
themselves.

## What's in here

| Path | What it does |
| --- | --- |
| `profile/README.md` | Renders on [github.com/twetch-inc](https://github.com/twetch-inc). This is the page people land on. |
| `SECURITY.md` | Default security policy and reporting process. |
| `SUPPORT.md` | Where to go for help — app users vs. developers. |
| `CONTRIBUTING.md` | Default contribution guide. |
| `CODE_OF_CONDUCT.md` | Applies to these repositories, not to the Twetch network. |
| `.github/ISSUE_TEMPLATE/` | Default issue forms and the "new issue" chooser links. |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default pull request template. |

## How the defaults work

A repository that defines its own copy of one of these files uses its own. Only
the gaps fall through to here — so a repo with a genuinely different
contribution process should just write its own `CONTRIBUTING.md` rather than
trying to make this one cover both cases.

Changes land on `main` and take effect immediately. There's no build step and
nothing to deploy.

## Editing the profile

`profile/README.md` is a public marketing surface, not internal documentation.
Three things to keep in mind:

- **`twetch-rs` is linked but still private.** Signed-out visitors get a 404 on that link until the repo is made public. This is deliberate — the profile is written for the state we're heading to, not the state we're in.
- **Only link routes that exist.** `twetch.com` is a single-page app, so a made-up path still returns HTTP 200. The real list is in [sitemap.xml](https://twetch.com/sitemap.xml); check there before adding a link.
- **Images must be publicly reachable.** The banner is served from `twetch.com`, which is why it renders. An image referenced from a private repo shows up broken for everyone who isn't signed in.

## Don't archive this repo

Archiving makes it read-only, which means the profile can't be updated. It's the
one repository in the org that should stay active.
