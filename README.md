# Example Design System Docs

> **Warning:**
> Under construction
> Not ready for production


Our Design System houses guidelines, reusable UI components, and other resources we use to create our apps and in-house websites. It is flexible and always evolving to serve the best experience for every situation.  

Using this system  help us make work more efficient, and our products more consistent, while still looking, feeling, and sounding uniquely you.

We adopt the Atomic Design visual design system, architect with ITCSS, and build with BEM and OOCSS techniques, using SCSS and PostCSS running on Webpack.




## Setup

### Framework

We are using Tailwind to create a usable framework: http://tailwindcss.com/

It gives us a set of utility classes right from the start than can help with faster setup, testing and building components, and intuitively include responsive modifiers.

We rely heavily on SCSS for mixins, variables, nesting (when required) and use PostCSS for autoprefixing. The latter is important because one less thing to worry about.

All our css will imported in the `main.scss` file.

## Design

### Arquitecture

Our CSS arquitecture is based on ITCSS: https://itcss.io/

The importance of ITCSS is that it helps with large scale CSS projects, and will help prevent major rewrites down the line and an easier starting point for new contributors and new projects.

You can read in-depth here: https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/

On each folder you will find more information on the CSS that belong there.

### Style Guide

Our naming convention is based on BEM:

```
.block__element-name--modifier
```

Let take for example a simple list of users. We would have our HTML markup:

```
<ul class="user-group">
    <li class="user-group__item">
    <li class="user-group__item">
    <li class="user-group__item">
</ul>
```

And our CSS:

```
.user-group {
    list-style: none;
    display: flex;
    flex-direction: column;
}

.user-group__item {
    display: block;
    padding: 10px;
}
```

Now lets say instead of a list, you want a row. You can add to your `.user-group` a new class called `.user-group—-row` and add some modifying CSS:

```
.user-group--row{
    flex-flow: row nowrap;
}
```



Most higher-order components like feeds have the following markup:

```
<div class="feed">
	<div class="feed__title"></div>
	<div class="feed__content">
		<div class="card feed__item"></div>
		<div class="card feed__item"></div>
		<div class="card feed__item"></div>
		<div class="card feed__item"></div>
	</div>
</div>
```



#### Containers and Wrappers


Containers are used for content on your site in  setting a maximum width and centering on the page.

```
  <div class="container md:container--narrow">
    Some content...
  </div>
```

```
.container {
    max-width: 1200px;
    margin: 0 auto;
}

.container--narrow {
    max-width: 900px;
}
```

Wrappers are used to encapsule components in cases where more advanced positioning is needed (e.g. dropdowns).

```
.dropdown__wrapper {
    display: table;
    position: absolute;
}

.dropdown {
    display: fixed;
}
```



It's important to define when an element's class belongs to a higher order block or if you need a modifier. Remember the idea is to create as many reusable code as possible, so take into account how much styling will be repeated and which one is exclusive to the context.



## Inquiries

You can help me improve the system and ensure it remains current and relevant.  

- Any questions, let me know at:  juanscv92@gmail.com

- You can file a new issue if we are missing components or our advice isn’t clear and actionable.
