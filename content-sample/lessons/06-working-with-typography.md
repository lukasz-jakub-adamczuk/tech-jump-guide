/*
Title: 06
Description: This description will go in the meta description tag
*/

Lesson 6

# Working with Typography

## Adding Color to Text

The only property we need to set the color of text is the `color` property. The `color` property accepts one color value, but in many different formats. These formats include keywords, hexadecimal values, and RGB, RGBa, HSL, and HSLa values. Hexadecimal values are the most prevalent, as they provide the most control with the least amount of effort.

Let’s take a look at the CSS required to change the color of all the text within the `<html>` element on a page:

    html {
      color: #555;
    }

## Changing Font Properties

CSS offers a lot of different properties for editing the look and feel of text on a page. These properties fit into two categories: font-based properties and text-based properties. Most of these properties will be prefaced with either `font-*` or `text-*`. To begin we’ll discuss the font-based properties.

### Font Family

The `font-family` property is used to declare which font—as well as which fallback or substitute fonts—should be used to display text. The value of the `font-family` property contains multiple font names, all comma separated.

The first declared font, starting from the left, is the primary font choice. Should the first font be unavailable, alternative fonts are declared after it in order of preference from left to right.

Font names consisting of two or more words need to be wrapped in quotation marks. Additionally, the last font should be a keyword value, which will use the system default font for the specified type, most commonly either `sans-serif` or `serif`.

The `font-family` property in action looks like this:

    body {
      font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    }

In this case, `Helvetica Neue` is the preferred font to display. If this font is unavailable or not installed on a given device, the next font in the list—Helvetica—will be used, and so on.

### Font Size

The `font-size` property provides the ability to set the size of text using common length values, including pixels, em units, percentages, points, or `font-size` keywords.

Here the CSS is setting a `font-size` of `14` pixels on the `<body>` element:

    body {
      font-size: 14px;
    }

### Font Style

To change text to italics, or to prevent text from being italicized, we’ll use the font-style property. The `font-style` property accepts four keyword values: `normal`, `italic`, `oblique`, and `inherit`. Of these four, the most commonly used are italic (sets text to italic) and normal (returns text to its normal style).

The following CSS sets all elements with a class of `special` to include a `font-style` of `italic`:

    .special {
      font-style: italic;
    }

### Font Variant

It doesn’t happen often, but occasionally text will need to be set in small capitals, also known as small caps. For this specific case we’ll use the `font-variant` property. The `font-variant` property accepts three values: `normal`, `small-caps`, and `inherit`. The most typically seen values are `normal` and `small-caps`, which are used to switch typefaces between normal and small caps variants.

To switch all elements with a class of firm, we’ll use a `font-variant` of small-caps:

    .firm {
      font-variant: small-caps;
    }

### Font Weight

Occasionally, we’ll want to style text as bold or to change the specific weight of a typeface. For these cases we’ll use the `font-weight` property. The `font-weight` property accepts either keyword or numeric values.

Keyword values include `normal`, `bold`, `bolder`, `lighter`, and `inherit`. Of these keyword values, it is recommended to primarily use `normal` and `bold` to change text from normal to bold and vice versa. Rather than using the keyword values `bolder` or `lighter`, it’s better to use a numeric value for more specific control.

In practice, here’s the CSS to set the `font-weight` to `bold` for any element with the class of `brave`:

    .brave {
      font-weight: bold;
    }

