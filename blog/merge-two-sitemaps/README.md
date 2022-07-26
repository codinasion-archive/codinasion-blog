---
title: How to merge two sitemaps
author: harshraj8843
date: 2022-02-09
hero: images/hero.png
description: An XML sitemap is a file that lists a website’s important pages, making sure Google can find and crawl them all. It also helps search engines understand your website structure. You want Google to crawl every essential page of your website. But sometimes, pages end up without any internal links pointing to them, making them hard to find. A sitemap can help speed up content discovery.
tags:
  - sitemap
contributors:
  - harshraj8843
---

## What is sitemap.xml ?

An [XML sitemap](https://developers.google.com/search/docs/advanced/sitemaps/overview) is a file that lists a website’s important pages, making sure Google can find and crawl them all. It also helps search engines understand your website structure. You want Google to crawl every essential page of your website. But sometimes, pages end up without any internal links pointing to them, making them hard to find. A sitemap can help speed up content discovery.

Here is a example of **sitemap.xml**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" xmlns:news="http://www.google.com/schemas/sitemap-news/0.9" xmlns:xhtml="http://www.w3.org/1999/xhtml" xmlns:mobile="http://www.google.com/schemas/sitemap-mobile/1.0" xmlns:image="http://www.google.com/schemas/sitemap-image/1.1" xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
<url> <loc>https://codinasion.web.app/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/pages/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/todo-app-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/tic-tac-toe-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/devweb-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/django-setup-in-windows-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/how-to-install-python-in-windows</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/django-setup-in-ubuntu-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/authors/harshraj8843</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
</urlset>
```

## How to merge two different sitemaps ?

- #### sitemap1.xml

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" xmlns:news="http://www.google.com/schemas/sitemap-news/0.9" xmlns:xhtml="http://www.w3.org/1999/xhtml" xmlns:mobile="http://www.google.com/schemas/sitemap-mobile/1.0" xmlns:image="http://www.google.com/schemas/sitemap-image/1.1" xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
  <url> <loc>https://codinasion.web.app/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/pages/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/todo-app-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/tic-tac-toe-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/devweb-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  </urlset>
  ```

- #### sitemap2.xml

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" xmlns:news="http://www.google.com/schemas/sitemap-news/0.9" xmlns:xhtml="http://www.w3.org/1999/xhtml" xmlns:mobile="http://www.google.com/schemas/sitemap-mobile/1.0" xmlns:image="http://www.google.com/schemas/sitemap-image/1.1" xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
  <url> <loc>https://codinasion.web.app/blog/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/blog/django-setup-in-windows-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/blog/how-to-install-python-in-windows</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/blog/django-setup-in-ubuntu-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  <url> <loc>https://codinasion.web.app/blog/authors/harshraj8843</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
  </urlset>
  ```

- #### script

  ```bash
  sed '$ d' sitemap1.xml > try1.xml
  sed '1d;2d;$ d' sitemap2.xml > try2.xml
  cat try1.xml try2.xml > sitemap.xml
  echo '</urlset>' >> sitemap.xml
  rm try1.xml
  rm try2.xml
  ```

  Run this script in terminal

#### Final output => **_sitemap.xml_**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" xmlns:news="http://www.google.com/schemas/sitemap-news/0.9" xmlns:xhtml="http://www.w3.org/1999/xhtml" xmlns:mobile="http://www.google.com/schemas/sitemap-mobile/1.0" xmlns:image="http://www.google.com/schemas/sitemap-image/1.1" xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
<url> <loc>https://codinasion.web.app/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/pages/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/todo-app-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/tic-tac-toe-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/devweb-react</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/django-setup-in-windows-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/how-to-install-python-in-windows</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/django-setup-in-ubuntu-for-begineers</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
<url> <loc>https://codinasion.web.app/blog/authors/harshraj8843</loc> <changefreq>daily</changefreq> <priority>0.7</priority> </url>
</urlset>
```

---
