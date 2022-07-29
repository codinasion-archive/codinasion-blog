---
title: How to find and replace text in linux
author: harshraj8843
date: 2022-02-16
hero: images/hero.png
description: SED command Syntex for find and replace text in same file sed -i 's/<old_text>/<new_text>/g' file.txt Syntex for find and replace text and save to another file sed 's/<old_text>/<new_text>/g' file.txt > newfile.txt Syntex for find and replace text containing '/' /hii => bye sed -i 's/\/hii/bye/g' file.txt /hii => /bye sed -i 's/\/hii/\/bye/g' file.txt
tags:
  - sed
  - ubuntu
contributors:
---

## SED command

- #### Syntex for find and replace text in same file

  ```bash
  sed -i 's/<old_text>/<new_text>/g' file.txt
  ```

- #### Syntex for find and replace text and save to another file

  ```bash
  sed 's/<old_text>/<new_text>/g' file.txt > newfile.txt
  ```

- #### Syntex for find and replace text containing '/'

  - **/hii => bye**

    ```bash
    sed -i 's/\/hii/bye/g' file.txt
    ```

  - **/hii => /bye**

    ```bash
    sed -i 's/\/hii/\/bye/g' file.txt
    ```

[Learn more about SED command](https://www.gnu.org/software/sed/manual/sed.html)

---
