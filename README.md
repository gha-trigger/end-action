# end-action

GitHub Actions for [gha-trigger](https://gha-trigger.github.io)

## What does this action do?

- Update the commit status according to the job status

## Example

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: gha-trigger/end-action@main
        if: always()
        with:
          github_token: ${{steps.start.outputs.github_app_token}}
          state: ${{job.status}}
```

## Inputs

### Required

- `github_token`: GitHub Access Token to update a commit status
- `state`: GitHub Actions current job status

### Optional

- `needs`: [needs context](https://docs.github.com/en/actions/learn-github-actions/contexts#needs-context)

## Environment Variables

Environment Variables must be set by [gha-trigger/set-env-action](https://github.com/gha-trigger/set-env-action).

## Outputs

Nothing.

## LICENSE

[MIT](LICENSE)
