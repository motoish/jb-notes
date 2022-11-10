# jb-notes

[![code quality](https://github.com/mtngtnsh/jb-notes/workflows/Lint%20Code%20Base/badge.svg)](https://github.com/marketplace/actions/super-linter)

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
