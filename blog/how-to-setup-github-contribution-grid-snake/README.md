---
title: How to Setup Github Contribution Grid Snake
author: harshraj8843
date: 2022-02-23
hero: images/hero.png
description: This post will help you in setting up github contribution grid snake aka snake game for your README.md like this... Github Contribution Grid Snake Lets Begin... Step 1 - Create New Repo If you want to continue with an existing repo, continue with step 2 Step 2 - Add Github Action Add this github action in your repo at path .github/workflows/snake-update.yml Step 3 - Run Workflow Run github action workflow manually for first time use. Step 4 - Use it in README.md At this point your github-contribution-grid-snake.gif is available at https://raw.githubusercontent.com/<your_username>/<repo_name>/output/github-contribution-grid-snake.gif Now copy-paste this in your README.md Don't forget to change <your_username> and <repo_name> with your own github username and reponame Done Congratulations !!! You have completed this setup
tags:
  - github
contributors:
---

This post will help you in setting up **github contribution grid snake** aka **snake game** for your `README.md` like this...

![Github Contribution Grid Snake](https://raw.githubusercontent.com/harshraj8843/harshraj8843/output/github-contribution-grid-snake.gif)

**Lets Begin...**

## Step 1 - _Create New Repo_

If you want to continue with an existing repo, continue with **step 2**

![new repo](./images/1.png)

![new repo](./images/2.png)

## Step 2 - _Add Github Action_

Add this github action in your repo at path **_.github/workflows/snake-update.yml_**

```yml
name: Generate snake game gif
on:
  # this workflow can be triggered manually
  workflow_dispatch:
  # this workflow will run on every saturday at 23:50
  schedule:
    - cron: "50 23 * * 6"

jobs:
  generate-snake-game:
    runs-on: ubuntu-latest
    timeout-minutes: 10

    steps:
      # generates a snake game from a github user contributions graph, output a gif animation at <gif_out_path>
      - name: generate github-contribution-grid-snake.gif
        uses: Platane/snk@master
        with:
          github_user_name: ${{ github.repository_owner }}
          gif_out_path: dist/github-contribution-grid-snake.gif

      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.gif to the output branch
        uses: crazy-max/ghaction-github-pages@v2.5.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          # It will be given by GitHub automatically
          # https://docs.github.com/en/actions/security-guides/automatic-token-authentication
```

## Step 3 - _Run Workflow_

Run github action workflow manually for first time use.

![run action](./images/3.png)

![run action](./images/4.png)

## Step 4 - _Use it in README.md_

At this point your **github-contribution-grid-snake.gif** is available at

```md
https://raw.githubusercontent.com/<your_username>/<repo_name>/output/github-contribution-grid-snake.gif
```

Now copy-paste this in your `README.md`

```md
![Snake game](https://raw.githubusercontent.com/<your_username>/<repo_name>/output/github-contribution-grid-snake.gif)
```

**_Don't forget to change <your_username> and <repo_name> with your own github username and reponame_**

## Done

**Congratulations !!!**

You have completed this setup :)

---
