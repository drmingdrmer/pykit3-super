pk3 is the super repo for pykit3 sub module repos

This is just a container and does nothing.

# Ready to use modules

- k3num 


# Add new module

Basic dir layout such as `.travis.yml` and source code and test folder is prepared in template repo:
https://github.com/pykit3/tmpl

Use this repo to create a new module repo:

# Development

- `travis` is used for CI, such as https://travis-ci.com/pykit3/k3num .
- Testing is based on native python `unittest`.
- Document is generated by `sphinx`.
  Python docstring follows [google docstring style](https://www.sphinx-doc.org/en/1.5/ext/example_google.html).
  Documenting building stuffs are all in `docs/` dir.
- Github meta data such as description and settings are managed with `.github/settings`. see https://github.com/pykit3/gh-config for detail.
- Module publishing utils is in this module.
- A module repo needs a `__name__ = "k3num"` and `__version__ = "0.1.2"` in its top level `__init__.py` so that building script generates the module name automatically
  A `version` must be in semantic version syntax.
- Publish a release: `make release`. It invokes makefile in a embedded repo
    `_building`  in every repo. `make release` builds a `setup.py` and commit it
    and then push a tag of `'v' + __version__`.
    A github Action will publish the package to pypi.
