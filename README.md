# evergreen-travis

An experimental bot for keeping the node versions in your travis CI configuration up to date with new releases.

## The problem

Node version numbers need to be specified explicitly in you travis.yml files, which means keeping up to date with new node releases can be an arduous task, especially if you have a lot of projects using travis.

## The solution

`evergreen-travis` is a bot which will open a PR in your repos when new node versions are published so you don't have to manually update all of your repositories.

## How to use

Just open a PR on the [repositories.json](./repositories.json) file in this repo adding any repositories that you want to keep up to date. Then `evergreen-travis` will look after the rest.

If you have a lot of repos, you can add `username/*` instead to have `evergreen-travis` index all of your repos.

### Notes

* `evergreen-travis` will only index original repos if you use a wildcard option. Forks of other repositories are ignored. If you have a fork that you want to be indexed then you should add it explicitly.
* If you have a large number of repositories in your account, but only a few of them need to be indexed then please don't use a wildcard.

## Feedback

`evergreen-travis` is new and highly experimental. All feedback is appreciated. Please open an issue if you have any problems, suggestions or feedback.

## Known issues

* Doesn't currently work with repos with a branch other than `master` as the default branch.

## Tech stack

`evergreen-travis` is 3 AWS lambda functions and an SQS queue. The code lives with [https://github.com/lennym](@lennym).
