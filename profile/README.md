## Jiru Labs

Local-first tools for people who run AI agents on their own terms.

Everything here is MIT, runs on your machine, and talks to no server of ours — no backend,
no account, no telemetry, in any of it.

---

### [mcp-config-audit](https://github.com/jiru-labs/mcp-config-audit) &nbsp;[![PyPI](https://img.shields.io/pypi/v/mcp-config-audit?color=3775A9&logo=pypi&logoColor=white&label=pypi)](https://pypi.org/project/mcp-config-audit/)

Security scanner for local MCP (Model Context Protocol) configurations — Claude Desktop,
Claude Code, Cursor, VS Code, Windsurf. It reports what the configuration file itself gives
away: credentials written into it in plain text, servers reached in the clear, launch commands
that download and run remote code or resolve a package name anyone could claim, and servers
handed a whole filesystem or an unrestricted shell.

It reads the configuration, not the servers. Read-only, no network call while scanning, and it
never logs a credential value — only that one exists, and where.

```bash
pipx install mcp-config-audit
```

> **PyPI is the only registry this project is published to.** Every release is built from a
> tagged commit in this organization and pushed over a trusted publisher; there is no release
> path that does not pass through the repo. A package of this name on any other registry is
> not ours.

### [proofkey](https://github.com/jiru-labs/proofkey) &nbsp;[![Chrome Web Store](https://img.shields.io/chrome-web-store/v/loibjoemoahkajjnfioajcibcamhdafc?color=4285F4&logo=googlechrome&logoColor=white&label=chrome%20web%20store)](https://chromewebstore.google.com/detail/loibjoemoahkajjnfioajcibcamhdafc)

A Grammarly-style writing assistant for Chrome that talks to **your** LLM, with **your** API key,
or needs no key at all: in Google Chrome it starts on the model Chrome keeps on your computer,
and in Brave it can run a model inside the browser instead. Inline underlines, a suggestion card
and quick rewrite actions — the interaction model kept, the engine swapped for one you control.
On either of those, or pointed at a local server, nothing you check leaves the machine.

**[Install from the Chrome Web Store](https://chromewebstore.google.com/detail/loibjoemoahkajjnfioajcibcamhdafc)** · [build from source](https://github.com/jiru-labs/proofkey#install-from-source)

### [epub2audiobook](https://github.com/jiru-labs/epub2audiobook)

Turns an epub into a chaptered audiobook. Gemini TTS does the narration; voice conversion against
a single reference clip then anchors the timbre, so the voice stops changing every time the model
starts a new generation. Resumable, and it shows the cost before it spends anything.

The code is the small part. **[FINDINGS.md](https://github.com/jiru-labs/epub2audiobook/blob/main/FINDINGS.md)**
is the research behind it: engine defects measured in semitones and hertz, the blind listening
rounds, and the fixes that improved the numbers while sounding worse.

---

### How this is built

- Every GitHub Action is pinned to a **commit SHA**, with Dependabot raising the bumps as
  reviewable PRs — pinned, but not frozen.
- Releases publish over **OIDC trusted publishing**. There is no long-lived registry token
  to leak.
- Secret scanning with **push protection**, private vulnerability reporting, signed commits,
  and 2FA required across the organization.

[jirulabs.com](https://jirulabs.com) · [info@jirulabs.com](mailto:info@jirulabs.com)
