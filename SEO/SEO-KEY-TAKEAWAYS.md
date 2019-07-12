# SEO KEY TAKEAWAYS

## Code (HTML tags)
* Use Robots meta tag
    * `<meta name=”robots” content=[parameter]>`
    * Default value is follow (means crawler will follow all the links in the page), index (means crawler will index the page) 
    * E.g <meta name=”robots” content=[follow,noindex]>
* Use canonical link element to avoid duplicate content
    * Add a rel=canonical link from the non-canonical page to the canonical one. So if we picked the shortest URL as our canonical URL, the other URL would link to the shortest URL in the <head> section of the page – like this:
        `<link rel="canonical" href="http://pykih.com/page/" />`
    * Add canonical url to all pages.
* For e.g. crawler can reach a specific page using the following url:
        www.pykih.com/organization/undp
        www.pykih.com/undp
        www.pykih.com/organization/project/undp
    In this case identify the main page and put canonical URL in all the pages. For e.g. if we set the main to www.pykih.com/undp then canonical URL will be
    `<link rel="canonical" href="http://pykih.com/undp/" />`
* Use descriptive alt tages. `<img>`.
    * Alt tag should contain keyphrase of the page and in case linked image, the alt text should be the title of the page it’s linking to.
* Use structured data
    * Use schema.org to find the tags for the schemas and it's parameters
    * Then Use JSON-ld to create structured markup and insert that markup in `<head>` tag of of the page:
    * E.g. markup of recipe
 ```javascript
    <script type="application/ld+json">
    {
      "@context": "http://schema.org",
      "@type": "Recipe",
      "author": "John Smith",
      "cookTime": "PT1H",
      "datePublished": "2009-05-08",
      "description": "This classic banana bread recipe comes from my mom -- the walnuts add a nice texture and flavor to the banana bread.",
      "image": "bananabread.jpg",
      "recipeIngredient": [
        "3 or 4 ripe bananas, smashed",
        "1 egg",
        "3/4 cup of sugar"
      ],
       "interactionStatistic": {
            "@type": "InteractionCounter",
            "interactionType": "http://schema.org/Comment",
            "userInteractionCount": "140"
          },
          "name": "Mom's World Famous Banana Bread",
          "nutrition": {
           "@type": "NutritionInformation",
            "calories": "240 calories",
            "fatContent": "9 grams fat"
          },
          "prepTime": "PT15M",
          "recipeInstructions": "Preheat the oven to 350 degrees. Mix in the ingredients in a bowl. Add the flour last. Pour the mixture into a loaf pan and bake for one hour.",
          "recipeYield": "1 loaf",
          "suitableForDiet": "http://schema.org/LowFatDiet"
        }
</script>
```
* Use tools such as [Structure Data testing](https://search.google.com/structured-data/testing-tool/u/0/) to check any errors in JSON-LD.
* Add keywords on the `h1` tag of the page.
* Include **meta tags** such as meta description and **meta title** and make sure these contains keywords.
* Make sure that **title** tag of every page is different.
* Add descriptive anchor text.
    * Anchor text which links to other pages should contain keywords of the page and should describe what the page is about.
    * Never just link the plain url like https://example.com
* Use geo meta tags to let the search engines know your location.
* While creating pagination always add `rel=”next”` and `rel=”prev”` in the link tag.

## Images

* Choose a right file name
    * Google uses the file name to determine what an image is about. That’s why you should use your focus keyphrase in the image file name.
    * **Note** that you should always start your file name with your main keyphrase.

        | Format       | Usefullness      | 
        | ------------- |:-------------:| 
        |    JPEG       |larger photos or illustrations|
        |    PNG           |    To preserve background transparency           |
        |       SVG        |       For logos and icons        |
        |       webp            |   Produce high-quality results with smaller file sizes        |
* Resize your images
    * Make sure that scaled image is compressed so it is served in the smallest file size possible.
    * Reduce the size of images, by removing the Exif data. (using tools)
* Use responsive image which serves different image per screen width.

## Page Url’s
* Url should describe your content and should include an accurate phrase or term that pertains to the page content 
* Include Keywords in URL.
* Use hyphens to separate words
* Use lowercase letters
* Keep urls short and descriptive
* Always use **absolute url** not the relative ones.
   * absolute urls: `<a href="services/video-production/corporate-videos">`
   * relative urls:  `<a href="/corporate-videos">`
<a href="corporate-videos">`
* Use subdirectory structure rather than subdomain structure.
    * Better: http://www.example.com/topic
    * Not - optimized: http://topic.example.com
* Minimize dynamic url strings.
    * Fix the problem by removing characters such as ?, #, !, *, %, and & and reducing the number of parameters to one.
    * If there are such types of url use **mod_rewrite** to create restful URL architecture.
## Robots.txt
* Only use to block the complete sub-directory rather than individual pages.
* Don't add css and js file until necessary.
* List all the XML sitemaps. (important)
* Use google search console to check and validate robots.txt file.

## XML sitemaps
* Create xml sitemaps which contains all the URL of the page. You can also create multiple sitemaps.
* Upload sitemap on google webmaster which helps google to crawl all your pages.
* Format of XML sitemap is.
 ![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/image
    * Should contain location tag.
        * Should accurately reflect your site protocol (http or https) and if you have chosen to include or exclude www.
    * Last modified date
    * Priority Tag
    **NOTE->** These are not automatically added you need to write a script or add manually.
    *  Limitations of XML sitemap
        *  A maximum of 50000 urls
        * Uncompressed file size of 50mb
    * After creating sitemap add them to google, yahoo and bing webmaster tools.
    * Add your sitemap path to robots.txt file.
* Optimizing sitemap
    * Only include SEO relevant pages in sitemap.
    * Exclude:
        * Non-canonical pages.
        * Duplicate pages.
        * Paginated pages.
        * Parameter or session ID based URLs.
        * Site search result pages.
        * Reply to comment URLs.
        * Share via email URLs.
        * URLs created by filtering that are unnecessary for SEO.
        * Archive pages.
        * Any redirections (3xx), missing pages (4xx) or server error pages (5xx).
        * Pages blocked by robots.txt.
        * Pages with noindex.
        * Resource pages accessible by a lead gen form (e.g., white paper PDFs).
        * Utility pages that are useful to users, but not intended to be landing pages (login page, contact us, privacy policy, account pages, etc.).
* If number of url exceeds then use [sitemap index file](https://support.google.com/webmasters/answer/75712?hl=en).
    * Use descriptive sitemap names that reflect your site structure. 
    * Don’t set the sitemap name as sitemap1, sitemap2, sitemap3, instead follow the structure of your website and name accordingly,
    Such as project sitemap should be /sitemap/projects, organization should be /sitemap/organization.
* If you have video in the website then create a seperate video sitemap.

## Mobile Friendliness
* Is your website compatible with mobile.
* Test loading time on mobile devices.
* Don't use flash and pop ups.
* Use google Mobile friendly test to check mobile friendly.
* Responsive Design
    * Site should be adjustable on the screen on which it is viewed on.
* Do not restrict users to view content. Some websited don't allow users to view some content on the mobile site. Don't do that.
* Dynamic Serving 
    * With this method, you have two versions of your Web site: one for smartphones, and another for larger devices. The Web server decides which version to send when a page is requested.
    * Separate Urls:
        * In this case, you have two versions of your site. The server directs the user to the most appropriate site, on a different URL, depending on the device.
        * Eg of seperate url is like of facebook, when it checks the user agent is from desktop browser it opens www.facebook.com and when it checks that user agent is from mobile browser it redirects the user to m.facebook.com.
* https://moz.com/learn/seo/mobile-optimization

## Keywords:

* Use keywords in folder names and filenames, and in page files and image files.
* Use keywords near the top of the content of the page.
* Place keywords into `<H>` (heading) tag.
* Use bold and italic keywords.
* Only one keyword or keyphrase per page and use this keyword between 1%-5% of the page.
* Use keywords in meta tags of the page.
* Links between pages within your site contain keywords.
* Use synonyms and different word forms such as singulars and plurals.
* Use tools such as 
    * [Google Adwords Keywords Planner]( https://adwords.google.com/KeywordPlanner)
    * [Bing Keywords Research Tool](https://www.bing.com/toolbox/keywords)

## Information Architecture:

* Identify most important pages/projects of the website.
* Link most important pages from home pages.
* Minimize cluttering the homepage.
* Logo should link to the homepage.
* Descriptive navigation links.
    * Is the internal anchor text used in navigation links descriptive and aligned with keyword goals?.
* Divide content in Categories and Sub-Categories
    * Add categories on the homepage and also on the main menu of the site.
    * Name of the category should resemble the search terms used by your audience.
    * Thumb rule for categories is that no category should be twice the size of any other category.
    * Are all targeted keywords properly represented in site navigation.
* Create Easy Navigation for the users:
    * Breadcrumbs
        * Visible above the title of the post.
    * Tags
        * Limit the amount of tags you use;
        * Make sure tags are used more than one/two
        * Make sure tags are visible.
    * Make sure every page contains some links to other pages on your site (internal linking).
    *  Anchor tags should be clear and specific. It should reflect the context of the page it is linked to.
    *   Anchor text is one of the most important, specify the page heading in this.
    * Identify the cornerstone content of your website and create most links towards it. Cornerstone content is the most important content on your website. It represents your mission. It is lengthy, timeless and informative. It should be regularly updated. 
* URL structure should be in harmony with the site navigation structure,
* Make sure don't use canonical tags in the paginated pages.
* Your main pages should not be more then two clicks away from the home page.

## Copywriting:
* Checklist to keep in mind while writing your post:
    * Length
        * Your text contains 300 to 800 words.
    * Preparation 
        * Prepare an audience profile (ask yourself "Who is going to read this?")
        * Gauge search intent of audience (are they looking for information i.e. informative intent or are they looking to buy something i.e. commercial intent?) 
        * Be clear about your text purpose (is it to convince, inform or entertain?)
        * Your central message is clear and formulated and conveyed at the correct places (usually 1st and last paragraph).
        * You use a tone appropriate for your audience.
    * Keyword
        * You use your keywords at the right places.
        * You use your keyphrase an adequate amount of times (should comprise 1-5% of the text).
    * Structure
        * There should be clear headings and subheadings.
        * In each paragraph, discuss only one topic.
        * Paragraphs should never be just 1 sentence. Each para should at least have 3 sentences & a maximum of 4-5 sentences. 
        * The subtopics of your text are discussed in a logical order.
        * Make clear transitions between paragraphs.
        * Add headings to longer paragraphs or clusters of thematically similar smaller paragraphs. 
        * Add keyphrase to 1 or more headings.
    * Readability
        * Use synonyms to avoid using the same word over and over.
        * Subheadings should be clear and informative (no cliffhangers)
        * Sentences should show variation in length, structure and beginning words.
        * Use transition words correctly and frequently.
        * Avoid passive voice whenever possible.
        * Avoid complex words whenever possible.
    * Style
        * Writing style should be consistent across the text.
        * Use concrete language.
        * Use examples correctly (if applicable).
        * Use asides correctly (if applicable).
        * The humor you used is appropriate (if applicable).
        * Metaphors and expressions are used in moderation (if applicable).
        * After you started with an anecdote or case study, you have rounded things up in the final paragraph (if applicable).
    * Typography
    * Editing
        * Go through text and make sure there isn't too much information in text. 
        * Sentences should not be longer than 20 words or too complicated.
        * Long sentences should comprise no more than 1/4th of the text.
        * Change passive sentences to active ones.
        * Use SVO order when forming sentences (Subject-Verb-Object)

## UX:

| Do's       | Don'ts    | 
| ------------- |:-------------:| 
|Make your buttons look like buttons|Don’t write: ‘Click here to (…)’.Button should state clear call-to-action, for example: ‘buy this product’, ‘contact us’, ‘log in’, ‘activate’, and ‘download’.|
|Links should have a different color than the rest of the text, but this shouldn’t be the only visual means of indicating it’s a link|Don’t make users guess where their click takes them|
|Communicate with the words your users use|Make the items descriptive. Don’t call an item ‘employment opportunities’, call it ‘jobs’.|
|Make sure important pages on your site are no more than three clicks away from your homepage.
||
|Make sure people can always find their way back out of the rabbit hole they go into.||
|Provide users with some kind of map which they can use to navigate. For e.g. using breadcrumbs.||
|If there is a search box, make it easier to find.||

## Metrics for Checking

* Speed
    * Loading time of the site should be less.
    * Tools for site-speed:-
        * Web page test
        * Google PageSpeed Insights
        * Google lighthouse
        * Pingdom tools
    * Things to improve site-speed:-
        *Enable compression of your website file using compressing tools such as GZIP.
        * Minify css, javascript, HTML
        * Reduce redirects
        * Remove render blocking javascript
* Security
    * Website secured with SSL.
    * Use of HTTPS over HTTPS.
* Accessibility
    * Test your site with disabling styles
        * See if the quality and semantics of HTML are done right.
        * There is a logical grouping of elements and the structure is clear
    * Unplug your mouse and use the keyboard for navigation
    * Check the contrast
        * The most frequently used requirement for this is to guarantee a contrast of at least 4.5:1 between text and background.
        * Very big text can have a lower ratio of 3:1.
        * Check contrast on color [contrast analyser](https://developer.paciellogroup.com/resources/contrastanalyser/).
    *   Use accessibility evaluation tools
        * Webaim Wave 
        * Deque Axe
    * Conversion Rate Optimization
        *   User Testing
            * Perform A/B testing
             * Consider putting a small survey and visitors some questions such as. ‘What’s the goal of your visit today?’ Or: ‘What’s keeping you from buying this product?’.

## Tools

| FOR     | TOOLS   | 
| ------------- |:-------------:| 
|Keyphrase Searching| Google Adwords Keyword Planner, Yoast Suggest Google Trends Internal search engine, [Answerthepublic](https://answerthepublic.com/) , [Bing keyword Research](https://www.bing.com/toolbox/keywords)|
|Sitespeed Checking| Web page test, Google PageSpeed Insights Google lighthouse Pingdom tools|			
|Structured Data| [JSON-LD](https://json-ld.org/), Schema.org, [google structured data markup](https://search.google.com/structured-data/testing-tool/u/0/)|
|Structured Data testing| Structure Data testing|			
|SEO Tools |Google analytics, google search console|
|Crawlability Check|Google search console|.
|Accessibility evaluation tools| [Webaim Wave](https://wave.webaim.org/extension/), [Deque Axe](https://www.deque.com/axe/)
|User testing for CRO (conversion rate optimization)| abtestguide.com|
|Reducing image file size|[ImageOptim](https://imageoptim.com/mac), [JPEGmini](https://www.jpegmini.com/), jpeg.io, Kraken.io|
|Compression of File| [GZIP](https://www.gnu.org/software/gzip/)|
|Mobile friendly test|[Mobile friendly test](https://search.google.com/test/mobile-friendly)|
|Google Webmaster|https://www.google.com/webmasters/#?modal_active=none|
|Sitemap| [Sitemap Index](https://support.google.com/webmasters/answer/75712?hl=en), [Schema Sitemap](https://www.sitemaps.org/protocol.html), [Creating Site Map](https://support.google.com/webmasters/answer/156184)|
|Submitting Sites| [Google](https://www.google.com/webmasters/tools/submit-url), [Bing](http://www.bing.com/toolbox/submit-site-url) |
|Page Speed|[Google Page Speed](https://developers.google.com/speed/pagespeed/insights/)|
|Website Crawler| [Screaming Frog](https://www.screamingfrog.co.uk/seo-spider/)|
|A/B Testing|[AB Test Guide](https://abtestguide.com/calc/)|
