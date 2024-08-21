# GitHub CLI

## Ref

[CLI](https://cli.github.com/manual/gh)

## Usage 1: Get remote branch list

```sh
 gh api -H "Accept: application/vnd.github.v3+json" repos/{owner}/{repo}/branches --jq ".[].name" --paginate
```

Or, you can also set alias.

```sh
gh alias set branch 'api -H "Accept: application/vnd.github.v3+json" repos/{owner}/{repo}/branches --jq ".[].name" --paginate'

gh branch
```

## Usage 2: Get GitHub Actions workflow

```sh
gh api -H 'Accept: application/vnd.github.v3+json' /repos/{owner}/{repo}/actions/workflows
```

And erase the history..

```sh
gh api -H 'Accept: application/vnd.github.v3+json' /repos/{owner}/{repo}/actions/workflows | jq '.workflows[].id'

export REPOSITORY={workflow_id}

gh run list --workflow "${WORKFLOW}" --limit 50 --json databaseId,status \\n --jq '.[] | select(.status == "completed") | .databaseId' \\n | xargs -n 1 -I {} gh api -X DELETE repos/${REPOSITORY}/actions/runs/{}
```

::: {tip}
👆 It should be press `q` for every 50-times, if you wanted to delete 50 running records.
:::

```sh
gh workflow view
gh workflow list
```

or

```sh
gh workflow view --yaml
gh workflow list -a
```

## Usage 3: Other

```sh
gh run view
```
