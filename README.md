# CHANGEME

## Project initialization steps

1. Initialize repository (typically via `git init`)
2. Install dependencies (typically via `npm install`)
3. Acknowledge pre-configured precommit git hooks, they validate changes to be committed against preconfigured _lint_ rules and expected _prettier_ style.  
   _If for some reason in context of this project you don't find it helpful, ensure to remove all `husky` and `lint-stage` related configuration._
4. Acknowledge pre-configured semi-automation of a [release process](RELEASE_PROCESS.md). For that to work as expected, project is expected to to follow [semantic commit messages](https://www.conventionalcommits.org/en/v1.0.0-beta.4/#summary).  
   See proposed [Commit Message Guidelines](https://docs.google.com/document/d/1hKUs3qt_aVp_PBI1UqvfaIqKma3jAJimEoGCRGGbOqs/edit#).  
    _If for some reason in context of this project you don't find it helpful, ensure to remove all `commitlint` and `standard-version` related configuration, and cleanup `.travis.yml`._
5. Fill all occurences of CHANGEME found in any files across a project with expected counterparts. While doing that also remove this section.
6. Commit created changes, ideally by combining them into initial commit by pursuing following steps:

- `git stash`
- `git rebase -i --root`  
  _Change here 'pick' to 'edit' on first commit_
- `git stash pop`
- `git add -A .`
- `git commit --amend '-S'`  
  _Confirm on initial commit message._  
  _(note: this one doesn't necessarily need to confirm to commitlint. To make it distinct you may use emotikon as `💥`)_.
- `git rebase --continue`
- `git push -f`

7. Ideally all further updates should go through CI validated and reviewed PR's
