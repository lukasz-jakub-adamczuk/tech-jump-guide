/*
Title: 9
Description: This description will go in the meta description tag
*/

Lesson 9

# Adding Media

## Images

To add images to a page, we use the `<img>` inline element. The `<img>` element is a self-containing, or empty, element, which means that it doesn’t wrap any other content and it exists as a single tag. For the `<img>` element to work, a `src` attribute and value must be included to specify the source of the image. The `src` attribute value is a URL, typically relative to the server where a website is hosted.

In conjunction with the `src` attribute, the `alt` (alternative text) attribute, which describes the contents of an image, should be applied. The `alt` attribute value is picked up by search engines and assistive technologies to help convey the purpose of an image. The `alt` text will be displayed in place of the image if for some reason the image is not available.

    <img src="dog.jpg" alt="A black, brown, and white dog wearing a kerchief">

### Adding Images Demo

<p data-height="400" data-theme-id="0" data-slug-hash="WxkrXm" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/WxkrXm/">WxkrXm</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

> ### Supported Image Formats

> Images come in a variety of different file formats, and each browser may support (or not support) different formats. By and large, the most commonly supported formats online are `gif`, `jpg`, and `png` images. Of these, the most widely used formats today are `jpg` and `png`. The `jpg` format provides quality images with high color counts while maintaining a decent file size, ideal for faster load times. The `png` format is great for images with transparencies or low color counts. We most commonly see `jpg` images used for photographs and `png` images used for icons or background patterns.

### Sizing Images

It is important to identify the size of an image in order to tell the browser how large the image should be before the page even loads; thus the browser can reserve space for the image and render the page faster. There are a few different ways to size images so that they work well on a page. One option is to use the `width` and `height` attributes directly within the `<img>` tag in HTML.

Additionally, images may be sized using the `width` and `height` properties in CSS. When both the HTML attributes and CSS properties are used, the CSS attributes will take precedence over the HTML attributes.

Specifying either a width or height will cause the other dimension to adjust automatically to maintain the aspect ratio of the image. As an example, if we want an image to be `200` pixels tall but are less specifically concerned about how wide it is, we can set the `height` to `200` pixels, and the width of the image will adjust accordingly. Setting both a `width` and `height` will work also; however, doing so may break the aspect ratio of an image, causing it to appear distorted.

    img {
      height: 200px;
      width: 200px;
    }

<p data-height="400" data-theme-id="0" data-slug-hash="RRLQxQ" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/RRLQxQ/">RRLQxQ</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

While using the `width` and `height` attributes directly in HTML provides some semantic value by noting an image’s original size, it can be difficult to manage numerous images that all need to be the same size. In this event, it’s common practice to use CSS to resize the images.

### Positioning Images

We can use a number of different approaches to position images on a web page. By default images are positioned as inline-level elements; however, their positions may be changed using CSS, specifically the `float`, `display`, and box model properties, including `padding`, `border`, and `margin`.

### Inline Positioning Images

The `<img>` element is by default an inline-level element. Adding an image without any styles to a page will position that image within the same line as the content that surrounds it. Additionally, the height of the line in which an image appears will be changed to match the height of the image, which can create large vertical gaps within that line.

    <p>Gatsby is a black, brown, and white hound mix puppy who loves howling at fire trucks and collecting belly rubs. <img src="dog.jpg" alt="A black, brown, and white dog wearing a kerchief"> Although he spends most of his time sleeping he is also quick to chase any birds who enter his vision.</p>

### Inline Images Demo

<p data-height="400" data-theme-id="0" data-slug-hash="zBERWB" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/zBERWB/">zBERWB</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Leaving images untouched in their default positioning isn’t too common. More often than not, images are displayed as block-level elements or are floated flush to one side.

### Block Positioning Images

Adding the display property to an image and setting its value to block forces the image to be a block-level element. This makes the image appear on its own line, allowing the surrounding content to be positioned above and below the image.

    img {
      display: block;
    }

### Block Images Demo

<p data-height="400" data-theme-id="0" data-slug-hash="vKZdRd" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/vKZdRd/">vKZdRd</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Positioning Images Flush Left or Right

Sometimes displaying an image as `inline` or `block`, or perhaps even `inline-block`, isn’t ideal. We may want the image to appear on the left or right side of its containing element, while all of the other content wraps around the image as necessary. To do this, we use the `float` property with a value of either `left` or `right`.

