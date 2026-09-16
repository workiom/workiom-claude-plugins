# Security Policy

## Reporting a vulnerability

**Please do not report security issues through public GitHub issues, pull
requests, or discussions.** A public report exposes the problem to everyone
who has installed the plugin before a fix is available.

Instead, report it privately to **support@workiom.com** with the subject line
`SECURITY: workiom-claude-plugins`.

If GitHub's [private vulnerability reporting][pvr] is enabled on this
repository, you may also use the **Report a vulnerability** button under the
Security tab.

[pvr]: https://docs.github.com/code-security/security-advisories/guidance-on-reporting-and-writing/privately-reporting-a-security-vulnerability

Please include whatever you have:

- What the issue is and roughly how severe you think it is
- Steps to reproduce, or a proof of concept
- The affected plugin and version (see `version` in the plugin's `plugin.json`)
- Any suggested fix

We will acknowledge your report, keep you updated as we investigate, and let
you know when a fix ships. We will credit you in the release notes unless you
prefer to stay anonymous.

Please give us a reasonable opportunity to fix the issue before disclosing it
publicly.

## Scope

This policy covers the contents of this repository:

- The marketplace manifest (`.claude-plugin/marketplace.json`)
- The `workiom-vibe-apps` plugin — its skill, its `.mcp.json`, and the
  `vibe-pack.py` packaging script

Because installing this marketplace causes the plugin's skill and scripts to
run on a user's own machine, we are particularly interested in reports about:

- Code in this repository that executes unexpectedly or with more privilege
  than intended
- Guidance in `SKILL.md` that could lead a generated vibe app to leak
  credentials, tenant data, or session tokens
- Anything that would let a generated page reach a tenant other than the
  viewer's own

Vulnerabilities in the **Workiom platform itself** (`workiom.com`,
`api.workiom.com`, `mcp.workiom.com`) are out of scope for this repository,
but we still want to hear about them — please use the same address above.

## Supported versions

The marketplace serves the plugin from the default branch, so security fixes
are applied to the latest released version. There is no backporting to earlier
versions; please update to the latest version before reporting an issue.
