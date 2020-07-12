# Git Workflow
TBD.

## Branch Strategy
TBD.

## Commit
TBD.

## Pull/Merge Request
TBD.

## Code Review and Approval
### Intro
Code review is a process when someone's code is reviewed by the others, usually by their team members and tech leads. The goals of code review are:
- To improve code quality (e.g. by aligning code style and pointing out possible bugs)
- To find better solutions for logic implementation inside the codebase
- To increase sense of code ownership between team members, especially when each member is not working together on the same feature.
### Workflow
1. When creating a Pull Request (PR), add a description containing at least:
  - Purpose of PR (e.g. to implement a new feature, to fix a bug). You can also add screenshots or tables to help explain the PR.
  - Reference to tickets related to PR (Trello card, GitHub Issues etc.).
2. Mention at least one team member and one other engineer outside the project (usually tech lead).
3. Resolve comment threads after you push changes to address those comments.
4. PR can only be merged when it has been approved by at least one team member and one engineer outside the project (usually tech lead).
5. After PR has been merged to target branch (usually `development`), delete the temporary branch.  This step is unnecessary if you are merging branch `development` to `master`, because branch `development` reperesents software state in staging environment, and will be used for future PRs. There is a setting to protect those two branches from being deleted, even though you can't do it on private GitHub repos using free plan.

## Deployment
TBD.
