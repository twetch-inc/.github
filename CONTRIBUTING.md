# Contributing

Thanks for looking. These are the defaults across Twetch repositories — if a
repo has its own `CONTRIBUTING.md`, that one wins.

## Before you write code

**Open an issue first for anything non-trivial.** A typo fix or an obvious bug
can go straight to a pull request. A new capability, a refactor, or anything
that changes a public API should start as an issue so we can agree on the shape
before you spend an evening on it.

**Check the scope.** Some of our repositories have a `SCOPE.md` that lists what
the project does and what it deliberately never will. Those omissions are
decisions with reasons attached, not gaps waiting to be filled. If your change
adds a capability that isn't on the allow list, the pull request needs to change
`SCOPE.md` first — and if you can't write the row, the capability isn't ready.

## Pull requests

- **Branch from the default branch** and keep the change focused. One concern per PR.
- **Write a real description.** What changed, why, and how you know it works.
- **Run the gates.** Whatever the repo's CI runs, run it locally first. For Rust that's:

  ```bash
  cargo fmt --all --check
  cargo clippy --workspace --all-targets -- -D warnings
  cargo test --workspace
  ```

- **Say what you skipped.** If a check couldn't run in your environment, put that in the description. We'd rather know than find out.
- **Don't reformat unrelated files.** A diff that touches 400 files because your editor reformatted them is a diff nobody can review.

## Tests

New behaviour needs a test. Bug fixes need a test that fails before the fix and
passes after — that's how we know it's actually fixed and stays fixed.

Some tests exist to pin a wire format or a signing layout byte for byte. They
look pedantic and they are load-bearing: a one-byte divergence turns into an
opaque `invalid signature` on every write. If one of those fails, the fix is
almost never to update the expected value.

## Things that will get a PR closed

- **Secrets in the diff.** Keys, tokens, kubeconfigs, seed phrases, `.env` files. If you've already pushed one, tell us immediately and rotate it — don't quietly force-push and hope.
- **Anything that puts key material somewhere new.** Seeds and identity keys stay client-side. A change that moves them, logs them, or sends them anywhere needs a conversation first.
- **Vendored copies of code we already have.** If the thing you need exists elsewhere in the workspace, depend on it rather than pasting it.
- **Bulk AI-generated changes nobody has read.** Use whatever tools you like, but you're the author and you're expected to understand every line you're proposing.

## Security

Don't open an issue or a pull request for a security vulnerability. See
[SECURITY.md](SECURITY.md).

## Commit messages

Present tense, and describe the change rather than the file:
`fix follower paging past id 65535`, not `update handlers.rs`.
