# mulanshan Surge Rules

Personal Surge rule sets for AI services, special sites, and small routing patches.

This repository is intended to complement mature community rule projects such as:

- blackmatrix7/ios_rule_script
- SukkaW/Surge

The rule files here do not include policies. Choose the policy in your Surge profile when referencing them with `RULE-SET`.

## Usage

Replace `mulanshan/surge-rules` with your own GitHub repository path after publishing.

```ini
[Rule]

# Personal overrides should be placed before broad China / Google / Microsoft / GitHub rules.
RULE-SET,https://raw.githubusercontent.com/mulanshan/surge-rules/main/rules/douban.list,Proxy,extended-matching,no-resolve
RULE-SET,https://raw.githubusercontent.com/mulanshan/surge-rules/main/rules/ai.list,Ai,extended-matching,no-resolve
```

## Files

- `rules/ai.list`: Combined AI services.
- `rules/douban.list`: Douban web, mobile web, app API, and image/static resources.
- `examples/rule-section.conf`: Example `[Rule]` section.

## Notes

Put specific personal rules before broad community rules. For example, `douban.list` should be placed before China direct rules if you want Douban to use a proxy policy.

For domain-heavy rule sets, use `extended-matching` on the `RULE-SET` line so Surge can also match SNI and HTTP Host / `:authority`.
