pep8-staged
===========
Automatically run pep8 on staged git content before committing to your repo.

This provides a [git pre-commit hook](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) that runs
[pep8](http://pep8.readthedocs.io/en/release-1.7.x/) on staged git content.
If pep8 fails, the content will not be committed to the repo. This enables
fast turnaround for enforcing code styles within your repository.

The hook script runs on the staged content, not the current working copy. This
ensures that the true content about to committed has been vetted.


Installation
------------
If you'd like to distribute the pre-commit hook with your repository:
- Copy these files into your repository and run `install-hooks.sh` script.
- Commit them to the repository so that it will be easy to share the script
  with other contributors.

To just use the hook, copy the `git-hooks/pre-commit` file into your
repository's `.git/hooks` directory.


Customizing pep8
----------------
See the [pep8 documentation](http://pep8.readthedocs.io/en/release-1.7.x/intro.html#configuration).
The easiest way to distribute a code style for a repository is to commit a `pep8`
section to `setup.cfg` along with this hook.

Example:
```
[pep8]
max-line-length=100
exclude=migrations/*
```


See also
--------
[lint-staged](https://github.com/okonet/lint-staged)
[Running Jest Tests Before Each Git Commit](https://benmccormick.org/2017/02/26/running-jest-tests-before-each-git-commit/)
