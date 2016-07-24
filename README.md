# Ideal code to go inside the <head> document

This is the ideal code to go inside the <head> element, for a basic site. For larger sites where you need more options, I'd recommend diving into [Josh Bucheas' Github page](https://github.com/joshbuchea/HEAD). It has a lot more options that this, as this is only my recommended usage and provides information for what each tag does.





## Declaring character encoding
The charset attribute specifies the character encoding for the HTML document.
Character Set = Unicode Transformation Format-8. It is an octet (8-bit) lossless encoding of Unicode characters.


```html
<meta charset="utf-8">
```

- [Character encodings for beginners](https://www.w3.org/International/questions/qa-what-is-encoding)

- [Declaring character encodings in HTML](https://www.w3.org/International/questions/qa-html-encoding-declarations)



## Render the page as IE Edge
Tells IE to behave as the latest rendering engine. If none is set, IE will render the site how it thinks it is best shown. Gets rid of compatibility mode and improves overall headaches.
```html
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
- [Info here](https://stackoverflow.com/questions/6771258/what-does-meta-http-equiv-x-ua-compatible-content-ie-edge-do)


## Make site responsive
Tells the browser to set the website width in px, to the devices width. 
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```
- [Using the viewport meta tag to control layout on mobile browsers](https://developer.mozilla.org/en/docs/Mozilla/Mobile/Viewport_meta_tag)

## Title & Description
Title: Displays your title in the browser window, history, bookmarks. Shows in search engines and should reflect as your entire site and the page you're on. 

Description: This tag provides a short description of the page. In some situations, this description is used as a part of the snippet shown in the search results. Recommended usage is between 150 and 160 characters. It's also worth noting that you should make use of keywords. 

```html
<title> Document title goes here </title>
<meta name="description" content="">
```
- [Definitive guide to using important meta tags](http://www.hobo-web.co.uk/definitive-guide-to-using-important-meta-tags/)

- [Meta tags that Google understands](https://support.google.com/webmasters/answer/79812?hl=en)


## Robots Meta
>The robots meta tag lets you utilize a granular, page-specific approach to controlling how an individual page should be indexed and served to users in search results.

>After the robots.txt file (or the absence of one) has given permission to crawl a page, by default pages are treated as crawlable, indexable, archivable, and their content is approved for use in snippets that show up in the search results, unless permission is specifically denied in a robots meta tag

I'd recommend using a robots.txt file, as then you don't have to include the meta tags in every page but as Google says, if you want to deny a single page from being indexed then the robots meta tag is the way to go. Ask, Google, Bing, and Yahoo all respect the below code. 

```html
<!-- Do not show this page or Cached link search results and don't follow the links on this page -->
<meta name="robots" content="noindex, nofollow">
```
- [Robots meta tag specifications](https://developers.google.com/webmasters/control-crawl-index/docs/robots_meta_tag)

## Facebook / OpenGraph and Twitter Cards

###OpenGraph 
>Most content is shared to Facebook as a URL, so it's important that you mark up your website with Open Graph tags to take control over how your content appears on Facebook.
>Without these tags, the Facebook Crawler uses internal heuristics to make the best guess about the title, description, and preview image for your content. Designate this info explicitly with Open Graph tags to ensure the highest quality posts on Facebook.


```html
<meta property="og:url"                 content="http://www.example.com" />
<meta property="og:title"               content="Website page title" />
<meta property="og:description"         content="A brief description of the content" />
<meta property="og:site_name"           content="Example" />
<meta property="og:image"               content="http://www.example.com/image.jpg" />
<meta property="fb:app_id"              content="000000" />  <!-- Used for Domain Insights -->
<meta property="og:type"                content="website" /> <!-- website is deafult -->
<meta property="og:locale"              content="en_US" />   <!-- en_US is deafult -->
```
- [A Guide to Sharing for Webmasters - Facebook](https://developers.facebook.com/docs/sharing/webmasters)

### Twitter Cards
>With Twitter Cards, you can attach rich photos, videos and media experience to Tweets that drive traffic to your website. Simply add a few lines of HTML to your webpage, and users who Tweet links to your content will have a “Card” added to the Tweet that’s visible to all of their followers.

>When the Twitter card processor looks for tags on your page, it first checks for the Twitter property, and if not present, falls back to the supported Open Graph property.

The below meta tags are the bare minimum and there are also lots of different style cards. See their documentation for more information. 

Twitter fallbacks these tags:
- twitter:title / og:title
- twitter:description / og:description
- twitter:image / og:image

```html
<meta name="twitter:card"               content="summary">
<meta name="twitter:site"               content="@your_sites_username">

<!-- You don't need to include these if you have OpenGraph tags -->
<meta name="twitter:title"              content="Page Title">
<meta name="twitter:description"        content="Page description less than 200 characters">
<meta name="twitter:image"              content="http://www.example.com/image.jpg">

```

- [Getting started with Twitter Cards](https://dev.twitter.com/cards/getting-started)
- [Must-Have Social Meta Tags for Twitter, Google+, Facebook and More](https://moz.com/blog/meta-data-templates-123)





#Favicons


```html
<!-- For IE 10 and below -->  
<!--  No link, just place a file called favicon.ico in the root directory -->

<!-- For IE 11, Chrome, Firefox, Safari, Opera -->  
<link rel="icon" href="path/to/favicon-16.png" sizes="16x16" type="image/png">  
<link rel="icon" href="path/to/favicon-32.png" sizes="32x32" type="image/png">  
<link rel="icon" href="path/to/favicon-48.png" sizes="48x48" type="image/png">  
<link rel="icon" href="path/to/favicon-62.png" sizes="62x62" type="image/png"> 

```

- [All About Favicons (And Touch Icons)](https://bitsofco.de/all-about-favicons-and-touch-icons/)


## HTML5 Shim
HTML5 Shim is a Javascript workaround for legacy browsers that don't support HTML5 elements. The code below makes sure IE 6-8 supports these elements allowing you to use and style them in your document. 
```html
    <!--[if lt IE 9]> 
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/html5shiv/3.7.3/html5shiv.min.js"></script> 
    <![endif]-->
```
