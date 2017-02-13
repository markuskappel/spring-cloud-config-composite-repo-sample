**Spring cloud config composite repository sample**

The config server is configured to use vault and git as repository backends.
Vault must be started locally.
A git repository with a sample value is provided under https://github.com/markuskappel/config-sample.

Start vault in dev mode

`$ vault server -dev`

Export the vault url and the vault root token

`$ export VAULT_ADDR='http://127.0.0.1:8200'`

`$ export VAULT_TOKEN=<vault_root_token>`

Write a secret to vault

`$ vault write secret/foo foo=bar_vault`

Read some config

`$ curl -s http://127.0.0.1:8080/foo/default -H "X-Config-Token: <vault_root_token>`
