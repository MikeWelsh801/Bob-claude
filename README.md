# Bob Ross for Claude Code

> *"We don't make mistakes — just happy little accidents."*

A Claude Code plugin that swaps Claude's voice for the calm, encouraging tone of the one and only Bob Ross. Same engineering capability, just delivered with a little more warmth and a lot less panic.

## What's inside

- **`bob-ross` output style** — Claude still reads files, writes code, runs tests, and reviews diffs the way it always does. It just narrates the work like a gentle painting instructor. Code, comments, and commit messages stay professional; the Bob Ross voice lives in the prose to you.
- **`/happy-accident` slash command** — Paste a failing test, a stack trace, or a scary-looking error. Claude will take a breath, reframe what actually happened, put it in proportion, and suggest one concrete next brushstroke. Good for the moments when CI goes red and your blood pressure goes up.

## Install

Inside a Claude Code session:

```
/plugin marketplace add MikeWelsh801/bob_ross
/plugin install bob-ross@bob-ross-plugins
```

Then activate the output style:

```
/config
```

Navigate to **Output style** → pick **Bob Ross**. Start a new session so the voice takes effect.

Or, set it directly in `.claude/settings.local.json`:

```json
{
  "outputStyle": "bob-ross"
}
```

### Running it locally without installing

If you've cloned this repo and just want to try it:

```bash
claude --plugin-dir /path/to/bob_ross
```

## What it feels like

**Before:**
> Reading the file now. The test failed due to a null reference on line 42. Adding a guard.

**After:**
> Let's take a little peek at this file and see what we're working with. Ah — happy little accident here, this value showed up to the party as `null` and the test wasn't quite expecting company. We'll add a gentle guard right there, and she'll be just fine.

## Design notes

- The output style sets `keep-coding-instructions: true`, so all of Claude Code's normal engineering guidance stays in place. Only the tone changes.
- Bob Ross metaphors are used sparingly on purpose. A happy little cloud on every line becomes parody; the goal is calm, not cosplay.
- For genuinely risky or destructive operations (data loss, security, prod), the style still tells you plainly. A soothing voice on a real fire isn't helpful.
- Short answers stay short. Bob was calm, not wordy.

## Contributing / updating

Bump `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`, push to `main`, and users run:

```
/plugin marketplace update bob-ross-plugins
```

to pull the newer version.

## License

MIT. Paint whatever you want with it.

---

*Now then — let's get started. We're gonna have a good time.*
