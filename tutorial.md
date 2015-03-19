# Using Bootstrap for the First Time

## Setting It Up

It's pretty easy to get Bootstrap set up with normal HTML files, so I've done it for you in order to save time. If you want to do it yourself go to getbootstrap.com and choose 'Download Boostrap.' Once you understand it better you'll probably be going to the 'Customize' section of the website, but to start you'll want all of the files, which are included in this starter repo.

On the front page they have the boiler plate HTML you'll need to get started, which I've included in the index.html file. This index page is already linked to the Bootstrap css/fonts/js. In this repo I"ve also added some content populated with cat ipsum so we have something to work with.

## Start Using Bootstrap

In your terminal write:

<pre><code> open index.html </pre></code>

This will open up the page in your browser.

It looks pretty sad at the moment, no space to breathe around the edges. Fortunately Bootstrap has a solution.

<pre><code>
  <div class="container">
</pre></code>

The container class will create padding around all of the elements. It also instantiates the use of the grid system, which is one of the most important elements of Bootstrap, so don't forget to leave this part ever.

Bootstrap does have two different options:

<pre><code>
<div class="container">
<div class="container-fluid">
</pre></code>
