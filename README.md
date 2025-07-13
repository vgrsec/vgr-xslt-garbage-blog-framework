# Welcome!

This is the dumbest blog framework possible written in an archaic xml‑based language.

Seriously. [W3](https://www.w3.org/Style/XSL/) last talked about this technology in 2017. Except we're not using XSLT 3.0, we're using [XSLT 1.0!](https://www.w3.org/TR/xslt-10/) from 1999.

Somebody sent me some cool [code](https://github.com/pacocoursey/xslt) which inspired me to learn more.

So, this probably is all fine. I mostly don't understand the inner workings because ChatGPT vibed with me for a few days... so I'm logging a bunch to console. Either way, you're welcome, and I'm sorry, for this. `vgr`

[Demo – garbageblogframework.vgrsec.com](https://garbageblogframework.vgrsec.com)  
[Code – github.com/vgrsec/vgr-xslt-garbage-blog-framework](https://github.com/vgrsec/vgr-garbage-blog-framework)

## Overview

For more info see the [FAQ](./faq.xml).

To use this framework for blogging:

- Record a blog entry in `./content/posts.xml`

  ```xml
  <item>
    <title>Last Blog Post</title>
    <description>
      I am Jack&apos;s XML Parser. I consume unclosed tags I kill jack.
    </description>
    <link>https://demo.vgrsec.com/content/posts/20250707.xml</link>
    <guid isPermaLink="false">post-20250707</guid>
    <pubDate>Mon, 7 Jul 2025 13:00:00 +0000</pubDate>
    <author>vgr.xsltgbf@example.com (vgr)</author>
  </item>
  ```

- These fields are used to populate the blog’s header. **Make sure the date matches** both the blog file name *and* the date in the file.

- Create a file in `./content/pages/YYYYMMDD.xml`.

- Insert the following code.

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <?xml-stylesheet type="text/xsl" href="../../xslt/site.xsl"?>
  <blogpost id="post-YYYYMMDD">
      <content>      
      </content>
  </blogpost>
  ```

- The `id` field associates this entry with `./content/posts.xml`; make sure it matches. You can put any HTML you want into `content` (maybe?).

> If you get XML errors wrap the offending code in [CDATA](https://www.tutorialspoint.com/xml/xml_cdata_sections.htm).

I did some testing; it seems to work. I don't use Chrome, or Android, so it *might* work?

| Engine | Chrome (Blink) | Firefox (Gecko) | Safari (WebKit) | Edge (Blink) | Android WebView | iOS Safari |
| ------ | -------------- | --------------- | --------------- | ------------ | --------------- | ---------- |
| Support | 🤷 | ✅ | ✅ | 🤷 | 🤷 | ✅ |

## Customizing

This framework comes equipped with an "easy" to use theme engine. By default it comes with:

1. Light Mode
2. Dark Mode
3. Hot Dog Stand
4. OMG Pony

Add new themes by modifying `./xslt/site.xslt`.

- You’ll find `body.dark` and other theme blocks waiting. Copy and paste a theme block, give your theme a new `body.$name`.
- Once named and set, go to `console.log("Theme Script")` and add your theme to the array of names.
- Finally add the theme button inside `<aside class="sidebar">` by copying an existing button and modifying `id="btn-$name"`, `background:#`, and `fill:#`.

Oh also I'm using a licensed font: [Input Mono](https://input.djr.com/) because frankly it’s the perfect font and I love it. It’s **not** licensed to you and probably won’t work, so you’ll have to remove it from the CSS.

## Theme Demo

Check out the premade [template](./template.xml) to see all of the different HTML tags in action with the theme. I probably covered everything in a $5 bootstrap theme. Maybe not—who cares.

### Demo Attribution

- Video: [Apollo 11 – Buzz descending the ladder and stepping onto the moon](https://commons.wikimedia.org/wiki/File:Apollo_11._Television_clip_of_Buzz_descending_the_ladder_and_stepping_onto_the_moon,_1094228.ogv)
- Audio: [Lady Gaga performs *The Star‑Spangled Banner*](https://commons.wikimedia.org/wiki/File:Lady_Gaga_performs_The_Star-Spangled_Banner_audio.ogg)

![a quiet place](../assets/pages/home/home.png)