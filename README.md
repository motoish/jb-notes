# jb-notes

[![MegaLinter](https://github.com/mtngtnsh/jb-notes/workflows/hangyuz.net/badge.svg?branch=main)](https://github.com/mtngtnsh/jb-notes/actions?query=workflow%3Ahangyuz.net+branch%3Amain)

## Introduction

Learning Jupyter, and note it by Jupyter Book Community.

## Deployment

### Before publish your book, it needs to install the tools

```pip
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
