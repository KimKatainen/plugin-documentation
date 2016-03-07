#Hubchat plugins documentation

Hubchat is a community platform that consists of posts, comments and replies. It comes with different kind of embeddable plugins. All plugins require a community that has been created at hubchat.com. You can create a community at hubchat.com/forum/create.

- [COMMENTS](#COMMENTS)
- [COMMUNITY](#COMMUNITY)
- [RECOMMENDATIONS](#RECOMMENDATIONS)

## COMMENTS
Comments plugin is used to embed an individual commenting thread in a page.

### Installation
The plugin is installed by adding an HTML code (below) to the source code of the website. The code is placed where the commenting thread would be liked to appear.

```html
<!-- 
  data-forum-slug: url-name of the forum (required) 
  data-embedded-id: unique id of the thread (recommended) 
  data-embedded-title: title of the thread (optional) 
  data-limit: number of comments to be shown initially (optional) 
  data-recommended-title: title for recommendations list (optional) 
  data-recommended-limit: number of recommendations to show (optional) 
  data-recommended-featured-only: use true if you want to recommend only featured topics (optional) 
  data-language: en or fi (optional) 
--> 
<div class="hubchat-comments" 
  data-forum-slug="REPLACE_THIS_WITH_YOUR_FORUM_NAME" 
  data-embedded-id="" 
  data-embedded-title="" 
  data-limit="" 
  data-recommended-title="" 
  data-recommended-limit="" 
  data-recommended-featured-only="" 
  data-language=""></div> 
<script type="text/javascript"> 
  (function () {
    var b = document.createElement("script");
    b.type = "text/javascript"; 
    b.async = true; 
    b.src = "https://www.hubchat.com/embedded/public/js/incl/plugins.js";
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(b, s);
  })(); 
</script> 
<noscript> 
  Your browser does not support JavaScript. Enable JavaScript or use a browser that supports it to use Hubchat. 
</noscript>
```

### Parameters
Configuring the code is possible by adding parameters to the JavaScript code. Parameters are added to the `<div>` element as HTML5 `data-*` attributes. 

`<div data-embedded-id=”unique-article-id”></div>`

#### data-forum-slug (required)
Data-forum-slug is a required parameter that defines the community of the commenting thread. The value of the parameter should be the name of the community. E.g. `data-forum=”example-community”`.

#### data-embedded-id (recommended)
Data-embedded-id defines a unique id for the commenting thread. This way the commenting thread is not identified based on a URL address.

The data-embedded-id value can be any string that is unique within the community. E.g. `data-embedded-id=”article-1”`.

If data-embedded-id parameter is not used in the installation code, commenting threads are automatically generated based on URL. This way, every time a page with the installation code is opened, the discussion thread that should be used on the page, is defined based on URL. This may cause problems on websites where users are able to access the same content via multiple different URLs, or the URL of the content might change in the future.

#### data-embedded-title
Data-embedded-title defines the title of the commenting thread on the forum. Without the data-embedded-title parameter the title is defined by the content of the `<title>` or `<og:title>` tags of the website. E.g. `data-embedded-title=”article title”`.

#### data-language
Data-language parameter defines the language in which the discussion thread is displayed to the user. If the parameter is not used, the language is defined automatically based on the settings of the logged in user, or the browser language of the logged out user. E.g. `data-language=”en”`

#### data-limit
Data-limit parameter defines the number of comments displayed in the commenting thread. The default number of displayed comments is ten. E.g. `data-comments=”0”` or `data-comments=”2”`.

#### data-recommended-limit
Data-recommended-title defines the number of recommendations displayed below the commenting thread. The default number of displayed recommendations is four. E.g. `data-recommended-limit=”0”` or `data-recommended-limit=”2”`.

#### data-recommended-title
Data-recommended-title defines the text shown above recommendations. By default the title is “More in community [name]” Example value: `data-recommended-title=”More discussion”`.

#### data-recommended-featured-only
Data-recommended-featured-only can be set `true` if only featured posts should be recommended.

### Community settings
Community settings are accessed at [hubchat.com/f/community-slug/edit](https://www.hubchat.com/f/community-slug/edit) or the page where the forum has been embedded. E.g. example.com/forum.

The only mandatory setting required by Comments is “allowed sites where plugins can be used” (under “Embedded”). This defines the websites where commenting threads of the community can be embedded. The setting guarantees that no one can embed commenting threads of a community on a website without authorization.

Forum settings are also used for things like defining the color scheme of plugins.

#### Comments Recommendations
Comments displays discussion recommendations below the commenting thread. These recommendations can be disabled with `data-recommended-limit=”0”` parameter.

## COMMUNITY
Community plugin is used to embed a Hubchat community in a website.

Note: Remember to set you site as allowed in the Community settings.
#### Installation
The plugin is installed by adding an HTML code (below) to the source code of the website. The code is placed where the community would be liked to appear.
```html
<!-- 
  data-forum-slug: name of the forum (required)
  data-language: en or fi (optional) 
--> 
<div class="hubchat-forum" 
  data-forum-slug="REPLACE_THIS_WITH_YOUR_FORUM_NAME" 
  data-language=""></div> 
<script type="text/javascript"> 
  (function () {
    var b = document.createElement("script");
    b.type = "text/javascript"; 
    b.async = true; 
    b.src = "https://www.hubchat.com/embedded/public/js/incl/plugins.js";
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(b, s);
  })(); 
</script> 
<noscript> 
  Your browser does not support JavaScript. Enable JavaScript or use a browser that supports it to use Hubchat. 
</noscript>
```

### Parameters
Configuring the code is possible by adding parameters to the JavaScript code. Parameters are added to the `<div>` element as HTML5 `data-*` attributes.

#### data-forum-slug (required)
The name of the embedded community. The name has to match the name of the community that has been created at Hubchat. E.g. `data-forum-slug=”Example community”`.

#### data-language
Data-language parameter defines the language in which the community is displayed to the user. If the parameter is not used, the language is defined automatically based on the settings of the logged in user, or the browser language of the logged out user. E.g. `data-language=”en”`.

## RECOMMENDATIONS
Recommendations plugin is used to promote active discussions on a website.
### Installation
The plugin is installed by adding an HTML code (below) to the source code of the website. The code is placed where the active discussions would be liked to appear.
```html
<!-- 
  data-forum-slug: list of the community names separated by comma (required) 
  data-limit: number of recommendations to show (optional) 
  data-featured-only: use true if you wan't to recommend only featured topics (optional)
  data-language: en or fi (optional) 
--> 
<div class="hubchat-recommended" 
  data-forum-slug="REPLACE_THIS_WITH_YOUR_FORUM_NAME" 
  data-limit="" 
  data-featured-only="" 
  data-language=""></div> 
<script type="text/javascript"> 
  (function () {
    var b = document.createElement("script");
    b.type = "text/javascript"; 
    b.async = true; 
    b.src = "https://www.hubchat.com/embedded/public/js/incl/plugins.js";
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(b, s);
  })(); 
</script> 
<noscript> 
  Your browser does not support JavaScript. Enable JavaScript or use a browser that supports it to use Hubchat. 
</noscript>
```

### Parameters
Configuring the code is possible by adding parameters to the JavaScript code. Parameters are added to the `<div>` element as HTML5 `data-*` attributes. 

`<div data-forum=”community name”></div>`

#### data-forum-slug (required)
The name of the embedded community. The name has to match the name of the community that has been created at Hubchat. E.g. `data-forum-slug=”example-community”`.

#### data-limit (recommended)
Defines the number of recommendations displayed below the commenting thread. The default number of displayed recommendations is four. E.g. `data-limit=”0”` or `data-limit=”2”`.

#### data-featured-only
Should be true if you only wish to show featured discussions.

#### data-language
Data-language parameter defines the language in which the recommendations are displayed to the user. If the parameter is not used, the language is defined automatically based on the settings of the logged in user, or the browser language of the logged out user. E.g. `data-language=”en”`

#### Displaying Hubchat on a dynamic website (e.g. Ajax)
Hubchat plugins are typically initialized at page load. Loading a plugin or adding plugins dynamically after the page load is possible with the following code:

`window.Hubchat.initPlugins();`

The code will initialize the Hubchat elements again that have not been initialized yet.
