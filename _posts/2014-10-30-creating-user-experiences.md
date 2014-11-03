#### The need for new thinking by developers
* The need for new thinking by developers
  * "as our case is new, so we must think anew and act anew"
  * "For the history of software, it's been good enough to make things possible. Now success also depends on making things easy."
  * design is more than just a pretty face
* Stuck in a rut
  * no longer the tech that holds us back
  * for some systems it is not worth it
  * payoff can be huge
    * higher productivity
    * lower training
    * few errors
    * more satisfied users
  * book: "out of our minds" by Ken Robinson
* Evolution as a useful mental model
  * ecosystem changing requires changes to survive
  * designing user interfaces hasn't been a requirement in the .NET ecosystem
* Example to learn from: the music industry
  * ipod
  * music industry got too comfortable and things changed
* StaffLynx as an example
  * business apps have come a long way from terminal based to web based
* Preparing for the new ecosystem
  * principles are learnable and fundamental
  * pattern matching
* A test of awareness and observation
  * moonwalking bear!
  * _inattentional blindness_
    * you won't see what you're not looking for
    * your area of focus is tiny, size of a quarter at arms length
    * book: _Universal Principles of Design_ (Lidwell, Holden, Butler)

#### Design principles for choosing options
Looking at some objects in the real world to learn about design and applying those things to our designs. We need to understand why the objects are good or bad. Lets look at things with the "designers eye"

* What's wrong with this elevator?
  * observations: buttons and description seperate, increase left to right
  * didn't notice there is no 13th floor
  * alignment is a little bit off
  * worn off paint shows people confuse the buttons with the description
  * buttons are round in real life -> archetypes
    * certain objects and actions have a universal or near-universal form or theme
* The Gestalt principle of proximity
  * things that are grouped spatially are associated together
  * not grouping makes it difficult to figure out without greater context
  * button should be close to placard, placard and buttons should be different shapes
* Some important design principles for choosing options
  * Fitt's law.
    * the amount of time required to locate and use an option is smaller if the option is bigger
  * on the elevator the most often visited places are larger and more prominent
  * Pareto Principle (80/20) -> likely that 4 or 5 of the buttons are used for 80% of user actions
  * Hick's law -> the time required to locate and use an option increases as the number of options increases.
* Hick's Law and its consequences
   * every time you add an option, it decreases the value of the other options
   * can violate if you expect users to be highly trained and use the app a lot
   * long lists and trees are commonplace, devs don't think about the usability
   * most often they just add it to an existing list
* Alternatives to ridiculously long lists of options
  * remove all but the 20% most used features
  * or shrink the less common ones
  * standard area and an advanced area
  * make the most prominent be bigger
  * design principles don't tell you exactly what to do, just guides.
* Users outnumber developers, plus summary and next steps
  * users expect more from their software
  * real world objects are good examples of good and bad design

#### Visual Scanning and Processing
human visual system is tuned to certain shapes etc.
  * tuned to detect edges
  * start to make sense in 1/4 second
    * shapes and groups
  * experience used to interpret the output of stage 2
  * we're mostly concerned with the second stage
* The Gestalt principles of proximity and similarity
  * do you see rows or columns? depends on spacing and proximity
  * easy to mix up rows or columns of buttons
  * objects that are similar are considered to be related and that overrides proximity
    * color, shape or size (size does not work as well)
* More grouping gestalt principles
  * similarity to show relations
  * grouping to show relations
  * violating similarity can cause something to stand out (highlight)
  * Common fate:
    * involves movement
    * items that move together are assumed to be connected
  * continuity and closure:
    * visual system will fill in gaps automatically
    * spaces are filled in
  * Gestalt closure, continuity, and figure/ground
    * a slider is perceived as a single line with the slider sat on top o it
    * fading text implies more text
    * a path that dissapears we expect to continue outside our vision
    * figure/ground
      * some part of what you see is supposed to be important
      * your visual system tries to calculate out what the "figure" is vs what is the background
      * visual system uses some queues to do this
      * overlays, greying and shrinking can help focus user, switch what the figure is
* Gestalt principles in remote controls, plus more on inattentional blindness
  * remote controls a good place for Gestalt
  * need to match up what the user is focussing on and what the software is promoting, a mismatch causes inatentional blindness
* Gutenberg diagram, and summary
  * eye tends to scan upper left to lower right with less attention to the upper right and lower left areas

#### Preference for Naturalness
When people see natural things they tend to feel less stressed.
* Savannah preference and whitespace
  * Biophilia -> preference for green growing things
  * Savannah preference -> preference for openness, openness means safety and lack of threats
  * layouts on a computer screen makes a user more comfortable and less stressed if that are more open and not too crowded.
  * scrolling preferred to less whitespace
  * first preference should be for more whitespace
