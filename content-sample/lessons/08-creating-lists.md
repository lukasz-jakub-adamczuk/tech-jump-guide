/*
Title: 8
Description: This description will go in the meta description tag
*/

Lesson 8

# Creating Lists

## Unordered Lists

An unordered list is simply a list of related items whose order does not matter. Creating an unordered list in HTML is accomplished using the unordered list block-level element, `<ul>`. Each item within an unordered list is individually marked up using the list item element, `<li>`.

By default, most browsers add a vertical `margin` and left `padding` to the `<ul>` element and precede each `<li>` element with a solid dot. This solid dot is called the list item marker, and it can be changed using CSS.

    <ul>
      <li>Orange</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>

## Ordered Lists

The ordered list element, `<ol>`, works very much like the unordered list element; individual list items are created in the same manner. The main difference between an ordered list and an unordered list is that with an ordered list, the order in which items are presented is important.

Because the order matters, instead of using a dot as the default list item marker, an ordered list uses numbers.

    <ol>
      <li>Head north on N Halsted St</li>
      <li>Turn right on W Diversey Pkwy</li>
      <li>Turn left on N Orchard St</li>
    </ol>

Ordered lists also have unique attributes available to them including `start` and `reversed`.

### Start Attribute

The `start` attribute defines the number from which an ordered list should start. By default, ordered lists start at `1`. However, there may be cases where a list should start at `30` or another number. When we use the `start` attribute on the `<ol>` element, we can identify exactly which number an ordered list should begin counting from.

The `start` attribute accepts only integer values, even though ordered lists may use different numbering systems, such as roman numerals.

    <ol start="30">
      <li>Head north on N Halsted St</li>
      <li>Turn right on W Diversey Pkwy</li>
      <li>Turn left on N Orchard St</li>
    </ol>

### Reversed Attribute

The `reversed` attribute, when used on the `<ol>` element, allows a list to appear in reverse order. An ordered list of five items numbered `1` to `5` may be reversed and ordered from `5` to `1`.

The `reversed` attribute is a Boolean attribute, and as such it doesn’t accept any value. It is either true or false. False is the default value; the value becomes true when the attribute name `reversed` appears on the `<ol>` element.

    <ol reversed>
      <li>Head north on N Halsted St</li>
      <li>Turn right on W Diversey Pkwy</li>
      <li>Turn left on N Orchard St</li>
    </ol>

### Value Attribute

The `value` attribute may be used on an individual `<li>` element within an ordered list to change its value within the list. The number of any list item appearing below a list item with a `value` attribute will be recalculated accordingly.

As an example, if the second list item has a `value` attribute value of `9`, the number on that list item marker will appear as if it is the ninth item. All subsequent list items will be numbered upwards from `9`.

### Description Lists

Another type of list seen online (but not as often as unordered or ordered lists) is the description list. Description lists are used to outline multiple terms and their descriptions, as in a glossary, for example.

Creating a description list in HTML is accomplished using the description list block-level element, `<dl>`. Instead of using a `<li>` element to mark up list items, the description list requires two block-level elements: the description term element, `<dt>`, and the description element, `<dd>`.

A description list may contain numerous terms and descriptions, one after the other. Additionally, a description list may have multiple terms per description, as well as multiple descriptions per term. A single term may have multiple meanings and warrant multiple descriptions. Conversely, a single description may be suitable for multiple terms.

When adding a description list, the `<dt>` element must come before the `<dd>` element. The definition term and the description that directly follows it correspond to one another; thus, the order of these elements is important.

By default, the `<dl>` element will include vertical margins, just like the `<ul>` and `<ol>` elements. Additionally, the `<dd>` element includes a left margin by default.

    <dl>
      <dt>study</dt>
      <dd>The devotion of time and attention to acquiring knowledge on an academic subject, especially by means of books</dd>
      <dt>design</dt>
      <dd>A plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
      <dd>Purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
      <dt>business</dt>
      <dt>work</dt>
      <dd>A person's regular occupation, profession, or trade</dd>
    </dl>

## Nesting Lists

One feature that makes lists extremely powerful is their ability to be nested. Every list may be placed within another list; they can be nested continually. But the potential to nest lists indefinitely doesn’t provide free rein to do so. Lists should still be reserved specifically for where they hold the most semantic value.

One trick with nesting lists is to know where to begin and end each list and list item. Speaking specifically about unordered and ordered lists, as that is where most nesting will occur, the only element that may reside directly within the `<ul>` and `<ol>` elements is the `<li>` element. To repeat, the only element we can place as a direct child of the `<ul>` and `<ol>` elements is the `<li>` element.

That said, once inside the `<li>` element, the standard set of elements may be added, including any `<ul>` or `<ol>` elements.

To nest a list rather than closing a list item, begin a new list. Once the nested list is complete and closed, close the wrapping list item and continue on with the original list.

    <ol>
      <li>Walk the dog</li>
      <li>Fold laundry</li>
      <li>
        Go to the grocery and buy:
        <ul>
          <li>Milk</li>
          <li>Bread</li>
          <li>Cheese</li>
        </ul>
      </li>
      <li>Mow the lawn</li>
      <li>Make dinner</li>
    </ol>

Because nesting lists can be a little tricky—and unwanted styles will appear if it’s done incorrectly—let’s quickly review. The `<ul>` and `<ol>` elements may contain only `<li>` elements. The `<li>` element may contain any normal element as desired; however, the `<li>` element has to be a direct child of either a `<ul>` or `<ol>` element.

It’s also worth noting that as lists are nested inside of other lists, their list item markers will change according to how deeply the list is nested. In the previous example, the unordered list nested within the ordered list uses hollow circles instead of solid discs as the list item marker. This change happens because the unordered list is nested one level into the ordered list.

