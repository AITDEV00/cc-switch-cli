# CC Switch CLI jya0-5.11.1

ADEO fork of upstream v5.11.1 for the gateway client-distribution installer.
Binaries are consumed through the ADEO LiteLLM mirror; the built-in self-update
flow is not used

## Added

- `provider add --overwrite` (requires `--id`): a true upsert. When the id
  already exists the provider is updated in place through the same write path as
  interactive edit (created_at preserved); when the id is absent it is added
  normally. Without the flag, duplicate rejection is unchanged

## Changed

- `cc-switch --version` reports `jya0-5.11.1` so installers can pin the fork
  build; Cargo.toml stays at upstream `5.11.1`
- Release workflow accepts `jya0-*` tags, skips minisign signing when the
  signing secret is absent, derives `latest.json` download URLs from
  `GITHUB_REPOSITORY`, and always publishes `checksums.txt`