Remembering back to Lesson 5, “[Positioning Content](05-positioning-content),” we recall that the `float` property was originally intended to position images to the left or right of a containing element. Now we’ll use it for that original purpose.

Floating an image is a start; however, all other content will align directly against it. To provide spacing around an image, we’ll use the `margin` property. Additionally, we can use the `padding`, `border`, and `background` properties to build a frame for the image, if desired.

    img {
      background: #eee;
      border: 2px solid #aaa;
      float: right;
      margin: 0 0 0 20px;
      padding: 8px;
    }

### Floating Images Demo

<p data-height="400" data-theme-id="0" data-slug-hash="KrXQBP" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/KrXQBP/">KrXQBP</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

> ### When to Use an Image Element vs. a Background Image

> There are two primary ways to add images to a web page. One way, as covered here, is to use the `<img>` element within HTML. Another way is to use the `background` or `background-image` property within CSS to assign a background image to an element. Either option will do the job; however, they each have specific use cases.

> The `<img>` element within HTML is the preferred option when the image being used holds semantic value and its content is relevant to the content of the page.

> The `background` or `background-image` property within CSS is the preferred option when the image being used is part of the design or user interface of the page. As such, it’s not directly relevant to the content of the page.

The `<img>` element is quite popular, and when it was originally added to the HTML specification it forever changed the way websites were built.

## Adding Audio

HTML5 provides a quick and easy way to add audio files to a website by way of the `<audio>` [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio). As with the `<img>` element, the `<audio>` element accepts a source URL specified by the src attribute. Unlike the `<img>` element, though, the `<audio>` element requires both opening and closing tags, which we’ll discuss soon.

    <audio src="genesis.ogg"></audio>

### Audio Attributes

Several other attributes may accompany the src attribute on the `<audio>` element; the most popular include `autoplay`, `controls`, `loop`, and `preload`.

The `autoplay`, `controls`, and `loop` attributes are all Boolean attributes. As Boolean attributes, they don’t require a stated value. Instead, when each is present on the `<audio>` element its value will be set to true, and the `<audio>` element will behave accordingly.

By default, the `<audio>` element isn’t displayed on a page. If the autoplay Boolean attribute is present on the `<audio>` element, nothing will appear on the page, but the audio file will automatically play upon loading.

    <audio src="genesis.ogg" autoplay></audio>

To display the `<audio>` element on a page, the `controls` Boolean attribute is necessary. When it’s applied to the `<audio>` element, the `controls` Boolean attribute will display a browser’s default audio controls, including play and pause, seek, and volume controls.

    <audio src="genesis.ogg" controls></audio>

### Adding Audio Demo

<p data-height="200" data-theme-id="0" data-slug-hash="ZOXxbL" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/ZOXxbL/">ZOXxbL</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

When present on the `<audio>` element, the loop Boolean attribute will cause an audio file to repeat continually, from beginning to end.

Lastly, the `preload` attribute for the `<audio>` element helps identify what, if any, information about the audio file should be loaded before the clip is played. It accepts three values: `none`, `auto`, and `metadata`. The `none` value won’t preload any information about an audio file, while the `auto` value will preload all information about an audio file. The `metadata` value sits in between the `none` and `auto` values, as it will preload any available metadata information about an audio file, such as the clip’s length, but not all information.

When the `preload` attribute isn’t present on the `<audio>` element, all information about an audio file is loaded, as if the value was set to `auto`. For this reason, using the `preload` attribute with a value of `metadata` or `none` is a good idea when an audio file is not essential to a page. It’ll help to conserve bandwidth and allow pages to load faster.

### Audio Fallbacks & Multiple Sources

At the moment, different browsers support different audio file formats, the three most popular of which are `ogg`, `mp3`, and `wav`. For the best browser support we’ll need to use a handful of audio fallbacks, which will be included inside an `<audio>` element’s opening and closing tags.

To begin, we’ll remove the `src` attribute from the `<audio>` element. Instead, we’ll use the `<source>` element, with a `src` attribute, nested inside the `<audio>` element to define a new source.

Using a `<source>` element and `src` attribute for each file format, we can list one audio file format after the other. We’ll use the type attribute to quickly help the browser identify which audio types are available. When a browser recognizes an audio file format it will load that file and ignore all the others.

