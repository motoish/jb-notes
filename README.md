# jb-notes

[![main](https://github.com/motoish/jb-notes/workflows/motoish.com/badge.svg?branch=main)](https://github.com/motoish/jb-notes/actions/workflows/workflow.yml?query=branch%3Amain)
[![gh-pages](https://github.com/motoish/jb-notes/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/motoish/jb-notes/actions?query=branch%3Agh-pages)
[![Release](https://github.com/motoish/jb-notes/workflows/Release/badge.svg?branch=main)](https://github.com/motoish/jb-notes/actions?query=workflow%3ARelease+branch%3Amain)

## Introduction

Learning Jupyter, and note it by Jupyter Book Community.

## Deployment

### Before publish your book, it needs to install the tools

```sh
pip install -r requirements.txt
```

### All you need to do is

```sh
jb build --all jb-notes
cd jb-notes
git checkout main
git add .
git commit -m "{messages}"
git push
ghp-import -n -p -f _build/html
```
