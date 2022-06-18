A GitHub Actions Reusable Workflow for automatically linking a Jira issue into a PR description.

<img width="922" alt="Screen Shot 2022-06-18 at 17 10 50" src="https://user-images.githubusercontent.com/2134196/174429108-1458f65c-8861-4f5f-8c9f-09eb4ac72010.png">

## Usage

Place a GitHub Actions Workflow file like `.github/workflows/pr-jira-issue-linker.yaml` with content like below:

```yaml
name: Jira Issue Linker
on:
  pull_request:
    types:
      - opened

jobs:
  jira-issue-linker:
    uses: kauche/github-actions-jira-issue-linker-workflow/.github/workflows/jira-issue-linker.yaml@v0.0.2
    with:
      jira_domain: <YOUR_JIRA_DOMAIN>
```

#### Input

-   `jira_domain`
    - Your domain for Jira like `example-domain.atlassian.net`.

---

After placing the Workflow file, create a branch with format like below:

- `<Jira Project Key>-<Jira Issue Number>-<Arbitrary String...>`

Finally, create a PR with the branch and then this Workflow will add a link to the Jira Issue into the PR description.
