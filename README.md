# Portfolio-Website
This is the code for my portfolio website, where I showcase my graphic design work and artwork. 

## Table of Contents
- [Requirements](https://github.com/cristi0404/Portfolio-Website#requirements)
- [Project Notes](https://github.com/cristi0404/Portfolio-Website#project-notes)
- [Design Notes](https://github.com/cristi0404/Portfolio-Website#design-notes)
- [Dev Notes](https://github.com/cristi0404/Portfolio-Website#dev-notes)
- [Future Updates](https://github.com/cristi0404/Portfolio-Website#future-updates)
- [Local Development](https://github.com/cristi0404/Portfolio-Website#local-development)

## Requirements

This website uses [Bootstrap 4](https://getbootstrap.com/) as the CSS framework across all pages, and [baguetteBox.js](https://github.com/feimosi/baguetteBox.js) on the gallery pages. It requires the inclusion of jquery (through CDN) to support the Bootstrap dropdown menu. It uses [Cloudflare](https://www.cloudflare.com/) as its DNS, [AWS S3](https://aws.amazon.com/s3/) for hosting, and the domain name was purchased through [Namecheap](https://www.namecheap.com/).

## Project Notes

- Most of the imagery on the website (aside from the portfolio pieces in the gallery pages) are SVGs because they scale infinitely, are small in file size, and go hand-in-hand with the flat-design visual approach. 
- I chose baguetteBox.js because its lightweight and written in pure Javascript (easy to understand/work with)
- The level of interactivity is different between desktops and touch screen devices (the latter is simplified to eliminate guesswork, especially since hover is not supported).
- This website is static/has no back-end whatsoever.
- The "graphics" folder contains the SVGs and the "images" folder contains the portfolio pieces.

## Design Notes

- The look and feel can be described as "cozy", "investigative", "nighttime", "intimate". The scenery is a cleaned-up/simplified version of my own desk, and includes hints about my personality/interests (the cactus, the world map, the earl grey tea, etc.)
- The color palette is warm and cool (complementary). The hex codes can be found at the very top of [main.css](public/css/main.css).
- The menu, headlines, and image captions are [Montserrat](https://fonts.google.com/specimen/Montserrat), the body copy is [Roboto](https://fonts.google.com/specimen/Roboto).
- All of the imagery is based on flat-design in order to give the site a simple and modern look.
- The SVGs are exported from the "website-finalgraphics.ai" file on my desktop.
- The sound effects are downloaded from [soundsnap](https://www.soundsnap.com/).
- The overall design is a balance of "ease of use" and "user intrigue". The inspiration comes from the psychology of motivation in video games.

## Dev Notes

- Bootstrap, google fonts, jquery, and baguetteBox.js are loaded through CDN
- The bootsrap navbar dropdown is customized to toggle on hover instead of on click for all pages (except for index since it doesn't have a dropdown)

### Layout

- The navbar setup is the same across all pages except for the landing page (index.html). The landing page doesn't include the dropdown, and on large and extra large hover screens, it is set to "writing-mode: vertical-lr". The navbar is flex-column on xs to medium screens, and flex-row on large and extra large screens (regardless of hover). 

- The rows on most of the pages have a min-height in order to visually center the contents and have them fit the whole page

- The landing and home page have similar row layouts and positioning for the window and lamp to match up. The main difference is landing is set to justify-content-start instead of center for large/xl screens (this only changes the left/right positioning), and align-items-start on xs-medium screens (to avoid the mismatch of vertically centering the window across different devices)

- The mobile/touchscreen version of the landing page is a combination of the index and home page.

- The SVGs on most of the pages are positioned relatively using negative margins in order to place them where I want them to go while maintining their relationships to each other as the screen size changes (the only exception is contact page where the SVGs are organized in their regular order, left to right)

- The only part of the website that follows the conventional bootstrap layout with rows and columns are the gallery pages

- Sizing for breakpoints below 576px and above 1200px rely on vw and vh

- Most text on the website is positioned absolutely within its containing SVG


### SVGs

- Non-interactive SVGs are embedded as images, while interactive SVGs are inline (with the exception of the window on the home page) in order to manipulate its contents with css/js (e.g. the lamp on landing, the computer/ipad/canvas, the iphone, and the file). 

- The width must be set for SVGs to display. No manipulation of the viewbox was done on any of them.


### CSS Organization

- All pages have their own css stylesheets in addition to the main one in order to customize the background color, navbar styling, container and row width/height.
- The graphic design page has its own stylsheet in addition to main.css and gallery.css in order to customize the caption formatting
- The main css file is organized as follows: 
  - color palette
  - global body, link, audio, and hr styles
  - global navbar styling
  - HTML pages in order of navigation (landing, home, gallery pages, about, contact) with individual media queries at the end of each page section



## Future Updates

- Copyright the website

### Gallery Pages

- When I have more work to showcase, group them into "categories". Each category should link to its own page. For example,

  - Graphic design categories: "illustrations", "infographics", "PROJECT NAME", etc
  - Digital art categories: each category is the name of a series
  - Art categories: "3D", "Gouache", "Graphite", "SERIES NAME"

- The main graphic design/digital art/art pages will only have the hover functionality with the titles of each category showing on the thumbnails - only the individual category pages will have a lightbox gallery
- Each cateogry page will have its own detailed description at the top

### Graphics

- Improve on the graphics as I get better at flat-design illustration


## Local Development

1. Get the http-server installed on you Mac by running (if brew is not install it, install it)
```bash
brew install http-server
```
2. Start the server (you need to be in root of the project):
```bash
http-server -p 8080 -a 0.0.0.0 -c-1
```

3. Read the output of server start, it will tell you where to go :)

Go here for more on usage of [http-server](https://www.npmjs.com/package/http-server)
