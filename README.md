# Pasilobus Design System

> **Warning:**
> Under construction
> Not ready for production



Our Design System houses guidelines, reusable UI components, and other resources we use to create our apps and in-house websites. It is flexible and always evolving to serve the best experience for every situation.  

Using this system  help us make work more efficient, and our products more consistent, while still looking, feeling, and sounding uniquely Pasilobus.

You can help us improve the system and ensure it remains current and relevant.  



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



#### Containers

Containers are used to wrap content on your site in specific cases, like setting a max width and horizonally center. Depending on the use case, you can either use it as a block element or a modifier.

- You can use modifiers and Tailwind's responsive classes to set different classes.

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


- If the container has especial elements to style`.block__container`.

  ```
  .main__container {
      background: #e5e5e5;
      padding: 30px;
  }
  ```




It's important to define when an element's class belongs to a higher order block or if you need a modifier. Remember the idea is to create as many reusable code as possible, so take into account how much styling will be repeated and which one is exclusive to the context.



## Inquiries

Any questions, let us know at: support@pasilobus.com.

You can file a new issue if we are missing components or our advice isn’t clear and actionable.

Learn more about Pasilobus at our website https://www.pasilobus.com
