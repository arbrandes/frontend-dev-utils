# frontend-dev-utils

This package includes development utilities for use with [`frontend-base`](https://github.com/openedx/frontend-base/).

## Tools

* [`autoinstall`](./tools/autoinstall/): Tool to watch for/install packed `frontend-base` `.tgz` files when running an app's developement server.
* [`serveconfig`](./tools/serveconfig/): Tool to serve `.json` files for testing `frontend-base`'s runtime config functionality.

## Releases

This package is published to npm by `semantic-release`, and its branches follow [OEP-10 ADR 0002: Frontend Stable Branches](https://docs.openedx.org/projects/openedx-proposals/en/latest/processes/oep-0010/decisions/0002-frontend-stable-branches.html):

* **`main`** is unstable.  Every merge publishes a prerelease on the `alpha` dist-tag.  Breaking changes land here with no DEPR process and no warning, so it is not supported in production.  All changes, including bug fixes, should target this branch first.
* **`stable`** carries the newest stable major and owns the `latest` dist-tag.  Changes arrive here as backports from `main`, and no breaking change lands after publication.
* **`n.x`** and **`n.m.x`** are maintenance branches for majors and minors that `stable` has moved past.  Each publishes under its own dist-tag, so consumers can pin a maintained line by semver range, for example `"1.x"`.

Both `.releaserc` and the `Release CI` workflow already know the whole layout, including the maintenance branch patterns, so a new line starts publishing as soon as it is pushed.

This repository is not branched or tagged for Open edX releases in its own right.  It participates by published version instead, per [OEP-10 ADR 0003: Frontend Release Strategy](https://docs.openedx.org/projects/openedx-proposals/en/latest/processes/oep-0010/decisions/0003-frontend-release-strategy.html).
