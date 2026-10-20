# Create Or Update Ref Action

[![CI](https://github.com/ovsds/create-or-update-ref-action/workflows/Check%20PR/badge.svg)](https://github.com/ovsds/create-or-update-ref-action/actions?query=workflow%3A%22%22Check+PR%22%22)
[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Create%20Or%20Update%20Ref-blue.svg)](https://github.com/marketplace/actions/create-or-update-ref)

Create ref with a given SHA or update it if it already exists.

## Usage

### Example

```yaml
jobs:
  create-or-update-ref:
    permissions:
      contents: write

    steps:
      - name: Create Or Update Ref
        id: create-or-update-ref
        uses: ovsds/create-or-update-ref-action@v1
        with:
          ref: tags/v1
          sha: ${{ github.sha }}
```

### Action Inputs

```yaml
inputs:
  github_token:
    description: |
      Github token used for API calls. Required scope - 'contents: write'
    default: ${{ github.token }}

  owner:
    description: |
      Owner of the repository
    default: ${{ github.repository_owner }}

  repo:
    description: |
      Repository name
    default: ${{ github.event.repository.name }}

  ref:
    description: |
      Ref name
    required: true

  sha:
    description: |
      Ref SHA
    required: true

  force:
    description: |
      Delete and create ref if it already exists instead of updating it
    default: "false"
```

## Development

### Global dependencies

- [mise](https://mise.jdx.dev/installing-mise.html), activated in the shell (`eval "$(mise activate zsh)"`)

All other tools are pinned in [mise.toml](mise.toml).

### mise tasks

For all commands see [mise.toml](mise.toml) or `mise tasks ls`.

## License

[MIT](LICENSE)
