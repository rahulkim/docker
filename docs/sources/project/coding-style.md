page_title: Coding Style Checklist
page_description: List of guidelines for coding Docker contributions
page_keywords: change, commit, squash, request, pull request, test, unit test, integration tests, Go, gofmt, LGTM

# Coding Style Checklist

This checklist summarizes the material you experienced working through [make a code contribution](/project/make-a-contribution) and [advanced contributing](/project/advanced-contributing).  The checklist applies to code that is program code or code that is documentation code.

## Change and commit code

* Fork the `docker/docker` repository.

* Make changes on your fork in a feature branch. Name your branch `XXXX-something` where `XXXX` is the issue number you are working on.

* Run `gofmt -s -w file.go` on each changed file before
committing your changes. Most editors have plug-ins that do this automatically.

* Update the documentation when creating or modifying features. 

* Commits that fix or close an issue should reference them in the commit message
`Closes #XXXX` or `Fixes #XXXX`. Mentions help by automatically closing the
issue on a merge.

* After every commit, run the test suite and ensure it is passing.

* Sync and rebase frequently as you code to keep up with `docker` master.

* Set your `git` signature and make sure you sign each commit.

* Do not add yourself to the `AUTHORS` file. This file is autogenerated from the Git history.

## Tests and testing

* Submit unit tests for your changes. 

* Make use of the builtin Go test framework built. 

* Use existing Docker test files (`name_test.go`) for inspiration. 

* Run <a href="../test-and-docs" target="_blank">the full test suite</a> on your branch before submitting a pull request.

* Run `make docs` to build the documentation and then check it locally.

* Use an <a href="http://www.hemingwayapp.com" target="_blank">online grammar
checker</a> or similar to test you documentation changes for clarity, concision,
and correctness.

## Pull requests

* Sync and cleanly rebase on top of Docker's `master` without multiple branches
mixed into the PR.

* Before the pull request, squash your commits into logical units of work using `git rebase -i` and `git push -f`. 

* Include documentation changes in the same commit so that a revert would remove all traces of the feature or fix.

* Reference each issue in your pull request description (`#XXXX`)

## Respond to pull requests reviews 

* Docker maintainers use LGTM (**l**ooks-**g**ood-**t**o-**m**e) in PR comments to indicate acceptance.

* Code review comments may be added to your pull request. Discuss, then make the
suggested modifications and push additional commits to your feature branch. 

* Incorporate changes on your feature branch and push to your fork. This automatically updates your open pull request.

* Post a comment after pushing to alert reviewers to PR changes; pushing a change does not send notifications.

* A change requires LGTMs from an absolute majority maintainers of an affected component. For example, if you change `docs/` and `registry/` code, an absolute majority of the `docs/` and the `registry/` maintainers must approve your PR.

## Merges after pull requests

* After a merge, [a master build](https://master.dockerproject.com/) is available almost immediately. 

* If you made a documentation change, you can see it at [docs.master.dockerproject.com](http://docs.master.dockerproject.com/). 