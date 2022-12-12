# Workflows

Also know as github actions. Stores in `.github/workflows` and they
can be used to do all sorts. They start up a VM and then provision
things and then do actions:

## Creating an issue


```yaml
name: VAT Issue Creator
on:
  schedule:
    - cron: 1 8 1 3,6,9,12 *

jobs:
  create_issue:
    name: VAT Check
    runs-on: ubuntu-latest
    permissions:
      issues: write
    steps:
      - name: Create vat issue 
        uses: imjohnbo/issue-bot@3daae12aa54d38685d7ff8459fc8a2aee8cea98b
        with:
          assignees: "artumi-richard"
          labels: "accounts"
          title: "VAT"
          body: |
            # VAT
            If the month is Mar, Jun, Sep or Dec we need to do VAT accounts
          pinned: false
          close-previous: true
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

`close-previous` seems to do something based on substring matching. So
it probably makes sense to have a long title if you have this turned
on.  The close-previous doesn't happen at exactly the same time as the
opening. 


TODO - is there a way to set a project for this? And project field
values?


