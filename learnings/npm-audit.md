# npm disable audit in .npmrc

npm can get noisy during installs with the [audit](https://docs.npmjs.com/cli/v6/commands/npm-audit) report:

```bash
1 vulnerabilities (0 moderate, 1 high)

To address issues that do not require attention, run:
  npm audit fix

To address all issues (including breaking changes), run:
  npm audit fix --force
```

[Dan Abramov](https://twitter.com/dan_abramov) has a great write-up on why [npm audit is broken by design](https://overreacted.io/npm-audit-broken-by-design/) - it is worth the read.

You can disable the audit for all npm commands using `.npmrc`:

```ini
audit=false
loglevel=silent
```
