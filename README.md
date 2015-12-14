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

### OOCSS
https://github.com/stubbornella/oocss
http://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/

### SMACSS
https://smacss.com/

### SUIT CSS
http://suitcss.github.io/

## Web Performance

### RAIL
http://www.smashingmagazine.com/2015/10/rail-user-centric-model-performance/
https://aerotwist.com/blog/bigrig/

### FLIP
https://aerotwist.com/blog/flip-your-animations/
