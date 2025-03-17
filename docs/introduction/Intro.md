---
sidebar_position: 1
---

# DOCUSAURAUS



##   Installation 

```bash
npx create-docusaurus@latest my-docs classic
cd my-docs
npm install
```

## Create github repo

```bash
git init
git add .
git comit -m "first comit"
git branch -M main
git remote add origin https://github.com/Shan82181/my-docs.git
git push -u origin main
```
## Changes in docusuraus.config.js
```jsx
url: 'https://github.com',

// Set the /<baseUrl>/ pathname under which your site is served

// For GitHub pages deployment, it is often '/<projectName>/'

baseUrl: '/my-docs/',

// GitHub pages deployment config.

// If you aren't using GitHub pages, you don't need these.

organizationName: 'Shan82181', // Usually your GitHub org/user name.

projectName: 'my-docs', // Usually your repo name.

deploymentBranch:'gh-pages',
```
## Deploy

```bash
cmd /C "set "GIT_USER=<Shan82181>" && yarn deploy"
```

## Create a pipeline in github 

- create a folder 
.github  
├── workflows
│ ├── deploy.yml
- after that paste the code in deploy.yml
```jsx
name: Deploy to GitHub Pages

on:

push:

branches: [main]

paths: [my-docs/**] // project name
# Review gh actions docs if you want to further define triggers, paths, etc

# https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#on

jobs:

build:

name: Build Docusaurus

runs-on: ubuntu-latest

steps:

- uses: actions/checkout@v4

with:

fetch-depth: 0

- uses: actions/setup-node@v4

with:

node-version: 18

cache: yarn

  

- name: Install dependencies

run: yarn install --frozen-lockfile

- name: Build website

run: yarn build

  

- name: Upload Build Artifact

uses: actions/upload-pages-artifact@v3

with:

path: build

  

deploy:

name: Deploy to GitHub Pages

needs: build

  

# Grant GITHUB_TOKEN the permissions required to make a Pages deployment

permissions:

pages: write  # to deploy to Pages

id-token: write  # to verify the deployment originates from an appropriate source

  

# Deploy to the github-pages environment

environment:

name: github-pages

url: ${{ steps.deployment.outputs.page_url }}

  

runs-on: ubuntu-latest

steps:

- name: Deploy to GitHub Pages

id: deployment

uses: actions/deploy-pages@v4
```

## After Changes

sync and commit all changes
```bash
cmd /C "set "GIT_USER=<Shan82181>" && yarn deploy"
```

<iframe width="560" height="315" src="https://www.youtube.com/embed/9iVNf0T09dE?si=oeARjeGddjSBu6V3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>