Fortunately we have control over how these list item markers appear at any level, which we’ll take a look at next.

## List Item Styling

Unordered and ordered lists use list item markers by default. For unordered lists these are typically solid dots, while ordered lists typically use numbers. With CSS the style and position of these list item markers may be adjusted.

### List Style Type Property

The `list-style-type` property is used to set the content of a list item marker. The available values range from squares and decimal numbers all the way to Armenian numbering, and the style may be placed on either the `<ul>`, `<ol>`, or `<li>` elements within CSS.

Any `list-style-type` property value can be added to either unordered or ordered lists. With this in mind, it is possible to use a numeric list item marker on an unordered list and a nonnumeric marker on an ordered list.

#### HTML

    <ul>
      <li>Orange</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>

#### CSS

    ul {
      list-style-type: square;
    }

### List Style Type Values

As previously mentioned, the `list-style-type` property comes with a handful of different values. The following list outlines these values as well as their corresponding content.

| List Style Type | Value Content |
| --------------- | ------------- |
| none | No list item |
| disc | A filled circle |
| circle | A hollow circle |
| square | A filled square |
| decimal| Decimal numbers |
| decimal-leading-zero | Decimal numbers padded by initial zeros |
| lower-roman | Lowercase roman numerals |
| upper-roman | Uppercase roman numerals |
| lower-greek | Lowercase classical Greek |
| lower-alpha / lower-latin | Lowercase ASCII letters |
| upper-alpha / upper-latin | Uppercase ASCII letters |
| armenian | Traditional Armenian numbering |
| georgian | Traditional Georgian numbering |

### Using an Image as a List Item Marker

There may come a time when the default `list-style-type` property values are not enough, and we want to customize our own list item marker. Doing so is most commonly accomplished by placing a background image on each `<li>` element within a list.

The process includes removing any default `list-style-type` property value and adding a background image and padding to the `<li>` element.

In detail, the `list-style-type` property value of `none` will remove existing list item markers. The `background` property will identify a background image, along with its position and repeat value, if necessary. And the `padding` property will provide space to the left of the text for the background image.

#### HTML

    <ul>
      <li>Orange</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>

#### CSS

    li {
      background: url("arrow.png") 0 50% no-repeat;
      list-style-type: none;
      padding-left: 12px;
    }

### List Style Position Property

By default the list item marker is to the left of the content within the `<li>` element. This list style positioning is described as `outside`, meaning all of the content will appear directly to the right, outside of the list item marker. Using the `list-style-position` property, we can change the default value of `outside` to `inside` or `inherit`.

The outside property value places the list item marker to the left of the `<li>` element and doesn’t allow any content to wrap below the list item marker. The inside property value (which is rarely seen or used) places the list item marker in line with the first line of the `<li>` element and allows other content to wrap below it as needed.

#### HTML

    <ul>
      <li>Cupcakes...</li>
      <li>Sprinkles...</li>
    </ul>

#### CSS

    ul {
      list-style-position: inside;
    }

### Shorthand List Style Property

The list style properties discussed thus far, `list-style-type` and `list-style-position`, can be combined into one shorthand `list-style` property value. When using the `list-style` property, we can use one or all list style property values at a time. The order of these shorthand values should be `list-style-type` followed by `list-style-position`.

    ul {
      list-style: circle inside;
    }
    ol {
      list-style: lower-roman;
    }

## Horizontally Displaying List

Occasionally we may want to display lists horizontally rather than vertically. Perhaps we want to divide a list into multiple columns, to build a navigational list, or to put a few list items in a single row. Depending on the content and desired appearance, there are a few different ways to display lists as a single line, such as by making the `display` property value of `<li>` elements `inline` or `inline-block` or by floating them.

### Displaying List

The quickest way to display a list on a single line is to give the `<li>` elements a `display` property value of `inline` or `inline-block`. Doing so places all the `<li>` elements within a single line, with a single space between each list item.

If the spaces between each of the `<li>` elements are troublesome, they may be removed using the same techniques we discussed in Lesson 5, “[Positioning Content](05-positioning-content).”

More often than not`, we’ll use the `inline-block` property value rather than the `inline` property value. The `inline-block` property value allows us to easily add vertical margins and other spacing to the `<li>` elements, whereas the `inline` property value does not.

When changing the `display` property value to `inline` or `inline-block`, the list item marker, be it a bullet, number, or other style, is removed.

#### HTML

    <ul>
      <li>Orange</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>

#### CSS

    li {
      display: inline-block;
      margin: 0 10px;
    }

### Floating List

Changing the `display` property value to `inline` or `inline-block` is quick; however, it removes the list item marker. If the list item marker is needed, floating each `<li>` element is a better option than changing the `display` property.

Setting all `<li>` elements’ float property to left will horizontally align all `<li>` elements directly next to each other without any space between them. When we float each `<li>` element, the list item marker is displayed by default and will actually sit on top of the `<li>` element next to it. To prevent the list item marker from being displayed on top of other `<li>` elements, a horizontal `margin` or `padding` should be added.

#### HTML

    <ul>
      <li>Orange</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>

#### CSS

    li {
      float: left;
      margin: 0 20px;
    }

## Summary

Lists are used quite commonly in HTML, often in places that might not be obvious or apparent. The key is to use them as semantically as possible and to leverage them where they best fit.

Let’s recap. Within this lesson we covered the following:

* How to create unordered, ordered, and description lists
* How to properly nest lists inside of other lists
* How to change the list item marker style and position
* How to use a background image instead of a list item marker
* How to horizontally display or float lists

Now that we know how to add lists to our pages, let’s add media to our pages, too. In the next chapter we’ll dive into embeddable media such as images, audio, and video.




