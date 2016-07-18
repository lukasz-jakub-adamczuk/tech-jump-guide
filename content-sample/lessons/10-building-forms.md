/*
Title: 10
Description: This description will go in the meta description tag
*/

Lesson 10

# Building Forms

## Initializing a Form

To add a form to a page, we’ll use the `<form>` [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form). The `<form>` element identifies where on the page control elements will appear. Additionally, the `<form>` element will wrap all of the elements included within the form, much like a `<div>` element.

    <form action="/login" method="post">
      ...
    </form>

A handful of different attributes can be applied to the `<form>` element, the most common of which are `action` and `method`. The `action` attribute contains the URL to which information included within the form will be sent for processing by the server. The `method` attribute is the HTTP method browsers should use to submit the form data. Both of these `<form>` attributes pertain to submitting and processing data.

## Text Fields & Textareas

When it comes to gathering text input from users, there are a few different elements available for obtaining data within forms. Specifically, text fields and textareas are used for collecting text- or string-based data. This data may include passages of text content, passwords, telephone numbers, and other information.

### Text Fields

One of the primary elements used to obtain text from users is the `<input>` [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Input). The `<input>` element uses the `type` attribute to define what type of information is to be captured within the control. The most popular type attribute value is text, which denotes a single line of text input.

Along with setting a `type` attribute, it is best practice to give an `<input>` element a `name` attribute as well. The `name` attribute value is used as the `name` of the control and is submitted along with the input data to the server.

    <input type="text" name="username">

### Input Text Demo

<p data-height="200" data-theme-id="0" data-slug-hash="pbdbBP" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/pbdbBP/">pbdbBP</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

The `<input>` element is self-contained, meaning it uses only one tag and it does not wrap any other content. The value of the element is provided by its attributes and their corresponding values.

Originally, the only two text-based `type` attribute values were `text` and `password` (for password inputs); however, HTML5 brought along a handful of new `type` attribute values.

These values were added to provide clearer semantic meaning for inputs as well as to provide better controls for users. Should a browser not understand one of these HTML5 `type` attribute values, it will automatically fall back to the `text` attribute value. Below is a list of the new HTML5 input types.

* color
* date
* datetime
* email
* month
* number
* range
* search
* tel
* time
* url
* week

### Textarea

Another element that’s used to capture text-based data is the `<textarea>` element. The `<textarea>` element differs from the `<input>` element in that it can accept larger passages of text spanning multiple lines. The `<textarea>` element also has start and end tags that can wrap plain text. Because the `<textarea>` element only accepts one type of value, the `type` attribute doesn’t apply here, but the `name` attribute is still used.

    <textarea name="comment">Add your comment here</textarea>

### Textarea Demo

<p data-height="300" data-theme-id="0" data-slug-hash="mEqEgN" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/mEqEgN/">mEqEgN</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

The `<textarea>` element has two sizing attributes: `cols` for width in terms of the average character width and `rows` for height in terms of the number of lines of visible text. The size of a textarea, however, is more commonly identified using the `width` and `height` properties within CSS.

### Multiple Choice Inputs & Menus

Apart from text-based input controls, HTML also allows users to select data using multiple choice and drop-down lists. There are a few different options and elements for these form controls, each of which has distinctive benefits.

### Radio Buttons

Radio buttons are an easy way to allow users to make a quick choice from a small list of options. Radio buttons permit users to select one option only, as opposed to multiple options.

To create a radio button, the `<input>` element is used with a `type` attribute value of radio. Each radio button element should have the same `name` attribute value so that all of the buttons within a group correspond to one another.

With text-based inputs, the value of an input is determined by what a user types in; with radio buttons a user is making a multiple choice selection. Thus, we have to define the input value. Using the `value` attribute, we can set a specific value for each `<input>` element.

