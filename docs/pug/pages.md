#Pages

Pug pages are the bread and butter of your site. These pages will be compiled into the html files that represent your site. The default pages (index.pug, starter.pug, and style-guide.pug) extend the default site template and pass in extra content via `block main`.

##Adding in Content

To add content and component markup to your page, there is a main block that is setup by default on each of the default pages (index.pug, starter.pug, and style-guide.pug) within Mimogear. This content will be nested directly into the main element of your site as dictated within the default site template.

```pug
block main
  p Any pug code can be nested here
```

##Extending a Template

Each page extends the default template.pug template as the first command within a pug page. Make sure this is included on your page!

**Base Level**

```pug
extends ../template.pug
```

In the case of adding a subfolder within /src/pug/pages/, make sure to correct the path the extend function looks for.

**Within 1 Subfolder**

```pug
extends ../../template.pug
```

##Changing the Theme

In some cases there are special treatments that are particular only to a certain type of page. For example, the index.pug page adds a class of mimo-theme to the body element which is used as a hook for the mimo-theme.css styles. The theme variable will allow you to change a theme specific class on the html element.

```pug
block theme
  - pageTheme = "homepage"
```

##Changing the Page's Title and Description

Much like changing the theme per page, there are two variables that also control the page title and page description. Changing these values will override the default title and description managed through package.json.

```pug
block title
  - var title = "A different title"

block description
  - var description = "A different description"
```

##Adding Additional Stylesheets

To add additional stylesheets onto your page, there is an optional block called `additional-stylesheets` at the end of the head region.

```pug
block additional-stylesheets
  link(
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/additional-stylesheet.css"
  )
```

##Adding Additional Scripts

To add additional scripts onto your page, there is an optional block called block `additional-scripts` at the end of the footer region.

```pug
block additional-scripts
  script(src="https://cdnjs.cloudflare.com/ajax/libs/additional-script.js")
```
