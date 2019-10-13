---
layout: default
title: Setting the thumbnail picture for hyperlinks on linkedin
description: adding your jekyll website to google's search index
author: Rim El Ballouli
social:
  links:
    - https://www.linkedin.com/in/rim-el-ballouli/
    - https://github.com/Rim-El-Ballouli/
    - https://www.researchgate.net/profile/Rim_El_Ballouli2/
    - https://scholar.google.com/citations?hl=en&user=ifD1gh0AAAAJ
lang: en_US
categories: Jekyll
---

### How to set the thumbnail picture on linkedin when linking to a jekyll site?

On linkedin there are two ways to add hyperlinks:

* either to the profile page's sections including the about, experience, education sections etc.
* or to a catered post  

Hyperlinks on Linkedin are displayed in a **preview** format as a combination of three things a thumbnail picture, 
title and website URL. Below are two sample images showing hyperlinks in two different preview modes on linkedin.

<img src="/blog/assets/images/profilepreview.png" width="350" style="float:left;margin-right:10px;margin-top:25px">

<img src="/blog/assets/images/postpreview.png" width="150" style>

If the thumbnail, title and URL are not directly set, linkedin (and other sites that preview hyperlinks) will automatically 
extract this information from the hyperlink and display them in the preview mode. 

This may cause an issue especially if the image does not confirm to the ideal size of a thumbnail, causing it to be scaled 
and cropped to fit a box of 552 pixels wide by 289 pixels tall (an aspect ratio of 1.91:1). 
This problem is visible in the above right image.

LinkedIn recommends using a 1.91:1 aspect ratio. Hence, an image of 1,200 pixels wide and 628 pixels tall will work great for sharing 
links with an image to LinkedIn.

In order to be in control of what is displayed in preview format, you must have read/write access to the website you are linking. 
If you don't then there is not much you can do.

Assuming that you have read/write access, then you can solve this issue in two steps.

### Step 1
Create a thumbnail image confirming to the ideal aspect ratio of linkedin which is 1.91:1. (e.g.  552px * 289px)

### Step 2
Add metadata that sets the title and thumbnail. Add two **\<meta>** tags 
to the \<head> tag of the webpage you are linking. Each **\<meta>** tag will set one of the fields to be displayed in 
the hyperlink preview i.e. image, and title. The URL can be automatically extracted from the hyperlink, there is no need to set it.
The meta tag with property: 

* **og:image** - sets the URL for the thumbnail image 
* **og:title** - sets the title of the page

Below is a sample html code defining the above metadata.

```html
<head> 
...
<meta property="og:image" content="/assets/images/thumbnail.png"/>
<meta property="og:title" content="Webpage and blog"/>
</head>
```
If you are using Jekyll SEO plugin, as suggested in the previous [post](https://rim-el-ballouli.github.io/blog/jekyll/2019/08/10/seo.html), 
 then these meta tags and others are automatically added to each page of your website according the front matter defined. 
 Therefore, you don't have to go under the trouble of defining each. **However you still have to define the meta tag for the image thumbnail.** 
 
 <p class="note"> The proposed solution is not specific for linkedin. The solution is infact generic and applicable 
 to any site that displays hyperlinks in a preview format such as Facebook.</p> 
 