# Using Bootstrap for the First Time

## Setting It Up

It's pretty easy to get Bootstrap set up with normal HTML files, so I've done it for you in order to save time. If you want to do it yourself go to getbootstrap.com and choose 'Download Boostrap.' Once you understand it better you'll probably be going to the 'Customize' section of the website, but to start you'll want all of the files, which are included in this starter repo.

On the front page they have the boiler plate HTML you'll need to get started, which I've included in the index.html file. This index page is already linked to the Bootstrap css/fonts/js. In this repo I"ve also added some content populated with cat ipsum so we have something to work with.

## Start Using Bootstrap

In your terminal write:

<p><code> open index.html </p></code>

This will open up the page in your browser.

It looks pretty sad at the moment, no space to breathe around the edges. Fortunately Bootstrap has a solution.

<p><code>
\<div class="container"\>
</p></code>

The container class will create padding around all of the elements. It also instantiates the use of the grid system, which is one of the most important elements of Bootstrap, so don't forget to leave this part ever.

Bootstrap does have two different options:

<p><code>
\<div class="container"\><br>
\<div class="container-fluid"\>
</p></code>

The "container" class has a max width where it will quit expanding and blank space will fill around it. This is usually the best choice, because things start to look wonky when they get too spread out. "Container-fluid" does not have a max-width. It will get as wide as the screen it is on.

So let's put in the container class below the body and before the nav and see how it does:

<p><code>
\<body\>
  \<div class="container"\><br>
    \<nav\>
</p></code>

Don't forget to close it. You can do this before the Javascript links:

    \</p\>
  \</div\>
\<!-- jQuery (necessary for Bootstrap's JavaScript plugins) --\>
\<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script\>