* Crowded screens and horror vacui
  * whitespace reduces cognitive load
  * prefer whitespace over boxes
  * Horror vacui -> fear of empty spaces. Clutter implies low quality and cheap. Example being shop windows
* No matter what you've heard, screen real estate isn't that valuable
  * sometimes crowded interfaces required, but rarely
  * user can only see a little bit of the screen clearly
  * find capability, metrics to work out what's important
  * users worried that we'll hide something they need
  * multiple views for different roles, please everybody without overloaded UI
* Infinite whitespace - demonstrating the viewport pattern
  * zoom out, semantic zoom
  * explore new navigation patterns
* An exercise on crowded screens
* Using color and gradients to promote naturalness
  * natural world there is almost no monochrome
  * gradients used to be more natural, simulate light
  * in the natural world, light comes from overhead almost all the time. As a result, in gradients using the same color family, the lighter color should generally be on top
  * faces lit from the bottom look creepy!
  * can use the inverse for highlight, but top-down should be default
  * kuler.adobe.com, www.colorschemer.com/schemes to get colours for gradient

#### Preference for Naturalness, part 2
humans prefer curved lines, edges infer sharp, danger etc.
* Contour bias and desire lines
  * curved paths
  * desire lines: paths spontaneously created by users that take a natural route between objectives
    * worthy goal to allow your users to construct their own desire lines through your software
  * rounded corners, rounded buttons, despite rectangular basis
* overuse of rectangular design and how to avoid it
  * too many devs stuck in dividing the screen into rectangles
  * look to video games for some inspiration, use contour bias
* using animation to promote naturalness
  * now easy to do
  * like gradients, should be used when natural
  * we're not used to things "blinking" into existence, small animation can help
  * fade in, fade out items, grow slowly from small to big
* animation examples in StaffLynx
  * screens slide in and out, the screen is not lost
  * foreground animates, background shrinks
  * animations lose value over time, reasonable to allow the user to turn them off
* 3d appearance - reasons and techniques
  * drop shadow, layering on top for grouping
  * reflections
  * perspective and texture gradients
  * greying out

#### Aesthetics and Legibility
Aesthetics important but not when underinvesting in usability

* Attractiveness bias
  * pretty but confusing is not successful
  * we are drawn to beautiful or attractive things, smooth colours, first impressions formed in less than five seconds
  * pretty things get second chances, the benefit of the doubt
* The Aesthetic-Usability Effect, advice on typefaces
  * users believe that beautiful software is more usable
  * don't sweat typefaces
  * keep number of sizes used to 3 or 4
  * proportionally spaced typefaces are preferred
* Legibility and Contrast
  * good contrast, not necessarily completely black. Maybe 90%
  * right aligned for labels -> reduces boxiness
* A bit more about fonts
  * not too important for business apps, maybe more so for games or commercial sites where you want a certain mood

#### Managing Cognitive Load
Reduce the amount of thought required for the user to get things done.
People can only manage a limited amount of information at a time, we need to keep the information presented them to a minimum,
just what they need at that moment
* Recognition over recall and progressive disclosure
  * users faster at recognizing the option they need instead of having to memorize option and inputs for each
  * context menus and shortcut keys are advanced options for fast access
  * progressive disclosure, control and manage the number of options the user needs to see at once
    * reveal details in layers
    * make sub menu items different, but similar to each other
    * item, hover, then enter record
* New UI for progressive disclosure, plus highlighting and the mapping principle
  * New UI stacks enable tooltips, trees etc to contain whatever we want
  * manipulating colours, highlighting by color, underline, size etc. fade for inactive etc.
* Mapping continued, pls affordances
  * mapping knobs on a stove to the burners
  * corresponding the UI with the real world impact
  * up button and down button are above and below each other, not next to each other
  * affordances
    * signals to the user about the right way to do things
* Affordances continued, plus constraints
  * scissors
  * drag handles on UI
  * entry points, "Click here to begin"
  * constraint
    * When an action is not appropriate, prevent the user from doing it, provide a visual signal that the action is not available
    * getting the logic here correct is important, very frustrated to get stuck from continuing
* Feedback, confirmation, and forgiveness
  * feedback needs to be kept close to the thing it is referring to
  * an irreversable action requires confirmation, asking too much reduces to value, reserve it
  * forgiveness -> undo
  * don't always need confirmation, accept and submit (holding area-> can be reclaimed within 30 seconds)
