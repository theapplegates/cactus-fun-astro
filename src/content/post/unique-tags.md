---
title: "Unique tags validation"
publishDate: "30 January 2023"
description: "This post is used for validating if duplicate tags are removed, regardless of the string case"
tags: ["blog", "blog", "Blog", "test", "bloG", "Test", "BLOG"]
---

## This post is to test zod transform

If you open the file `src/content/post/unique-tags.md`, the tags array has a number of duplicate blog strings of various cases.

These are removed as part of the removeDupsAndLowercase function found in `src/content/config.ts`.

<img data-src="https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit,w_auto/dpr_auto/f_auto,q_auto/poz8j0ok8tega9ch3sbc.jpg" class="cld-responsive">

The image above used [Cloudinary's](https://cloudinary.com/documentation/responsive_client_side_js) javascript library. It uses javascript to learn your device's viewport size. It then sends the correct sized image to your device. Oh did I mention it sets automatic breakpoints? Well, it does.
```js title="Base.astro"
  <script type="text/javascript">
      my_breakpoints = function (width){  // width - the current width of the containing element
        return 50 * Math.ceil(width / 50);
      }
      var cl = cloudinary.Cloudinary.new({cloud_name: "paulapplegate-com"});
      // replace 'demo' with your cloud name in the line above
      cl.config({breakpoints:my_breakpoints, responsive_use_breakpoints:"resize"})
      cl.responsive();
  </script>
```
