# Steps for Updating the SLab Slide Deck

1. Add a slide to \_includes/slides/

Each slide exists in its own file. To add a new slide, you make a new.html file in that folder. It's often easiest to just duplicate the file entirely, rename it, and then modify both the text of the file and the css selectors at the top. This is an example of a typical slide file:

```
<section class="slide skriker" id="skriker">
  <h1>Digital Skriker</h1>
  <p>Kelli Shermeyer’s project uses motion capture and virtual reality technologies to explore Caryl Churchill’s <i>The Skriker</i> (1994). She is interested not only in how these technologies might change the way we think about documenting stage movement and gesture, but also how they may enable new modes of performance, using “digital” space and nonhuman actors as part of an immersive and/or site-specific theatre practice.
</p>
</section>

```

To review, the things you would change upon copying this to a new file are the following - 

* The class and id names within the section tag (in this example, they are the word 'skriker'). You should select something meaningful for your slide. Note that if you want to just copy the color and background from another slide you can use whatever class and id names are associated with that file. So if you wanted to use the backgrounds from the GIS slides, you would insert "gis" instead of "skriker".
* The title between the h1 tags.
* The description between the p tags.

2. Make sure it has the style you want

You can do this in one of two ways -

* One option - copy the color and background from another slide you can use whatever class and id names are associated with that file. So if you wanted to use the backgrounds from the GIS slides, you would insert "gis" instead of "skriker".

* Second option (slightly more complicated) - in \_sass/style.css, add a new section to the CSS. You can do this by copying an old, which looks like this - 

```
.skriker {
    @include background-image(
        linear-gradient(top, rgba(black, 0.8), rgba(black, 0.8)),
        url('/images/skriker.png')
    );
}
```

You would want to change three pieces -

* .skriker should become .youruniqueclass - after the named class you gave your slide.
* linear-gradient(top, rgba(black, 0.8), rgba(black, 0.8)), - can either stay the same or be changed depending on what color you want.
* url('/images/skriker.png') becomes url('/images/your-image-name.png')


3. If you're planning to add a new background image, add it to the /images folder.

4. Make sure the slide you want is included in index.html. You do this by adding an include statement like these - 

'''
{% include slides/digital-skriker.html %}

{% include slides/takeback.html %}
'''

Though the filename would need to change to whatever the name of your new slide file is. To take a slide out, you can delete an include line.

5. Take the keyboard to the hallway and refresh the slides.