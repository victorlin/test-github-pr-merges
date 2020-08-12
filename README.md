# test-github-pr-merges

Goal: merge a GitHub Pull Request with fast-forward option (no diverging merge commit)

## merge options

1. merge commits
2. squash merge
3. rebase merge

As of the time of writing this (see [`git blame`](https://github.com/victorlin/test-github-pr-merges/blame/master/README.md)), this is the branch graph after testing all 3 options:

```
$ git log origin --oneline --all --branches --graph
* 10efa10 (HEAD -> master, origin/master, origin/HEAD) Update README.md
*   edfd561 Merge pull request #3 from victorlin/merge-commits
|\  
| * 634d1a7 (origin/merge-commits) Create test-merge-commits
|/  
* 3907c5b Create test-rebase-merge
| * a3e8040 (origin/rebase-merge) Create test-rebase-merge
|/  
* c32ad68 Create test-squash-merge (#1)
| * 126c12d (origin/squash-merge) Create test-squash-merge
|/  
* cdb743e Update README.md
* 29f7646 Initial commit
```

Looks like there will always be divergent commits no matter what. :/

## resources

- https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-merges
- https://git-scm.com/docs/git-merge#_fast_forward_merge
- https://stackoverflow.com/questions/46570752/why-is-fast-forward-merge-relevant-in-github-rebase-merge-workflow
- https://stackoverflow.com/questions/51222428/git-pull-request-dev-into-master-without-a-new-commit
- https://stackoverflow.com/questions/55800253/how-can-i-do-a-fast-forward-merge-using-the-github-api
