---
layout: post
title: "Gitbook Setup"
date: 2020-04-25
categories: ['code', 'deployment', 'devops', 'git']
---

This post will serve more as a reminder of steps followed to create a [gitbook website](https://dlstadther.github.io/cheatsheets) hosted by Github Pages, a repo/site for quick language/framework references.
The process here is not original and was strongly based off[@novalagung's](https://devops.novalagung.com/en/cicd-serverless-ebook-gitbook-github-pages-actions-calibre.html)

## Steps

### Install npm
> Assumes use of macOS.

```shell
$ brew install node npm
```

### Install `gitbook` cli
```shell
$ npm install -g gitbook-cli
/usr/local/bin/gitbook -> /usr/local/lib/node_modules/gitbook-cli/bin/gitbook.js
+ gitbook-cli@2.3.2
added 578 packages from 672 contributors in 12.158s
```

### Create new gitbook project
```shell
$ cd ~/code
$ gitbook init cheatsheets
Installing GitBook 3.2.3
gitbook@3.2.3 ../../../var/folders/kc/k1w6tvz529g7m_snq0jhqx9w0000gn/T/tmp-9832eeh5jUM1OScG/node_modules/gitbook
├── escape-html@1.0.3
├── escape-string-regexp@1.0.5
├── destroy@1.0.4
├── ignore@3.1.2
├── bash-color@0.0.4
├── gitbook-plugin-livereload@0.0.1
├── cp@0.2.0
├── nunjucks-do@1.0.0
├── graceful-fs@4.1.4
├── github-slugid@1.0.1
├── direction@0.1.5
├── q@1.4.1
├── spawn-cmd@0.0.2
├── gitbook-plugin-fontsettings@2.0.0
├── open@0.0.5
├── is@3.3.0
├── object-path@0.9.2
├── extend@3.0.2
├── json-schema-defaults@0.1.1
├── gitbook-plugin-search@2.2.1
├── jsonschema@1.1.0
├── crc@3.4.0
├── urijs@1.18.0
├── semver@5.1.0
├── immutable@3.8.2
├── front-matter@2.3.0
├── dom-serializer@0.1.0 (domelementtype@1.1.3, entities@1.1.2)
├── omit-keys@0.1.0 (array-difference@0.0.1, isobject@0.2.0)
├── error@7.0.2 (xtend@4.0.2, string-template@0.2.1)
├── tmp@0.0.28 (os-tmpdir@1.0.2)
├── npmi@2.0.1 (semver@4.3.6)
├── send@0.13.2 (range-parser@1.0.3, fresh@0.3.0, statuses@1.2.1, etag@1.7.0, ms@0.7.1, depd@1.1.2, mime@1.3.4, debug@2.2.0, http-errors@1.3.1, on-finished@2.3.0)
├── mkdirp@0.5.1 (minimist@0.0.8)
├── resolve@1.1.7
├── rmdir@1.2.0 (node.flow@1.2.3)
├── fresh-require@1.0.3 (is-require@0.0.1, shallow-copy@0.0.1, sleuth@0.1.1, astw@1.3.0, through2@0.6.5, escodegen@1.14.1, acorn@0.9.0)
├── gitbook-plugin-theme-default@1.0.7
├── js-yaml@3.13.1 (esprima@4.0.1, argparse@1.0.10)
├── tiny-lr@0.2.1 (parseurl@1.3.3, livereload-js@2.4.0, qs@5.1.0, debug@2.2.0, body-parser@1.14.2, faye-websocket@0.10.0)
├── cpr@1.1.1 (rimraf@2.4.5)
├── gitbook-plugin-lunr@1.2.0 (html-entities@1.2.0, lunr@0.5.12)
├── read-installed@4.0.3 (debuglog@1.0.1, util-extend@1.0.3, slide@1.1.6, readdir-scoped-modules@1.1.0, read-package-json@2.1.1)
├── gitbook-plugin-highlight@2.0.2 (highlight.js@9.2.0)
├── moment@2.13.0
├── gitbook-plugin-sharing@1.0.2 (lodash@3.10.1)
├── i18n-t@1.0.1 (lodash@4.17.15)
├── gitbook-markdown@1.3.2 (kramed-text-renderer@0.2.1, gitbook-html@1.3.3, kramed@0.5.6, lodash@4.17.15)
├── cheerio@0.20.0 (entities@1.1.2, css-select@1.2.0, htmlparser2@3.8.3, jsdom@7.2.2, lodash@4.17.15)
├── gitbook-asciidoc@1.2.2 (gitbook-html@1.3.3, asciidoctor.js@1.5.5-1, lodash@4.17.15)
├── chokidar@1.5.0 (async-each@1.0.3, path-is-absolute@1.0.1, inherits@2.0.4, glob-parent@2.0.0, is-binary-path@1.0.1, is-glob@2.0.1, anymatch@1.3.2, readdirp@2.2.1)
├── nunjucks@2.5.2 (asap@2.0.6, yargs@3.32.0, chokidar@1.7.0)
├── request@2.72.0 (tunnel-agent@0.4.3, aws-sign2@0.6.0, forever-agent@0.6.1, oauth-sign@0.8.2, is-typedarray@1.0.0, caseless@0.11.0, stringstream@0.0.6, aws4@1.9.1, isstream@0.1.2, json-stringify-safe@5.0.1, tough-cookie@2.2.2, node-uuid@1.4.8, qs@6.1.2, combined-stream@1.0.8, mime-types@2.1.26, bl@1.1.2, hawk@3.1.3, har-validator@2.0.6, http-signature@1.1.1, form-data@1.0.1)
├── juice@2.0.0 (deep-extend@0.4.2, slick@1.12.2, batch@0.5.3, cssom@0.3.1, commander@2.9.0, cross-spawn-async@2.2.5, web-resource-inliner@2.0.0)
└── npm@3.9.2
warn: no summary file in this book
info: create README.md
info: create SUMMARY.md
info: initialization is finished

$ cd cheatsheets
```

### Test fresh `gitbook` project
```shell
$ gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 7 plugins are installed
info: loading plugin "livereload"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 1 pages
info: found 0 asset files
info: >> generation finished with success in 0.4s !

Starting server ...
Serving book on http://localhost:4000
```

### Initialize as git repo
```shell
$ git init
Initialized empty Git repository in /Users/dstadther/code/cheatsheets/.git/

$ git remote add origin git@github.com:dlstadther/cheatsheets.git
```

### Make deploy keys and secrets
```shell
$ ssh-keygen -t rsa -b 4096 -C "$(git config user.email)" -f gh-pages -N ""
Generating public/private rsa key pair.
Your identification has been saved in gh-pages.
Your public key has been saved in gh-pages.pub.
The key fingerprint is:
SHA256:yljiBUUmFqvv2Mr+U6yVg5EoU6W2ih8MmmVi7H2AWkI dlstadther@gmail.com
The keys randomart image is:
+---[RSA 4096]----+
|   .=o+          |
|  .o =           |
| Eo.o.           |
|=.ooo.           |
|+**..+o.S        |
|*@.oo**.         |
|*.o.+=o.         |
| o =+            |
| .*o+.           |
+----[SHA256]-----+
```

### Create github deployment workflow
```shell
cat <<EOF >> .github/workflows/deploy.yml
# file ./cheatsheets/.github/workflows/deploy.yml

name: 'deploy website and ebooks'

on:
  push:
    branches:
      - master

env:
  ebook_name: 'cheatsheets'

jobs:
  job_deploy_website:
    name: 'deploy website'
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: actions/setup-node@v1
      with:
        node-version: '10.x'
    - name: 'Installing gitbook cli'
      run: npm install -g gitbook-cli
    - name: 'Generating distributable files'
      run: |
        gitbook install
        gitbook build
    - uses: peaceiris/actions-gh-pages@v2.5.0
      env:
        ACTIONS_DEPLOY_KEY: ${{ secrets.ACTIONS_DEPLOY_KEY }}
        PUBLISH_BRANCH: gh-pages
        PUBLISH_DIR: ./_book
  job_deploy_ebooks:
    name: 'deploy ebooks'
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: actions/setup-node@v1
      with:
        node-version: '10.x'
    - name: 'Installing gitbook cli'
      run: npm install -g gitbook-cli
    - name: 'Installing calibre'
      run: |
        sudo -v
        wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sudo sh /dev/stdin
    - name: 'Preparing for ebooks generations'
      run: |
        gitbook install
        mkdir _book
    - name: 'Generating ebook in pdf'
      run: gitbook pdf ./ ./_book/${{ env.ebook_name }}.pdf
    - name: 'Generating ebook in epub'
      run: gitbook epub ./ ./_book/${{ env.ebook_name }}.epub
    - name: 'Generating ebook in mobi'
      run: gitbook mobi ./ ./_book/${{ env.ebook_name }}.mobi
    - uses: peaceiris/actions-gh-pages@v2.5.0
      env:
        ACTIONS_DEPLOY_KEY: ${{ secrets.ACTIONS_DEPLOY_KEY }}
        PUBLISH_BRANCH: ebooks
        PUBLISH_DIR: ./_book
EOF
```

### Push repo to github
```shell
# ignore certain directory
touch .gitignore
cat <<EOF >> .gitignore
_book
gh-pages
gh-pages.pub
EOF

# init git repo
$ git add .gitignore .github/ README.md SUMMARY.md
$ git commit -m "Add gitbook start ci/cd"
[master (root-commit) c4ea777] Add gitbook start ci/cd
 4 files changed, 40 insertions(+)
 create mode 100644 .github/workflows/deploy.yml
 create mode 100644 .gitignore
 create mode 100644 README.md
 create mode 100644 SUMMARY.md

# push
$ git push origin master
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (8/8), 888 bytes | 888.00 KiB/s, done.
Total 8 (delta 0), reused 0 (delta 0)
To github.com:dlstadther/cheatsheets.git
 * [new branch]      master -> master
```

### Github repo config
Enable repo's Github Pages for `gh-pages` branch.
Navigate to [https://dlstadther.github.io/cheatsheets](https://dlstadther.github.io/cheatsheets)
