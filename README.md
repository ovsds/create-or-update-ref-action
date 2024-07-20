# Create Or Update Ref Action

[![CI](https://github.com/ovsds/create-or-update-ref-action/workflows/Check%20PR/badge.svg)](https://github.com/ovsds/create-or-update-ref-action/actions?query=workflow%3A%22%22Check+PR%22%22)
[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Create%20Or%20Update%20Ref-blue.svg)](https://github.com/marketplace/actions/create-or-update-ref)

Create ref with a given SHA or update it if it already exists.

## Usage

### Example

```yaml
- name: Create or update ref
  id: create-or-update-ref
  uses: ovsds/create-or-update-ref-action@v1
  with:
    ref: tags/v1
    sha: ${{ github.sha }}
```

### Action Inputs

| Name           | Description                                                         | Default                             |
| -------------- | ------------------------------------------------------------------- | ----------------------------------- |
| `github_token` | Github token used for API calls. Required scope - 'contents: write' | ${{ github.token }}                 |
| `owner`        | Repository owner.                                                   | ${{ github.repository_owner }}      |
| `repo`         | Repository name.                                                    | ${{ github.event.repository.name }} |
| `ref`          | Target ref name.                                                    |                                     |
| `sha`          | SHA to be used for the ref.                                         |                                     |

## Development

### Global dependencies

- nvm
- node

### Taskfile commands

For all commands see [Taskfile](Taskfile.yaml) or `task --list-all`.

## License

[MIT](LICENSE)