The numeric values `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, and `900` pertain specifically to typefaces that have multiple weights. The order of these weights starts with the thinnest weight, `100`, and scales up to the thickest weight, `900`. For reference, the keyword value of `normal` maps to `400` and the keyword `bold` maps to `700`; thus, any numeric value below `400` will be fairly thin, and any value above `700` will be fairly thick.

Changing the `font-weight` to `600` for any element with the class of `brave` now renders that text as semibold—not quite as thick as the `bold` keyword value from before:

    .brave {
      font-weight: 600;
    }

> ### Typeface Weights

> Before using a numeric value, we need to check and see whether the typeface we are using comes in the weight we’d like to use. Attempting to use a weight that’s not available for a given typeface will cause those styles to default to the closest value.

> For example, the Times New Roman typeface comes in two weights: `normal`, or `400`, and `bold`, or `700`. Attempting to use a weight of `900` will default the typeface to the closest related `weight`, `700` in this case.

### Line Height

Line height, the distance between two lines of text (often referred to as leading) is declared using the line-height property. The line-height property accepts all general length values, which we covered in Lesson 3, “[Getting to Know CSS](03-getting-to-know-css).”

The best practice for legibility is to set the `line-height` to around one and a half times our `font-size` property value. This could be quickly accomplished by setting the `line-height` to `150%`, or just `1.5`. However, if we’re working with a baseline grid, having a little more control over our `line-height` using pixels may be preferable.

Looking at the CSS, we’re setting a `line-height` of `22` pixels within the element, thus placing `22` pixels between each line of text:

    body {
      line-height: 22px;
    }

Line height may also be used to vertically center a single line of text within an element. Using the same property value for the `line-height` and `height` properties will vertically center the text:

    .btn {
      height: 22px;
      line-height: 22px;
    }

This technique may be seen with buttons, alert messages, and other single-line text blocks.

### Shorthand Font Properties

All of the `font`-based properties listed earlier may be combined and rolled into one `font` property and shorthand value. The `font` property can accept multiple `font`-based property values. The order of these property values should be as follows, from left to right: `font-style`, `font-variant`, `font-weight`, `font-size`, `line-height`, and `font-family`.

As a shorthand value, these property values are listed from left to right without the use of commas (except for font names, as the `font-family` property value uses commas). A forward slash, `/`, separator is needed between the `font-size` and `line-height` property values.

When using this shorthand value, every property value is optional *except* the `font-size` and `font-family` property values. That said, we can include only the `font-size` and `font-family` property values in the shorthand value if we wish.

    html {
      font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
    }

### Font Properties All Together

Let’s take a look at an example that uses all these `font`-based properties together. The following HTML and CSS demonstrates the different possibilities when styling text.

#### HTML

    <h2><a href="#">I Am a Developer</a></h2>

    <p class="byline">Posted by Lukasz Adamczuk</p>

    <p class="intro">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
    proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <a href="#">Continue&#8230;</a></p>

#### CSS

    h2,
    p {
      color: #555;
      font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
    }
    a {
      color: #0087cc;
    }
    a:hover {
      color: #ff7b29;
    }
    h2 {
      font-size: 22px;
      font-weight: bold;
      margin-bottom: 6px;
    }
    .byline {
      color: #9799a7;
      font-family: Georgia, Times, "Times New Roman", serif;
      font-style: italic;
      margin-bottom: 18px;
    }

### Font Properties Demo

<p data-height="400" data-theme-id="0" data-slug-hash="ezNgyb" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/ezNgyb/">ezNgyb</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

> ### CSS Pseudo-Classes

> The demonstration here uses the `:hover` CSS pseudo-class, something we’ve never seen before. For reference, pseudo-classes are keywords that may be added to the end of a selector to style an element when it’s in a unique state.

> The `:hover` pseudo-class styles an element when a user hovers over that element. When used with the `<a>` element, as shown here, all `<a>` elements will receive unique styles when they are hovered over. Now our `<a>` elements will change color upon being hovered over.

## Applying Text Properties

Knowing how to set the family, size, style, variant, weight, and line height of a font is only half the battle. Additionally we can decide how to align, decorate, indent, transform, and space text. Let’s start with text alignment.

### Text Align

Aligning text is an important part of building a rhythm and flow on a page; we do this using the `text-align` property. The `text-align` property has five values: `left`, `right`, `center`, `justify`, and `inherit`. All of these values are fairly straightforward; as expected, they align text to the left, right, or center, or they justify text.

The following CSS sets all paragraph text to be center aligned:

    p {
      text-align: center;
    }

The `text-align` property, however, should not be confused with the float property. The `text-align` values left and right will align text within an element to the left or right, whereas the float values left and right will move the entire element. Sometimes the `text-align` property will give us the desired outcome, and other times we may need to use the float property.

### Text Decoration

The `text-decoration` property provides a handful of ways to spruce up text. It accepts the keyword values of `none`, `underline`, `overline`, `line-through`, and `inherit`. Use of the `text-decoration` property varies, but the most popular use is to underline links, which is a default browser style.

Here the CSS styles any element with the class of `note` with a `text-decoration` of underline:

    .note {
      text-decoration: underline;
    }

Multiple text-decoration values may be applied to an element at once by space-separating each keyword within the value.

### Text Indent

The `text-indent` property can be used to indent the first line of text within an element, as is commonly seen in printed publications. All common length values are available for this property, including pixels, points, percentages, and so on. Positive values will indent text inward, while negative values will indent text outward.

Here, the CSS indents the text for all `<p>` elements inward by `20` pixels:

    p {
      text-indent: 20px;
    }

### Text Shadow

The `text-shadow` property allows us to add a shadow or multiple shadows to text. The property generally takes four values, all listed one after the other from left to right. The first three values are lengths, and the last value is a color.

Within the three length values, the first value determines the shadow’s horizontal offset, the second value determines the shadow’s vertical offset, and the third value determines the shadow’s blur radius. The fourth, and last, value is the shadow’s color, which can be any of the color values used within the `color` property.

The `text-shadow` property here is casting a `30%` opaque black shadow `3` pixels towards the right, `6` pixels down, and blurred `2` pixels off all `<p>` element text:

    p {
      text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
    }

Using negative length values for the horizontal and vertical offsets allows us to move shadows toward the left and the top.

Multiple text shadows can also be chained together using comma-separated values, adding more than one shadow to the text. Using numerous shadows allows us to place them above and below the text, or in any variation we desire.

> ### Box Shadow

> The `text-shadow` property places a shadow specifically on the text of an element. If we’d like to place a shadow on the element as a whole, we can use the `box-shadow` property.

> The `box-shadow` property works just like the `text-shadow` property, accepting values for horizontal and vertical offsets, a blur, and a color.

> The `box-shadow` property also accepts an optional fourth length value, before the color value, for the spread of a shadow. As a positive length value, the spread will expand the shadow larger than the size of the element it’s applied to, and as a negative length value the spread will shrink the shadow to be smaller than the size of the element it’s applied to.

> Lastly, the `box-shadow` property may include an optional `inset` value at the beginning of the value to place the shadow inside an element as opposed to outside the element.

### Text Transform

Similar to the `font-variant` property, there is the `text-transform` property. While the `font-variant` property looks for an alternate variant of a typeface, the `text-transform` property will change the text inline without the need for an alternate typeface. The `text-transform` property accepts five values: `none`, `capitalize`, `uppercase`, `lowercase`, and `inherit`.

The `capitalize` value will capitalize the first letter of each word, the `uppercase` value will capitalize every letter, and the `lowercase` value will make every letter lowercase. Using `none` will return any of these inherited values back to the original text style.

The following CSS sets all `<p>` element text to appear in all uppercase letters:

    p {
      text-transform: uppercase;
    }

### Letter Spacing

Using the `letter-spacing` property, we can adjust the space (or tracking) between the letters on a page. A positive length value will push letters farther apart from one another, while a negative length value will pull letters closer together. The keyword value none will return the space between letters back to its normal size.

Using a relative length value with the `letter-spacing` property will help ensure that we maintain the correct spacing between letters as the `font-size` of the text is changed. It is, however, always a good idea to double-check our work.

With the CSS here, all of the letters within our `<p>` elements will appear `0.5` em closer together:

    p {
      letter-spacing: -0.5em;
    }

### Word Spacing

Much like the `letter-spacing` property, we can also adjust the space between words within an element using the `word-spacing` property. The `word-spacing` property accepts the same length values and keywords as the `letter-spacing` property. Instead of spacing letters apart, though, the `word-spacing` property applies those values between words.

Here every word within a `<p>` element will be spaced `0.25` em apart.

    p {
      word-spacing: .25em;
    }

### Text Properties All Together

Let’s revisit our blog teaser demonstration from before, this time adding in a few text-based properties on top of our font-based properties.

#### HTML

    <h2><a href="#">I Am a Developer</a></h2>

    <p class="byline">Posted by Lukasz Adamczuk</p>

    <p class="intro">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
    proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <a href="#">Continue&#8230;</a></p>

#### CSS

    h2,
    p {
      color: #555;
      font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
    }
    a {
      color: #0087cc;
    }
    a:hover {
      color: #ff7b29;
    }
    h2 {
      font-size: 22px;
      font-weight: bold;
      letter-spacing: -.02em;
      margin-bottom: 6px;
    }
    h2 a {
      text-decoration: none;
      text-shadow: 2px 2px 1px rgba(0, 0, 0, .2);
    }
    .byline {
      color: #9799a7;
      font-family: Georgia, Times, "Times New Roman", serif;
      font-style: italic;
      margin-bottom: 18px;
    }
    .intro {
      text-indent: 15px;
    }
    .intro a {
      font-size: 11px;
      font-weight: bold;
      text-decoration: underline;
      text-transform: uppercase;
    }

### Text Properties Demo

<p data-height="400" data-theme-id="0" data-slug-hash="BzNpmZ" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/BzNpmZ/">BzNpmZ</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## Using Web-Safe Fonts

By default there are a few fonts that are pre-installed on every computer, tablet, smart-phone, or other web-browsing-capable device. Because they’ve been installed on every device, we can use these fonts freely within our websites, knowing that no matter what device is browsing our site, the font will render properly. These fonts have become known as “web-safe fonts.” There are only a handful of them, and the safest of the web-safe fonts are listed here:

* Arial
* Courier New, Courier
* Garamond
* Georgia
* Lucida Sans, Lucida Grande, Lucida
* Palatino Linotype
* Tahoma
* Times New Roman, Times
* Trebuchet
* Verdana

## Embedding Web Fonts

We also have the ability to upload fonts to a server and include them on a website via the CSS @font-face at-rule. This capability has done wonders for online typography. Now, more than ever, typography is coming to life online.

Embedding our own web fonts looks a bit like the following CSS. First, we use the @font-face at-rule to identify our font’s name, via the font-family property, as well as the source of our font (the path to the font file containing our chosen font), via the src property. From there we are able to use this font by including its name within any font-family property value.

    @font-face {
      font-family: "Lobster";
      src: local("Lobster"), url("lobster.woff") format("woff");
    }
    body {
      font-family: "Lobster", "Comic Sans", cursive;
    }

### Web Font Demo

<p data-height="400" data-theme-id="0" data-slug-hash="KMpWPb" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/KMpWPb/">KMpWPb</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Having the ability to embed any typeface on a website does not mean we legally have the authority to do so. Typefaces are works of art, and posting them on our server may allow others to easily steal them. The authority to use a typeface depends on the licensing we’ve been warranted.

Fortunately, the value of using new typefaces online has been recognized, and companies have begun developing ways to license and include new fonts on websites. Some of these companies, like Typekit and Fontdeck, work off a subscription model for licensing fonts, while others, like Google Fonts, license the fonts for free. Before uploading any fonts, let’s make sure we have permission to do so.

### Including Citations & Quotes

Writing online sometimes involves citing different sources or quotations. All of the different citation and quotation cases can be covered semantically in HTML using the `<cite>`, `<q>`, and `<blockquote>` elements. Because they are usually distinguished from regular text in appearance, we’ll discuss them here in the typography lesson.

Knowing when to use which element and attribute to properly mark up citations and quotes takes a bit of practice. In general, follow these rules:

* `<cite>`: Used to reference a creative work, author, or resource
* `<q>`: Used for short, inline quotations
* `<blockquote>`: Used for longer external quotations

### Citing a Creative Work

The `<cite>` inline element is used in HTML to specifically cite a creative work; the element must include either the title of the work, the author’s name, or a URL reference to the work. By default, content wrapped within the `<cite>` element will appear in italics within the browser.

For additional reference, it helps to include a hyperlink to the original source of the citation when relevant.

Here the book Steve Jobs, by Walter Isaacson, is referenced within the `<cite>` element. Inside the citation is also a hyperlink to the book.

    <p>The book <cite><a href="http://www.amazon.com/Steve-Jobs-Walter-Isaacson/dp/1451648537">Steve Jobs</a></cite> is truly inspirational.</p>

### Dialogue & Prose Quotation

Quite often, dialogue or prose is quoted inline, within other text. For this purpose, the `<q>` (or quote) inline element should be applied. The `<q>` element semantically indicates quoted dialogue or prose and shouldn’t be used for any other purposes.

By default, the browser will insert the proper quotation marks for us and will even change the quotation marks based on the language identified within the `lang` global attribute.

Here’s an example:

<p>Steve Jobs once said, <q>One home run is much better than two doubles.</q></p>

### Dialogue & Prose Citation

An optional attribute to include on the `<q>` element is the `cite` attribute. The `cite` attribute acts as a citation reference to the quote in the form of a URL. This attribute doesn’t alter the appearance of the element; it simply adds value for screen readers and other devices. Because the attribute isn’t viewable within the browser, it’s also helpful to provide a hyperlink to this source next to the actual quotation.

Here’s an example:

    <p><a href="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">Steve Jobs</a> once said, <q cite="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">One home run is much better than two doubles.</q></p>

### External Quotation

To quote a large block of text that comes from an external source and spans several lines, we’ll use the `<blockquote>` element. The `<blockquote>` is a block-level element that may have other block-level elements nested inside it, including headings and paragraphs.

Here’s an example that uses the `<blockquote>` element:

    <blockquote>
      <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
    </blockquote>

### External Citation

Longer quotes used within the `<blockquote>` element will often include a citation. This citation may comprise both the `cite` attribute and the `<cite>` element.

The `cite` attribute can be included on the `<blockquote>` element—in the same way that it was used on the `<q>` element earlier—to provide a citation reference to the quote in the form of a URL. The `<cite>` element then can fall after the actual quote itself to specify the original source of the quote, if relevant.

The HTML here outlines an extended quote from Steve Jobs that originally appeared in Fortune magazine. The quotation is marked up using the `<blockquote>` element with a `cite` attribute to specify where the quote originally appeared. In the `<blockquote>` element, the `<cite>` element, along with an `<a>` element, provides an additional citation and reference for the quote that is visible to users.

    <blockquote cite="http://money.cnn.com/magazines/fortune/fortune_archive/2000/01/24/272277/index.htm">
      <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
      <p><cite>&#8212; Steve Jobs in <a href="http://money.cnn.com/ magazines/fortune/fortune_archive/2000/01/24/272277/index.htm"> Fortune Magazine</a></cite></p>
    </blockquote>

### Summary

Learning how to style text is exciting, as our content can begin to convey some emotion. We can also start to play around with the hierarchy of our content, making our website more legible and digestible.

To quickly recap, within this lesson we discussed the following:

* Adding color to our text to enhance it
* Applying `font`-based properties, including `font-family`, `font-size`, `font-style`, `font-weight`, and more
* Applying `text`-based properties, including `text-align`, `text-decoration`, `text-indent`, `text-shadow`, and more
* The history behind web-safe fonts and how to embed our own web fonts
* How to properly mark up citations and quotations

Sharpening up our text and dabbling a bit with typography has brought our design along quite a way. Next, we’ll bring a little more color to our website by going over backgrounds and gradients.

