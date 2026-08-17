# Workiom Claude plugins

The plugin marketplace for Workiom. Adding it once makes every plugin below
installable.

```
/plugin marketplace add workiom/workiom-claude-plugins
/plugin install workiom-vibe-apps@workiom
```

Refresh later with `/plugin marketplace update workiom`.

## Plugins

| Plugin | What it does |
|---|---|
| [`workiom-vibe-apps`](plugins/workiom-vibe-apps) | Build and publish vibe apps — self-contained pages that run inside a Workiom workspace and read and write its lists |

Each bundles its skill **and** the Workiom connector it needs, so one install
wires up both.

Vibe apps are a private beta. Installing the plugin doesn't grant access —
the workspace needs the feature switched on, and until it is, the assistant
says so and stops.

## Layout

```
.claude-plugin/marketplace.json     the catalogue
plugins/<plugin-name>/
├── .claude-plugin/plugin.json      plugin manifest
├── .mcp.json                       the connector this plugin ships with
├── README.md                       written for the person installing it
└── skills/<skill-name>/
    ├── SKILL.md
    └── scripts/
```

## Adding a plugin

1. Create `plugins/<name>/` with the layout above.
2. Add an entry to `.claude-plugin/marketplace.json` — `name` and `source` are
   the only required fields.
3. Push. Users pick it up with `/plugin marketplace update workiom`.

**Names must be kebab-case** — lowercase letters, digits and hyphens only, in
`marketplace.json`, `plugin.json`, and the skill's own `name:`. Claude Code
tolerates other forms; the claude.ai marketplace sync rejects them. Use
`displayName` for anything human-readable.

Keep a plugin's directory name, its `plugin.json` `name`, and its
`marketplace.json` entry identical — `source` can point anywhere, but a
mismatch is only ever confusing.

To rename or remove a plugin later, add a `renames` map to the marketplace
manifest so existing installs migrate instead of breaking.
