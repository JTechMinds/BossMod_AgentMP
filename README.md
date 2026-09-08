# BossMod Agent Marketplace

Catalog of `bossmod.agent_pack/v1` agent packs for BossModAI.

Packs hydrate hire fields (specialty, description, what-done-looks-like).
They do **not** include an agent name. Import always pins a commit SHA or tag.

## Layout

```text
catalog.yaml
packs/
  engineering/
    code-auditor.agent.yaml
    impl-engineer.agent.yaml
  product/
    feature-planner.agent.yaml
```

- Folder = category slug (not a display name)
- File = stable pack id (`*.agent.yaml`)
- `catalog.yaml` is the index the app reads first
- Category in the index must match the folder path

## Contributing

Open a PR that adds `packs/<category>/<id>.agent.yaml` and a matching row in
`catalog.yaml`. Schema must be `bossmod.agent_pack/v1` with `kind: agent`.
YAML is data only — no shell, hooks, or credentials.

See BossModAI `docs/AGENT_PACKS.md` for import/export and trust rules.
