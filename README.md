# BOOTSTRAP BASICS

## Objectives

By the end of this lesson, developers should be able to:

- Create mobile-first, responsive site layouts using
  [Bootstrap](http://getbootstrap.com).
- Reference Bootstrap documentation.
- Add Bootstrap components to front end projects.
- Use Bootstrap themes, add-ons, and templates for further customization

## Preparation

1. Fork and clone this repository
2. Open a web browser window to [Get Bootstrap](http://getbootstrap.com)
3. Look over the included starter `index.html` file.

## Getting started with Bootstrap

Bootstrap is a free and open-source CSS framework with optional JavaScript components. Originally developed by Twitter as a framework to encourage consistency across internal tools, Bootstrap evolved into "the world’s most popular framework for building responsive, mobile-first sites." If the general appearance and blue shades seemed familiar, now you know why!

To get started with Bootstrap, first go to [Get Bootstrap](http://getbootstrap.com) and click Get Started!

### Quick Start

The fastest way to include Bootstrap and its components in your project is to use the CDN Link provided on the website.

Copy and paste this `<link>` tag into your `<head>` before all other stylesheets to load our css.

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-uWxY/CJNBR+1zjPWmfnSnVxwRheevXITnMqoEIeG1LJrdI0GlVs/9cVSyPYXdcSF" crossorigin="anonymous">
```

Many Bootstrap components require JavaScript to render and animate themselves properly. Previous versions of Bootstrap before Bootstrap v.5.0 used relied on jQuery. In this lesson, we're using Bootstrap 5, the latest version as of writing. This script tag bundles all JavaScript dependencies together and can be placed near the end of the of the closing `<body>` tag.

```
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-kQtW33rZJAHjgefvhyyzcGF3C5TFyBQBA13V1RKPf4uH+bwyzQxZ6CmMZHmNBEfJ" crossorigin="anonymous"></script>
```

Now, open up this repo's `index.html` file. Look how the H1 is styled. Uncomment the Bootstrap CDN link tag, and now see what changes!

Bootstap applies default styles to most built-in HTML tags, but it also uses several class-based styles to give it that signature Bootstrap look. Let's check out the Bootstrap layout system first!

## Bootstrap Layout System

### Containing Divs

![Bootstrap Grid Example](https://media.git.generalassemb.ly/user/16103/files/96713700-03a5-11e9-8eb8-9323ad08acbf)

Bootstrap uses Flexbox and Grid underneath the hood to create its own 12-column layout system. Remember: **the magic number in Bootstrap Layouts is 12**.

To begin using Bootstrap's layout system, we first need a `div` with a class of `container`. Inside this div, we also need a div with a class of `row`.

```
<div class="container">
    <div class="row">
    </div>
</div>
```

These two nested divs act as the containing elements. Now, let's bring in one of the components for Bootstrap to demonstrate how the layout system can be used to arrange elements easily.

You can bring in Bootstrap Components into your project by selecting what you need from the sidebar. Cards are a common UX component on many websites with helpful information. Let's use Bootstrap's version of a Card to demonstrate Bootstrap Layout.

Here is a Bootstrap Card:

```
<div class="card">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
```

Copy and paste two of these card elements INSIDE the `div` with class `row` we made earlier.

So, inside your `body` tag, your HTML should look like this:

```
 <div class="container">
      <div class="row">
        <div class="card col-md-6">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
            <p class="card-text">
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </p>
            <a href="#" class="card-link">Card link</a>
            <a href="#" class="card-link">Another link</a>
          </div>
        </div>
        <div class="card col-md-6">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
              <p class="card-text">
                Some quick example text to build on the card title and make up the
                bulk of the card's content.
              </p>
              <a href="#" class="card-link">Card link</a>
              <a href="#" class="card-link">Another link</a>
            </div>
          </div>
      </div>
    </div>
```
Great! Now, let's arrange these cards and make them mobile-friendly too!

### Columns and Built-In Breakpoints

Remember how we emphasized that 12 is the magic number? The number of columns across the containg divs should always add up to 12.

In general, to determine how many columns a Bootstrap component should cover, we use a class name like this:

```
col-SIZE-NUMBER
```

For size, we can use these built-in breakpoints:
- SM
- MD
- LG

And for number, any number from 1-12 will work.

An element can also contain multiple column classes to change its appearance between different screen sizes.

For example a `div` with both `col-md-6` and `col-sm-3` will take up 6 columns on medium-sized screens and up, but will take up 3 columns across on small-sized screens and smaller.

Add `col-md-6` to both Card elements inside of their opening `div` tags. Notice how their layout is effected.

YOU DO: Add a third card, and change the COL-MD-* class to have three cards across.

## Components that use JavaScript

Many complicated Bootstrap components rely on JavaScript because they are animated. One prominent example that you can find everywhere on the Internet is the infamous hamburger menu on sliding mobile navbars.

You can bring in a navbar from Bootstrap's component library like this. Notice the many nested divs and bootstrap classes on several elements.

```
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <a class="nav-link active" aria-current="page" href="#">Home</a>
        <a class="nav-link" href="#">Features</a>
        <a class="nav-link" href="#">Pricing</a>
        <a class="nav-link disabled">Disabled</a>
      </div>
    </div>
  </div>
</nav>
```

A common mistake is to bring in this Navbar without connecting to Bootstrap's JS dependencies. Additionally, the Hamburger Icon will only show up on mobile views and will be hidden on larger screen sizes. With complex Bootstrap components, you should read documentation how to customize elements properly.

## Overwriting Bootstrap Default Styles

With our own CSS Styles, we override default Bootstrap styles if want a more customized look.

As an example, let's bring in a form with several buttons.

```
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

Notice the classes on the buttons are `btn` and `btn-primary`.

Now, we can open our style.css file and write a new color we want for `.btn-primary,` which is the color most buttons will take.

```
.btn-primary {
    background-color: WHATEVER YOU WANT :)
}
```

Here are some popular button customizations that many people use with bootstrap:

Sharp Corners:
```
.btn {
    border-radius: 0
}
```

Pill Shape:
```
.btn {
    border-radius: 50px
}
```

## Using Layouts from StartBootstrap.com 

If you're curious about different ways you can use Bootstrap to quickly make several popular web page layouts, you can use [Start Bootstrap](https://startbootstrap.com/snippets) to find helpful Bootstrap Snippets. Beware of their portfolio templates! They're quite cliche lately! Otherwise, this is a great resource for getting inspiration and helpful hacks!


## The Bootstrap Default Look

Once you start using Bootstrap, you might start to notice how prevalent it is on the Internet. In fact, it is an inside joke of how common this look is on Start-up and Corporate Websites: https://www.dagusa.com/

In addition to using your own CSS, several devs have published Bootstrap Themes that overlay on top of Bootstrap's default styles to give a more customized look. 

When you look for Bootstrap Themes, make sure it is compatible with the version of Bootstrap you are using! As of writing, most themes are for Bootstrap V. 4!

One such site is Creative Tim: https://creative-tim.com


## Follow Up

Learn Bootstrap 4 in 30 minutes by FreeCodeCamp
https://www.freecodecamp.org/news/learn-bootstrap-4-in-30-minute-by-building-a-landing-page-website-guide-for-beginners-f64e03833f33/