Additionally, to preselect a radio button for users we can use the Boolean attribute `checked`.

    <input type="radio" name="day" value="Friday" checked> Friday
    <input type="radio" name="day" value="Saturday"> Saturday
    <input type="radio" name="day" value="Sunday"> Sunday

### Radio Button Demo

<p data-height="200" data-theme-id="0" data-slug-hash="ZOaOgv" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/ZOaOgv/">ZOaOgv</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Check Boxes

Check boxes are very similar to radio buttons. They use the same attributes and patterns, with the exception of checkbox as their `type` attribute value. The difference between the two is that check boxes allow users to select multiple values and tie them all to one control name, while radio buttons limit users to one value.

    <input type="checkbox" name="day" value="Friday" checked> Friday
    <input type="checkbox" name="day" value="Saturday"> Saturday
    <input type="checkbox" name="day" value="Sunday"> Sunday

### Check Boxes Demo

<p data-height="200" data-theme-id="0" data-slug-hash="dXkpyL" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/dXkpyL/">dXkpyL</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Drop-Down Lists

Drop-down lists are a perfect way to provide users with a long list of options in a practi- cal manner. A long column of radio buttons next to a list of different options is not only visually unappealing, it’s daunting and difficult for users to comprehend, especially those on a mobile device. Drop-down lists, on the other hand, provide the perfect format for a long list of choices.

To create a drop-down list we’ll use the `<select>` and `<option>` elements. The `<select>` element wraps all of the menu options, and each menu option is marked up using the `<option>` element.

The name attribute resides on the `<select>` element, and the value attribute resides on the `<option>` elements that are nested within the `<select>` element. The `value` attribute on each `<option>` element then corresponds to the `name` attribute on the `<select>` element.

Each `<option>` element wraps the text (which is visible to users) of an individual option within the list.

Much like the checked Boolean attribute for radio buttons and check boxes, drop-down menus can use the `selected` Boolean attribute to preselect an option for users.

    <select name="day">
      <option value="Friday" selected>Friday</option>
      <option value="Saturday">Saturday</option>
      <option value="Sunday">Sunday</option>
    </select>

### Drop-down List Demo

<p data-height="200" data-theme-id="0" data-slug-hash="JKOwvV" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/JKOwvV/">JKOwvV</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Multiple Selections

The Boolean attribute `multiple`, when added to the `<select>` element for a standard drop-down list, allows a user to choose more than one option from the list at a time. Additionally, using the `selected` Boolean attribute on more than one `<option>` element within the menu will preselect multiple options.

The size of the `<select>` element can be controlled using CSS and should be adjusted appropriately to allow for multiple selections. It may be worthwhile to inform users that to choose multiple options they will need to hold down the Shift key while clicking to make their selections.

    <select name="day" multiple>
      <option value="Friday" selected>Friday</option>
      <option value="Saturday">Saturday</option>
      <option value="Sunday">Sunday</option>
    </select>

## Form Buttons

After a user inputs the requested information, buttons allow the user to put that information into action. Most commonly, a submit input or submit button is used to process the data.

### Submit Input

Users click the submit button to process data after filling out a form. The submit button is created using the `<input>` element with a `type` attribute value of `submit`. The `value` attribute is used to specify the text that appears within the button.

    <input type="submit" name="submit" value="Send">

### Submit Input Demo

<p data-height="200" data-theme-id="0" data-slug-hash="ZOaPRZ" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/ZOaPRZ/">ZOaPRZ</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Submit Button

As an `<input>` element, the submit button is self-contained and cannot wrap any other content. If more control over the structure and design of the input is desired—-along with the ability to wrap other elements-—the `<button>` element may be used.

The `<button>` element performs the same way as the `<input>` element with the `type` attribute value of `submit`; however, it includes opening and closing tags, which may wrap other elements. By default, the `<button>` element acts as if it has a `type` attribute value of `submit`, so the `type` attribute and `value` may be omitted from the `<button>` element if you wish.

