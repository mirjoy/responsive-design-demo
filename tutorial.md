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

## Adding Navigation

Let's do something about the navigation. At the moment it is just an unordered list int he HTML. Bootstrap has a lot of default nav classes. If you want to find out about different styles, you can always go to the docs, they're pretty thorough.

So here is what the initial code will look like. What is all of it doing?

```
<nav class="navbar navbar-default">
  <div class="container">
    <ul class="nav navbar-nav">
      <li>Home</li>
      <li>Cats</li>
      <li>Kittens</li>
      <li>Tigers</li>
      <li>String</li>
    </ul>
  </div>
</nav>
```
If you refresh your page it still looks pretty messy.

The Bootstrap classes "navbar" and "navbar-default" help style the nav across the top of the website. They have a few different styles besides default. Try playing around with some others.

Because it's not inside the "container" class for the body, we need to add padding to the navbar as well, so we do that with the "container".

In the \<ul\> class, the "nav navbar-nav" horizontally aligns the list and hides those bullet points. Not bad, but not too pretty or functional yet.

The reason all of the words are cramming together is because the CSS is looking for \<a\> tags. So let's add those in.

```
<ul class="nav navbar-nav">
  <li role="presentation"><a href="#">Home</a></li>
  <li role="presentation"><a href="#">Cats</a></li>
  <li role="presentation"><a href="#">Kittens</a></li>
  <li role="presentation"><a href="#">Tigers</a></li>
  <li role="presentation"><a href="#">String</a></li>
</ul>
```

It's starting to look pretty good now. I prefer to see my navigation on the right, so let's add some CSS for that. Bootstrap has a handy class, "navbar-right."

```
<ul class="nav navbar-nav navbar-right">
```

Try making the screen as small as possible. This is what people will see on mobile phones. More importantly, the nav is stuck to the top, so if they are on their phone they might not be able to see any content.

Bootstrap has some built in jQuery that will "toggle" the menu up and down. Let's add that in.

It's in this little snippet. Any time you see the prefix "data", that is a jQuery method. You don't have to know how it works for now, just what it's doing. 'data-toggle' allows you to hit that little corner on your phone that expands or collapses the navigation.

The 'data target' lets us know what the jQuery is targeting. We'll assign that in a second.

The class "navbar-header" lets Bootstrap style it.

The 'icon-bar' lines show up so you have something to touch on your mobile phone.

The tag "sr-only" tells people with screen readers what this HTML is doing.

```
<div class="container">
  <div class="navbar-header">
    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#collapse-my-navbar" aria-expanded="false" aria-controls="navbar">
      <span class="sr-only">Toggle navigation</span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
    </button>
    </div>
```
You might not see anything if your view is wide, but shrink your browser until it's small and you'll see the little icon in the right hand corner. If you click on it right now, nothing will happen. That's because we're missing one more lines of code.

We need to allow the existing nav to be accessed in the mobile view. Place the line below right above the \<ul\>.

```
<div id="navbar" class="collapse navbar-collapse" id="collapse-my-navbar">
  <ul class="nav navbar-nav navbar-right">
```
Try shrinking your browser! It should be working.

We don't want anyone to forget which website they are on, so let's add our website name to the top navbar in a way that will appear on all sizes. I can go right after the closing button tag.

```
    <span class="icon-bar"></span>
  </button>
<a class="navbar-brand" href="#">All About Cats</a>
```

It's looking like a real navbar now. We might want to change the color or style it later, but let's move on for now.

## The Bootstrap Grid

At the moment all of our text is just stacked in one column. Bootstrap's default styling is that of "mobile first", which means that however you enter things, first and foremost they'll work on a phone. If you want to get them to look good on other screens you'll have to add more CSS.

The opposing philosophy is "graceful degradation" where you design for a large screen and then break it down into pieces for the phone after the fact. Both are valid ideas, it depends who your audience is. If you are building an exercise app, you'll probably want it to be mobile first. If it's something to be used in business, you'll probably assume it will be used on a desktop. Either way, it should work on any screen.

Bootstrap has a built in grid system that is 12 columns wide. You can specify how many columns across you want a div to take up. If you want it split into 3 sections, 12 divided by 3 is 4, so you will tell each div to take up 4 columns.

The other component to the grid is telling it when it should go to the mobile view - as in, all one column.

The following code will tell your div to take up 4/12 columns and span the width of the screen when it gets to a small size.

```
<div class="col-sm-4">
```

The four widths from Bootstrap are:
  xs - phone
  sm - tablet
  md - your browser isn't full screen
  lg - your browser is full screen

Let's try adding this div around our first three paragraphs.

```
<div class="col-sm-4">
  <h3>Cats as Pets</h3>
  <p>
  Lick butt play time, rub face on everything climb leg roll on the floor purring your whiskers off. Chew on cable throwup on your pillow, and chase ball of string yet shake treat bag missing until dinner time stick butt in face. If it fits, i sits claws in your leg, meowing non stop for food claw drapes. Love to play with owner's hair tie chase laser. Loves cheeseburgers sit in box, lick arm hair yet nap all day. Find empty spot in cupboard and sleep all day jump off balcony, onto stranger's head so caticus cuteicus or find empty spot in cupboard and sleep all day. Spread kitty litter all over house poop on grasses, chase dog then run away. Sit by the fire chase imaginary bugs. I am the best jump off balcony, onto stranger's head yet flop over, stretch, so lick butt, so leave fur on owners clothes rub face on owner.
  </p>
</div>
<div class="col-sm-4">
  <h3>Cats as Prey</h3>
  <p>
  Hate dog find something else more interesting. Leave hair everywhere swat at dog, but stand in front of the computer screen has closed eyes but still sees you or then cats take over the world and intrigued by the shower hide from vacuum cleaner. Pelt around the house and up and down stairs chasing phantoms. Attack feet lick arm hair. Hide when guests come over inspect anything brought into the house chew on cable yet scamper climb leg. Attack feet intently sniff hand, or scratch the furniture stretch behind the couch, or then cats take over the world but spit up on light gray carpet instead of adjacent linoleum. Use lap as chair scratch leg; meow for can opener to feed me. Kick up litter all of a sudden cat goes crazy, yet stare at ceiling. Chase red laser dot hunt anything that moves. Shove bum in owner's face like camera lens throwup on your pillow knock over christmas tree make meme, make cute face for hack up furballs meow all night having their mate disturbing sleeping humans chew foot.
  </p>
</div>
<div class="col-sm-4">
  <h3>Cats as Vermin Control</h3>
  <p>
  Chase mice if it fits, i sits. Sweet beast chase dog then run away for i like big cats and i can not lie. Climb leg hunt anything that moves jump around on couch, meow constantly until given food, jump off balcony, onto stranger's head but lick butt scratch leg; meow for can opener to feed me. Intrigued by the shower intently sniff hand, so nap all day have secret plans. Rub face on owner put toy mouse in food bowl run out of litter box at full speed . Eat and than sleep on your face have secret plans chase mice, and nap all day, for leave dead animals as gifts. Who's the baby stand in front of the computer screen hack up furballs. Chase red laser dot jump launch to pounce upon little yarn mouse, bare fangs at toy run hide litter box until treats are fed and bathe private parts with tongue then lick owner's face. Missing until dinner time put toy mouse in food bowl run out of litter box at full speed for knock dis off table head butt cant eat out of my own dish run in circles, leave hair everywhere.
  </p>
</div>
```

It should appear in three nice columns. Try making your screen smaller, and watch them stack.
