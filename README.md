# UI Methods
Sometimes, is easier to apply best practices if we have a method to do so. This document will try to consolidate a set of development methods to create web applications with many of the best practices recommended by the community.

## Why?
The [Merrian-Webster dictionary](http://beta.merriam-webster.com/dictionary/method) defines a method as *"a way, technique, or process of or for doing something"*. There are many activities that can be performed with a more predictable quality if we follow a method. For instance, is easier to understand the various metrics yielded by a profiler if we have a method or model to analize the data. Methods, and models provide us with principles and procedures to carry on tasks, and those principles and procedures are based on sound best practices. 

The following sections will provide links and a little bit of information for each of the methods I know for frontend development.

## Accessibility

### HIKE
*What is HIKE?*

HIKE is an acronym to help you remember some basic principles of web accessibility:

**H** stands for headings and semantic markup.

**I** stands for images and labels.

**K** stands for keyboard navigation.

**E** asks for you to ACT with a little extra love for custom components and more. 
http://accessibility.parseapp.com/#1

## Style Guides

### Atomic Design [http://patternlab.io/about.html](http://patternlab.io/about.html)
*Atomic design is a methodology composed of five distinct stages working together to create deliberate interface design systems.* ([http://atomicdesign.bradfrost.com/chapter-2/](http://atomicdesign.bradfrost.com/chapter-2/)).

* **Atoms**: are the basic building blocks of matter. Like HTML tags, such as a form label, an input or a button.
* **Molecules**: are groups of atoms bonded together and are the smallest fundamental units of a compound. These molecules take on their own properties and serve as the backbone of our design systems.
* **Organisms**: are groups of molecules joined together to form a relatively complex, distinct section of an interface.
* **Templates**: at the template stage, we break our chemistry analogy to get into language that makes more sense to our clients and our final output. Provide context!
* **Pages**: are template instances.

## CSS Organization
Move away from monolithic CSS files. The goal of this section is to provide methods to modularise the CSS into multiple files, making it more mainteinable and reusable. The key is to identify you UI components, as suggested in the Style Guide section, and enforce their implementation in CSS following one or more of the methods.

### BEM [http://getbem.com](http://getbem.com)
BEM main strength is to provide a common ground for naming CSS classes. Using proper naming will prepare you for the changes in design of the website. BEM is abbreviation of the key elements of the methodology — *Block*, *Element* and *Modifier*.

* **Block**: encapsulates a standalone entity that is meaningful on its own. While blocks can be nested and interact with each other, semantically they remain equal; there is no precedence or hierarchy. Holistic entities without DOM representation (such as controllers or models) can be blocks as well. Block names may consist of Latin letters, digits, and dashes. To form a CSS class, add a short prefix for namespacing: .block
* **Element**: parts of a block and have no standalone meaning. Any element is semantically tied to its block. Element names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block name plus two underscores plus element name: .block__elem
* **Modifier**: flags on blocks or elements. Use them to change appearance, behavior or state. Modifier names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block’s or element’s name plus two dashes: .block--mod or .block__mod--mod and .block--color-black with .block--color-red. Spaces in complicated modifiers are replaced by dash.

### OOCSS [https://github.com/stubbornella/oocss/wiki](https://github.com/stubbornella/oocss/wiki)
OOCSS intents to bring Object-Oriented principles to CSS development. Basically, a CSS “object” is a repeating visual pattern, that can be abstracted into an independent snippet of HTML, CSS, and possibly JavaScript. That object can then be reused throughout a site.

There are two main principles of OOCSS:
* **Separate structure and skin**: this means to define repeating visual features (like background and border styles) as separate “skins” that you can mix-and-match with your various objects to achieve a large amount of visual variety without much code. Separating structure and skin can also mean using classes to name your objects and their components, rather than relying solely on the semantics of HTML. For example, the media object is named with ```class="media"```, and its components are named with ```class="img"``` (for the image/video component) and ```class="bd"``` (for the body/text component). By referencing these classes in your stylesheets (say, rather than directly styling the ```<img>``` element), your HTML can be flexible. For instance, if a new media element were to take off in the next few years (e.g. ```<svg>```), it could be integrated into the HTML without having to touch the CSS.
* **Separate container and content**: this means “rarely use location-dependent styles”. An object should look the same no matter where you put it. So instead of styling a specific ```<h2>``` with ```.myObject h2 {...}```, create and apply a class that describes the ```<h2>``` in question, like ```<h2 class="category">```. This gives you the assurance that: (1) all unclassed ```<h2>s``` will look the same; (2) all elements with the category class (called a mixin) will look the same; and 3) you won’t need to create an override style for the case when you actually do want ```.myObject h2``` to look like the normal ```<h2>```.

### SMACSS [https://smacss.com/](https://smacss.com/)
At the very core of SMACSS is categorization. By categorizing CSS rules, we begin to see patterns and can define better practices around each of these patterns. Much of the purpose of categorizing things is to codify patterns—things that repeat themselves within our design. Repetition results in less code, easier maintenance, and greater consistency in the user experience. These are all wins. Exceptions to the rule can be advantageous but they should be justified.

There are five types of categories:

* **Base**: base rules are the defaults. They are almost exclusively single element selectors but it could include attribute selectors, pseudo-class selectors, child selectors or sibling selectors. Essentially, a base style says that wherever this element is on the page, it should look like this.
* **Layout**: layout rules divide the page into sections. Layouts hold one or more modules together.
* **Module**: are the reusable, modular parts of our design. They are the callouts, the sidebar sections, the product lists and so on.
* **State**: state rules are ways to describe how our modules or layouts will look when in a particular state. Is it hidden or expanded? Is it active or inactive? They are about describing how a module or layout looks on screens that are smaller or bigger. They are also about describing how a module might look in different views like the home page or the inside page.
* **Theme**: theme rules are similar to state rules in that they describe how modules or layouts might look. Most sites don’t require a layer of theming but it is good to be aware of it.

### SUIT CSS
http://suitcss.github.io/

## Web Performance

### RAIL
http://www.smashingmagazine.com/2015/10/rail-user-centric-model-performance/
https://aerotwist.com/blog/bigrig/

### FLIP
https://aerotwist.com/blog/flip-your-animations/
