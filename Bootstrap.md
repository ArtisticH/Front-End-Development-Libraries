# Bootstrap
Bootstrap is a front end framework used to design responsive web pages and applications. It takes a mobile-first approach to web development, and includes pre-built CSS styles and classes, plus some JavaScript functionality.

In this course, you'll learn how to build responsive websites with Bootstrap, and use its included classes to style buttons, images, forms, navigation, and other common elements.

## Use Responsive Design with Bootstrap Fluid Containers
In the HTML5 and CSS section of freeCodeCamp we built a Cat Photo App. Now let's go back to it. This time, we'll style it using the popular Bootstrap responsive CSS framework.

Bootstrap will figure out how wide your screen is and respond by resizing your HTML elements - hence the name responsive design.

With responsive design, there is no need to design a mobile version of your website. It will look good on devices with screens of any width.

You can add Bootstrap to any app by adding the following code to the top of your HTML:
```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>
```
In this case, we've already added it for you to this page behind the scenes. Note that using either `>` or `/>` to close the `link` tag is acceptable.

To get started, we should nest all of our HTML (except the `link` tag and the `style` element) in a `div` element with the class `container-fluid`.

## Make Images Mobile Responsive
First, add a new image below the existing one. Set its `src` attribute to `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

It would be great if this image could be exactly the width of our phone's screen.

Fortunately, with Bootstrap, all we need to do is add the `img-responsive` class to your image. Do this, and the image should perfectly fit the width of your page.
```html
<img class='img-responsive' src='https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg'>
```

## Center Text with Bootstrap
Now that we're using Bootstrap, we can center our heading element to make it look better. All we need to do is add the class `text-center` to our `h2` element.

Remember that you can add several classes to the same element by separating each of them with a space,
```html
<h2 class="red-text text-center">your text</h2>
```

## Create a Bootstrap Button
Bootstrap has its own styles for `button` elements, which look much better than the plain HTML ones.

Create a new `button` element below your large kitten photo. Give it the `btn` and `btn-default` classes, as well as the text of `Like`.
```html
<button class="btn btn-default">Like</button>
```

## Create a Block Element Bootstrap Button
Normally, your `button` elements with the `btn` and `btn-default` classes are only as wide as the text that they contain.  

By making them block elements with the additional class of `btn-block`, your button will stretch to fill your page's entire horizontal space and any elements following it will flow onto a "new line" below the block. This button would take up 100% of the available width.  

Note that these buttons still need the btn class.
```html
<button class="btn btn-default btn-block">Like</button>
```

## Taste the Bootstrap Button Color Rainbow
The `btn-primary` class is the main color you'll use in your app. It is useful for highlighting actions you want your user to take.

Replace Bootstrap's `btn-default` class with `btn-primary` in your button.

Note that this button will still need the `btn` and `btn-block` classes.
```html
<button class="btn btn-primary btn-block">Like</button>
```

## Call out Optional Actions with btn-info
Bootstrap comes with several pre-defined colors for buttons. The `btn-info` class is used to call attention to optional actions that the user can take.

Create a new block-level Bootstrap button below your `Like` button with the text `Info`, and add Bootstrap's `btn-info` class to it.

Note that these buttons still need the `btn` and `btn-block` classes.
```html
<button class="btn btn-block btn-primary">Like</button>
<button class="btn btn-block btn-info">Info</button>
```

## Warn Your Users of a Dangerous Action with btn-danger
Bootstrap comes with several pre-defined colors for buttons. The `btn-danger` class is the button color you'll use to notify users that the button performs a destructive action, such as deleting a cat photo.

Create a button with the text `Delete` and give it the class `btn-danger`.
```html
<button class="btn btn-block btn-danger">Delete</button>
```

## Use the Bootstrap Grid to Put Elements Side By Side
Bootstrap uses a responsive 12-column grid system, which makes it easy to put elements into rows and specify each element's relative width. Most of Bootstrap's classes can be applied to a `div` element.

Bootstrap has different column width attributes that it uses depending on how wide the user's screen is. For example, phones have narrow screens, and laptops have wider screens.

Take for example Bootstrap's `col-md-*` class. Here, `md` means medium, and `*` is a number specifying how many columns wide the element should be. In this case, the column width of an element on a medium-sized screen, such as a laptop, is being specified.

In the Cat Photo App that we're building, we'll use `col-xs-*`, where `xs` means extra small (like an extra-small mobile phone screen), and `*` is the number of columns specifying how many columns wide the element should be.

Put the `Like`, `Info` and `Delete` buttons side-by-side by nesting all three of them within one `<div class="row">` element, then each of them within a `<div class="col-xs-4">` element.

The `row` class is applied to a `div`, and the buttons themselves can be nested within it.

## Ditch Custom CSS for Bootstrap
```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<div class="container-fluid">
  <h2 class="red-text text-center">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats love:</p>
  <ul>
    <li>cat nip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```

We can clean up our code and make our Cat Photo App look more conventional by using Bootstrap's built-in styles instead of the custom styles we created earlier.

Don't worry - there will be plenty of time to customize our CSS later.

Delete the `.red-text`, `p`, and `.smaller-image` CSS declarations from your `style` element so that the only declarations left in your `style` element are `h2` and `thick-green-border`.

Then delete the `p` element that contains a dead link. Then remove the `red-text` class from your `h2` element and replace it with the `text-primary` Bootstrap class.

Finally, remove the smaller-image class from your first img element and replace it with the img-responsive class.
```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  h2 {
    font-family: Lobster, Monospace;
  }
  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
</style>

<div class="container-fluid">
  <h2 class="text-primary text-center">CatPhotoApp</h2>

  

  <a href="#"><img class="thick-green-border img-responsive" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats love:</p>
  <ul>
    <li>cat nip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```

## Use a span to Target Inline Elements
You can use spans to create inline elements. Remember when we used the `btn-block` class to make the button fill the entire row?  

That illustrates the difference between an "inline" element and a "block" element.

By using the inline `span` element, you can put several elements on the same line, and even style different parts of the same line differently.

Using a `span` element, nest the word `love` inside the `p` element that currently has the text `Things cats love`. Then give the `span` the class `text-danger` to make the text red.
```html
<p>Things cats <span class="text-danger">love:</span></p>
```

## Create a Custom Heading
We will make a simple heading for our Cat Photo App by putting the title and relaxing cat image in the same row.

Remember, Bootstrap uses a responsive grid system, which makes it easy to put elements into rows and specify each element's relative width. Most of Bootstrap's classes can be applied to a `div` element.

Nest your first image and your `h2` element within a single `<div class="row">` element. Nest your `h2` element within a `<div class="col-xs-8">` and your image in a `<div class="col-xs-4">` so that they are on the same line.

Notice how the image is now just the right size to fit along the text?
```html
<div class="row">
    <div class="col-xs-8">
      <h2 class="text-primary text-center">CatPhotoApp</h2>
    </div>
    <div class="col-xs-4">
      <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
    </div>
  </div>
```

## Add Font Awesome Icons to our Buttons
