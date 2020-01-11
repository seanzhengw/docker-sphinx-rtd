seanzhengw/sphinx-rtd docker images repository
---

[Docker Hub repository](https://hub.docker.com/r/seanzhengw/sphinx-rtd)

Sphinx image with sphinx_rtd_theme

# Using Image

## Use for locally

run sphinx make html at current directory

    $ docker run seanzhengw/sphinx-rtd:latest

## Use for GitLab-CI

assume make variable `BUILDDIR=build`, example `.gitlab-ci.yml` for sphinx make html, and upload artifacts named `mydoc`.

    image:
    name: seanzhengw/sphinx-rtd:latest
    entrypoint: [""]

    stages:
    - build

    html:
    stage: build
    script:
        - make html
        - mv build/html mysphinx-doc
    artifacts:
        name: "mydoc"
        paths:
        - mysphinx-doc
        expire_in: 1 month