Because it was introduced in HTML5, some browsers may not support the `<audio>` element. In this case, we can provide a link to download the audio file after any `<source>` elements within the `<audio>` element.

    <audio controls>
      <source src="genesis.ogg" type="audio/ogg">
      <source src="genesis.mp3" type="audio/mpeg">
      <source src="genesis.wav" type="audio/wav">
      Please <a href="genesis.mp3" download>download</a> the audio file.
    </audio>

To review the previous code, the `<audio>` element includes the `controls` Boolean attribute to ensure the audio player is displayed within browsers that support the element. The `<audio>` element does not include a `src` attribute and instead wraps three different `<source>` elements. Each `<source>` element includes a `src` attribute that references a different audio file format and a type attribute to identify the format of the audio file. As a last fallback, if a browser doesn’t recognize any of the audio file formats, the anchor link to download the element will be displayed.

In addition to the `<audio>` element, HTML5 also introduced the `<video>` element, which shares quite a few similarities with the `<audio>` element.

## Adding Video

Adding [video in HTML5](http://learn.shayhowe.com/html-css/adding-media/) is very similar to adding audio. We use the `<video>` element in place of the `<audio>` element. All of the same attributes (`src`, `autoplay`, `controls`, `loop`, and `preload`) and fallbacks apply here, too.

With the `<audio>` element, if the `controls` Boolean attribute isn’t specified the audio clip isn’t displayed. With videos, if the controls Boolean attribute is not specified the video will display. However, it is fairly difficult to view unless the `autoplay` Boolean attribute is also applied. In general, the best practice here is to include the `controls` Boolean attribute unless there is a good reason not to allow users to start, stop, or replay the video.

Since videos take up space on the page, it doesn’t hurt to specify their dimensions, which is most commonly done with `width` and `height` properties in CSS. This helps ensure that the video isn’t too large and stays within the implied layout of a page. Additionally, specifying a size, as with images, helps the browser render videos faster and allows it to allocate the proper space needed for the video to be displayed.

    <video src="blooming-flowers.mp4" controls></video>

### Adding Video Demo

<p data-height="450" data-theme-id="0" data-slug-hash="KrXRvo" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/KrXRvo/">KrXRvo</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>


> ### Customizing Audio & Video Controls

> By default, the `<audio>` and `<video>` element controls are determined by each browser independently. Depending on the design of a website, more authority over the look and feel of the media player may be needed. If this is the case, a customized player can be built, but it will require a little JavaScript to work.

> Additionally, if a customized player uses the `<img>` element as a control the value of the `alt` attribute should explictly state that the image is a control and requires the proper interaction to work.

### Poster Attribute

One additional attribute available for the `<video>` element is the `poster` attribute. The `poster` attribute allows us to specify an image, in the form of a URL, to be shown before a video is played.

    <video src="blooming-flowers.mp4" controls poster="blooming-flowers.png"></video>

### Poster Attribute Demo

<p data-height="450" data-theme-id="0" data-slug-hash="PzJZBj" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/PzJZBj/">PzJZBj</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Video Fallbacks

As with the `<audio>` element, video fallbacks are also necessary. The same markup format, with multiple `<source>` elements for each file type and a plain text fallback, also applies within the `<video>` element.

    <video controls>
      <source src="blooming-flowers.ogv" type="video/ogg">
      <source src="blooming-flowers.mp4" type="video/mp4">
      Please <a href="blooming-flowers.mp4" download>download</a> the video.
    </video>

One additional fallback option that could be used in place of a plain text fallback is to use a YouTube or Vimeo embedded video. These video hosting websites allow us to upload our videos, provide a standard video player, and enable us to embed our videos onto a page using an inline frame.

> ### HTML5 Audio & Video File Formats

> Browser support for the `<audio>` and `<video>` elements varies, as do the file formats required with these elements. Each browser has its own [preferred](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats) audio and video file formats.

> There are a few tools that help to convert an [audio](http://media.io/) or [video](http://ftp.osuosl.org/pub/pculture.org/mirovideoconverter//) file into different formats, and a quick search will provide an abundance of options.

### Adding Inline Frames

Another way to add content to a page is to embed another HTML page within the current page. This is done using an inline frame, or `<iframe>` element. The `<iframe>` element accepts the URL of another HTML page within the `src` attribute value; this causes the content from the embedded HTML page to be displayed on the current page. The value of the `src` attribute may be a URL relative to the page the `<iframe>` element appears on or an absolute URL for an entirely external page.

Many pages use the `<iframe>` element to embed media onto a page from an external website such as Google Maps, YouTube, and others.

    <iframe src="https://www.google.com/maps/embed"></iframe>

### Adding Inline Frames Demo

<p data-height="450" data-theme-id="0" data-slug-hash="kXGqWk" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/kXGqWk/">kXGqWk</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

The `<iframe>` element has a few default styles, including an inset `border` and a `width` and `height`. These styles can be adjusted using the `frameborder`, `width`, and `height` HTML attributes or by using the `border`, `width`, and `height` CSS properties.

### Seamless Inline Frames

Pages referenced within the `src` attribute of an `<iframe>` element play by their own rules, as they do not inherit any styles or behaviors from the page they are referenced on. Any styles applied to a page that includes an `<iframe>` element will not be inherited by the page referenced within the `<iframe>` element. Additionally, links within the page referenced within the `<iframe>` element will open inside that frame, leaving the page that contains the `<iframe>` element unchanged.

There will be times when we’ll want to change these behaviors, and the `seamless` Boolean attribute will allow us to do just that. When present on the `<iframe>` element, the `seamless` Boolean attribute allows styles from the page that includes an `<iframe>` element to be inherited by the page referenced within the `<iframe>` element. Additionally, the `seamless` Boolean attribute allows links clicked on a page referenced within an `<iframe>` element to be opened within the same window as the original page that includes the `<iframe>` element.

    <iframe src="contact.html" seamless></iframe>

The `seamless` Boolean attribute is a new attribute introduced in HTML5. Although the browser support for this attribute is growing, it will not work within older browsers. It’s advisable to test the `seamless` Boolean attribute before using it.

## Semantically Identifying Figures & Captions

With HTML5 also came the introduction of the `<figure>` and `<figcaption>` elements. These [elements](http://html5doctor.com/the-figure-figcaption-elements/) were created to semantically mark up self-contained content or media, commonly with a caption. Before HTML5 this was frequently done using an ordered list. While an ordered list worked, the markup was not semantically correct.

### Figure

The `<figure>` block-level element is used to identify and wrap self-contained content, often in the form of media. It may surround images, audio clips, videos, blocks of code, diagrams, illustrations, or other self-contained media. More than one item of self-contained content, such as multiple images or videos, may be contained within the `<figure>` element at a time. If the `<figure>` element is moved from the main portion of a page to another location (for example, the bottom of the page), it should not disrupt the content or legibility of the page.

    <figure>
      <img src="dog.jpg" alt="A black, brown, and white dog wearing a kerchief">
    </figure>

<p data-height="400" data-theme-id="0" data-slug-hash="OXxGNX" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/OXxGNX/">OXxGNX</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Figure Caption

To add a caption or legend to the `<figure>` element, the `<figcaption>` element is used. The `<figcaption>` may appear at the top of, bottom of, or anywhere within the `<figure>` element; however, it may only appear once. When it’s used, the `<figcaption>` element will serve as the caption for all content within the `<figure>` element.

Additionally, the `<figcaption>` element may replace an `<img>` element’s `alt` attribute if the content of the `<figcaption>` element provides a useful description of the visual content of the image.

    <figure>
      <img src="dog.jpg">
      <figcaption>A beautiful black, brown, and white hound dog wearing kerchief.</figcaption>
    </figure>

### Figure Caption Demo

<p data-height="400" data-theme-id="0" data-slug-hash="PzJgOW" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/PzJgOW/">PzJgOW</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Not all forms of media need to be included within a `<figure>` element or include a `<figcaption>` element; only those that are self-contained and belong together as a group.

## Summary

Alongside text, media is one of the largest parts of the web. Use of images, audio, and video has only grown over recent years, and it isn’t likely to slow down. Now we know how to incorporate these forms of media into our designs and how we can use them to enrich the content on our websites.

Within this lesson we covered the following:

* The best ways to add images, audio clips, videos, and inline frames to a page
* Different ways to position images in different situations
* How to provide audio and video fallbacks for older browsers
* Common attributes available to audio clips and videos
* The seamless attribute, which allows us to make inline frames behave as if they are part of the page they are referenced from
* The semantic way to mark up self-contained content, including media

We’re coming into the homestretch of learning HTML and CSS, with only a few more components left to introduce. Next on the list are forms.

## In Practice

Try to create webpage as much similar to screenshot below. It doesn't have to be pixel-perfect.

![cat-site-article-with-media](../imgs/practice/cat-site-article-with-media.png)
