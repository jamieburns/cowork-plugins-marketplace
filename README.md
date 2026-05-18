# cowork-plugins-marketplace

Personal Cowork plugin marketplace for plugins authored by Jamie Burns.

Lists Cowork plugins that live in their own repos. Not a public marketplace — this is the personal/internal staging ground. Individual plugins may eventually be published to Anthropic's official marketplace; their entries here remain as long as they're useful internally.

## Marketplace identifier

`jamie-cowork-plugins` (used in `/plugin install <plugin>@jamie-cowork-plugins`).

## Plugins currently listed

- **writing-cowork** — Multi-role cowork pattern for long-form writing projects. Source: [jamieburns/writing-cowork](https://github.com/jamieburns/writing-cowork).

## Install this marketplace in Cowork

```
/plugin marketplace add jamieburns/cowork-plugins-marketplace
/plugin install writing-cowork@jamie-cowork-plugins
```

## Add a new plugin to the marketplace

1. Author the plugin in its own repo (e.g., `~/code/<new-plugin>/`).
2. Push the plugin repo to a private GitHub repo under `jamieburns/`.
3. Add a new entry to `.claude-plugin/marketplace.json`:

   ```json
   {
     "name": "<plugin-name>",
     "source": {
       "source": "github",
       "repo": "jamieburns/<repo-name>"
     },
     "description": "...",
     "category": "...",
     "tags": ["..."]
   }
   ```

4. Commit and push this marketplace repo.
5. Run `/plugin marketplace update jamie-cowork-plugins` in Cowork.
6. Install with `/plugin install <plugin-name>@jamie-cowork-plugins`.
