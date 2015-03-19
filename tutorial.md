# Using Bootstrap for the First Time

## Setting It Up

It's pretty easy to get Bootstrap set up with normal HTML files, so I've done it for you in order to save time. If you want to do it yourself go to getbootstrap.com and choose 'Download Boostrap.' Once you understand it better you'll probably be going to the 'Customize' section of the website, but to start you'll want all of the files, which are included in this starter repo.

On the front page they have the boiler plate HTML you'll need to get started, which I've included in the index.html file. This index page is already linked to the Bootstrap css/fonts/js. In this repo I"ve also added some content populated with cat ipsum so we have something to work with.

## Start Using Bootstrap

In your terminal write:

```
open index.html
```

This will open up the page in your browser. You can tell that bootstrap is connected if the text shows up in a sans-serif font.

It looks pretty sad at the moment, no space to breathe around the edges. Fortunately Bootstrap has a solution.

```
<div class="container">
```

The container class will create padding around all of the elements. It also instantiates the use of the grid system, which is one of the most important elements of Bootstrap, so don't forget to leave this part ever.

Bootstrap does have two different options:

```
<div class="container">
<div class="container-fluid">
```

The "container" class has a max width where it will quit expanding and blank space will fill around it. This is usually the best choice, because things start to look wonky when they get too spread out. "container-fluid" does not have a max-width. It will get as wide as the screen it is on.

So let's put in the container class after the nav and before the content and see how it does:

```
  </nav>
<div class="container">
  <h1>Hello, Cats!</h1>
```

Don't forget to close it. You can do this before the Javascript links:

```
    </p>
  </div>
<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
```

Refresh your index.html. It already looks better!

Let's do something about the navigation. At the moment it is just an unordered list int he HTML. Bootstrap has a lot of default nav classes. If you want to find out about different styles, you can always go to the docs, they're pretty thorough.


(If you're curious what the "role" tags are for, and later "aria", they help visually-impaired people navigate your website.)

So here is what the initial code will look like. What is all of it doing?

```
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <ul class="nav navbar-nav">
      <li role="presentation">Home</li>
      <li role="presentation">Cats</li>
      <li role="presentation">Kittens</li>
      <li role="presentation">Tigers</li>
      <li role="presentation">String</li>
    </ul>
  </div>
</nav>
```
If you refresh your page it still looks pretty messy.

The Bootstrap classes "navbar" and "navbar-default" help style the nav across the top of the website. They have a few different styles besides default. Try playing around with some others.

Because it's not inside the "container" class for the body, we need to add padding to the navbar as well, so we do that with the "container-fluid." Because we want it to expand just as large as the rest of the page, we use "container-fluid in this instance." If we put it inside the rest of the container, then there would be weird padding around it. Not what you expect in your navbar.

In the ul class, the "nav navbar-nav" horizontally aligns the list and hides those bullet points. Not bad, but not too pretty or functional yet.


