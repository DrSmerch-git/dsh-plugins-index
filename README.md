# dsh-plugins-index

Public plugin-market index (format 1) for the private
[DrSmerch-git/dsh-plugins](https://github.com/DrSmerch-git/dsh-plugins) repository.

DeepSeek Harness reads this file in **Plugins → Experimental plugins → Discover** and
installs a chosen plugin from the listed pinned commit. Only names, versions, descriptions
and commit hashes live here — the plugin sources stay in the private repository.

Index URL:

    https://raw.githubusercontent.com/DrSmerch-git/dsh-plugins-index/main/index.json

## Regenerating

From a checkout of `dsh-plugins`:

```bash
node tools/build-index.mjs --publish ../dsh-plugins-index
cd ../dsh-plugins-index && git add index.json && git commit -m "index" && git push
```

Do not edit `index.json` by hand: the generator validates the result with the same parser
DSH uses, and a hand-edited file can be rejected by the Discover tab.