Rather than using the `value` attribute to control the text within the submit button, the text that appears between the opening and closing tags of the `<button>` element will appear.

    <button name="submit">
      <strong>Send Us</strong> a Message
    </button>

### Submit Button Demo

<p data-height="200" data-theme-id="0" data-slug-hash="rLYRPy" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/rLYRPy/">rLYRPy</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## Other Inputs

Besides the applications we’ve just discussed, the `<input`> element has a few other use cases. These include passing hidden data and attaching files during form processing.

### Hidden Input

Hidden inputs provide a way to pass data to the server without displaying it to users. Hidden inputs are typically used for tracking codes, keys, or other information that is not pertinent to the user but is helpful when processing the form. This information is not displayed on the page; however, it can be found by viewing the source code of a page. It should therefore not be used for sensitive or secure information.

To create a hidden input, you use the `hidden` value for the `type` attribute. Additionally, include the appropriate `name` and `value` attribute values.

    <input type="hidden" name="tracking-code" value="abc-123">

### File Input

To allow users to add a file to a form, much like attaching a file to an email, use the `file` value for the `type` attribute.

    <input type="file" name="file">


### File Input Demo

<p data-height="200" data-theme-id="0" data-slug-hash="grXEyV" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/grXEyV/">grXEyV</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Unfortunately, styling an `<input>` element that has a `type` attribute value of `file` is a tough task with CSS. Each browser has its own default input style, and none provide much control to override the default styling. JavaScript and other solutions can be employed to allow for file input, but they are slightly more difficult to construct.

## Organizing Form Elements

Knowing how to capture data with inputs is half the battle. Organizing form elements and controls in a usable manner is the other half. When interacting with forms, users need to understand what is being asked of them and how to provide the requested information.

By using labels, fieldsets, and legends, we can better organize forms and guide users to properly complete them.

### Label

Labels provide captions or headings for form controls, unambiguously tying them together and creating an accessible form for all users and assistive technologies. Created using the `<label>` element, labels should include text that describes the inputs or controls they pertain to.

Labels may include a `for` attribute. The value of the `for` attribute should be the same as the value of the `id` attribute on the form control the label corresponds to. Matching up the for and id attribute values ties the two elements together, allowing users to click on the `<label>` element to bring focus to the proper form control.

    <label for="username">Username</label>
    <input type="text" name="username" id="username">

### File Input Demo

<p data-height="200" data-theme-id="0" data-slug-hash="LkOoXx" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/LkOoXx/">LkOoXx</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

If desired, the `<label>` element may wrap form controls, such as radio buttons or check boxes. Doing so allows omission of the `for` and `id` attributes.

    <label>
      <input type="radio" name="day" value="Friday" checked> Friday
    </label>
    <label>
      <input type="radio" name="day" value="Saturday"> Saturday
    </label>
    <label>
      <input type="radio" name="day" value="Sunday"> Sunday
    </label>

### File Input Demo

<p data-height="200" data-theme-id="0" data-slug-hash="dXkBpJ" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/dXkBpJ/">dXkBpJ</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Fieldset

Fieldsets group form controls and labels into organized sections. Much like a `<section>` or other structural element, the `<fieldset>` is a block-level element that wraps related elements, specifically within a `<form>` element, for better organization. Fieldsets, by default, also include a border outline, which can be modified using CSS.

    <fieldset>
      <label>
        Username
        <input type="text" name="username">
      </label>
      <label>
        Password
        <input type="text" name="password">
      </label>
    </fieldset>

### Fieldset Demo

<p data-height="200" data-theme-id="0" data-slug-hash="oLoAYp" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/oLoAYp/">oLoAYp</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Legend

A legend provides a caption, or heading, for the `<fieldset>` element. The `<legend>` element wraps text describing the form controls that fall within the fieldset. The markup should include the `<legend>` element directly after the opening `<fieldset>` tag. On the page, the legend will appear within the top left part of the fieldset border.

    <fieldset>
      <legend>Login</legend>
      <label>
        Username
        <input type="text" name="username">
      </label>
      <label>
        Password
        <input type="text" name="password">
      </label>
    </fieldset>

