# rules

[agent-rules-nix](https://github.com/Hol1kgmg/agent-rules-nix) から参照する共有 agent rules の置き場。

- `rules/` 直下の `*.md` 1 ファイルが 1 ルール。ID はファイル名から `.md` を除いたもの。
- frontmatter（Claude Code の `paths:` など）はそのまま配布されるので、ここで書いた通りに利用側へ届く。

## 利用側の設定

`registry/rules/hol1kgmg.nix`:

```nix
{
  pin = {
    type = "github";
    owner = "Hol1kgmg";
    repo = "rules";
    branch = "main";
  };

  subdir = "rules";
  idPrefix = "hol1kgmg";
}
```

`rules.nix` に `"hol1kgmg/<ファイル名>"` を列挙し、`nix run .#rules-sources-lock` で rev を固定する。

## 開発

ツールは [mise](https://mise.jdx.dev/) で入れる。pre-commit で gitleaks（シークレット走査）を回す。

```bash
mise run setup
```
