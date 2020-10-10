# Stack

repo: <https://github.com/commercialhaskell/stack>

## Upgrade stack version

follow: <https://docs.haskellstack.org/en/stable/install_and_upgrade/>

do: `curl -sSL https://get.haskellstack.org/ | sh`

## Clear .stack directory

see: <https://github.com/commercialhaskell/stack/issues/133>

`rm -rf ~/.stack`

## Upgrade LTS version

find the latest LTS release version: <https://www.stackage.org/>

latest releases, LTS Haskell

edit the project `stack.yaml` file, replacing `resolver: xxx`
with the latest version

optionally, edit the project `package.yaml` file and, removing
any hardcoded version, e.g.

```yaml
-- replace
-- checkers == 0.5.2
-- with
checkers >= 0.5.2
```

run `stack install` and `stack test` to verify; if I get an
error like this:

```text
checkers-0.5.6 from stack configuration does not match ==0.5.2  (latest matching version is 0.5.2)
```

go back to the previous step and fix the dependencies
