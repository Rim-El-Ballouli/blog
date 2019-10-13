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

### How to specify the thumbnail picture on linkedin when linking to a jekyll site?

<p class="note"> The proposed solution is not specific neither for linkedin nor for a jekyll based website.
The solution is infact generic and applicable to any site that displays hyperlinks in a preview format such as Facebook. 
Jekyll and linkedin were intentionally added to the title to help any beginner searching for the solution 
thinking  that its specific for linkedin and jekyll (thats me a month ago &#128517;).</p> 

Hyperlinks on Linkedin are displayed in a **preview**  format as a combination of three things a thumbnail picture, 
title and brief description as shown below:

<img src="/blog/assets/images/linkpreview.png" width="500">

Say your posting a link to your blog post/webpage, if the thumbnail, title and description are not directly specified, 
linkedin (or other sites) will automatically extract this information from the hyperlink and display them in the preview mode. 

This may cause an issue especially if the image does not confirm to the size of a thumbnail, causing it to be cropped.
In order to be in control of what is displayed you must have read/write access to the website you are linking. 
If you don't then there is not much you can do.

Assuming that you have read/write access, then you can control what is displayed by adding only three **\<meta>** tags 
to the \<head> tag of your blog post/webpage. Each **\<meta>** tag will specify one of the fields to be displayed in 
the hyperlink preview i.e. image, title, description. The meta tag with property: 

* **og:image** - sets the URL for the thumbnail image 
* **og:title** - sets the title of the page
* **og:description** - sets the description of the page


```html
<head> 
...
<meta property="og:image" content="/assets/images/thumbnail.png"/>
<meta property="og:title" content="Why you should visit Belgium?"/>
<meta property="og:description" content="Great food, friendly people awesome word press .."/>
</head>
```

 If you are using Jekyll SEO plugin, as suggested in the previous [post](https://rim-el-ballouli.github.io/blog/jekyll/2019/08/10/seo.html), 
 then these meta tags and others are automatically added to each page of your website according the front matter defined. 
 Therefore, you don't have to go under the trouble of defining each. However you still have to define the meta tag for the image thumbnail.  