### Legend Demo    

<p data-height="200" data-theme-id="0" data-slug-hash="QEajmw" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/QEajmw/">QEajmw</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>


## Form & Input Attributes

To accommodate all of the different form, input, and control elements, there are a number of attributes and corresponding values. These attributes and values serve a handful of different functions, such as disabling controls and adding form validation. Described next are some of the more frequently used and helpful attributes.

### Disabled

The `disabled` Boolean attribute turns off an element or control so that it is not available for interaction or input. Elements that are disabled will not send any value to the server for form processing.

￼Applying the `disabled` Boolean attribute to a `<fieldset>` element will disable all of the form controls within the fieldset. If the type attribute has a `hidden` value, the `hidden` Boolean attribute is ignored.

    <label>
      Username
      <input type="text" name="username" disabled>
    </label>

### Disabled Attribute Demo

<p data-height="200" data-theme-id="0" data-slug-hash="oLpbva" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/oLpbva/">oLpbva</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Placeholder

The `placeholder` HTML5 attribute provides a hint or tip within the form control of an `<input>` or `<textarea>` element that disappears once the control is clicked in or gains focus. This is used to give users further information on how the form input should be filled in, for example, the email address format to use.

    <label>
      Email Address
      <input type="email" name="email-address" placeholder="name@domain.com">
    </label>

### Placeholder Demo

<p data-height="200" data-theme-id="0" data-slug-hash="PzEkmP" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/PzEkmP/">PzEkmP</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

The main difference between the `placeholder` and `value` attributes is that the `value attribute value text stays in place when a control has focus unless a user manually deletes it. This is great for pre-populating data, such as personal information, for a user but not for providing suggestions.

### Required

The `required` HTML5 Boolean attribute enforces that an element or form control must contain a value upon being submitted to the server. Should an element or form control not have a value, an error message will be displayed requesting that the user complete the required field. Currently, error message styles are controlled by the browser and cannot be styled with CSS. Invalid elements and form controls, on the other hand, can be styled using the `:optional` and `:required` CSS pseudo-classes.

Validation also occurs specific to a control’s type. For example, an `<input>` element with a `type` attribute value of `email` will require not only that a value exist within the control, but also that it is a valid email address.

    <label>
      Email Address
      <input type="email" name="email-address" required>
    </label>

### Required Demo

<p data-height="200" data-theme-id="0" data-slug-hash="OXzrgr" data-default-tab="result" data-user="lukaszadamczuk" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/lukaszadamczuk/pen/OXzrgr/">OXzrgr</a> by Lukasz Adamczuk (<a href="http://codepen.io/lukaszadamczuk">@lukaszadamczuk</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Additional Attributes

Other form and form control attributes include, but are not limited to, the following. Please feel free to research these attributes as necessary.

* accept
* autocomplete
* autofocus
* formaction
* formenctype
* formmethod
* formnovalidate
* formtarget
* max
* maxlength
* min
* pattern
* readonly
* selectionDirection
* step

## Summary

Forms play a large role in how users interact with, provide information to, and take action on websites. We’ve taken all the right steps to learn not only how to mark up forms but also how to style them.

To quickly recap, within this lesson we discussed the following:

* How to initialize a form
* Ways to obtain text-based information from users
* Different elements and methods for creating multiple choice options and menus
* Which elements and attributes are best used to submit a form’s data for processing
* How best to organize forms and give form controls structure and meaning
* A handful of attributes that help collect more qualified data

Our understanding of HTML and CSS is progressing quite nicely, and we only have one more component to learn: tables. In the next chapter, we’ll take a look at how to organize and present data with tables.

## In Practice

Create very similar forms:
* 1st for signing in
* 2nd for registration
* 3rd for polling

![forms](../imgs/practice/forms.png)
