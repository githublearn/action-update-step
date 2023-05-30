# Action: Update Step

Action step: Update the course repository when the learner completes a step.

_This is not a course._ Visit https://github.com/skills to view our courses.

### Example use

```yml
name: Step 0, Welcome
on: push
permissions:
  contents: write
jobs:
  on_start:
    name: On start
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
        with:
          fetch-depth: 0 # Let's get all the branches.
      - name: Update to step 1
        uses: skills/action-update-step@v2
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          from_step: 0
          to_step: 1
          branch_name: my-first-branch
          base_branch_name: my-base-branch # Optional
```

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
