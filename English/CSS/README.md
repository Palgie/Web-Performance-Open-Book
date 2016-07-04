CSS
=========================

## Architecture Matters

CSS is a big consideration for building and a quick and light CSS file for your website or application. Architecture is fundamental to how you and your development team manage and update the CSS. Not only for the first phases of your development project but a continued maintenance. This is a very common thing to overlook that too often results in an incompressible monster of a CSS file after only a few months of continued development.

The file size of your CSS file is of higher priority to other files due to the render engine priority of the browser. A CSS file typically falls into the critical render path as the page will not download until all blocking `.css` files are downloaded. Because of this there are many considerations for every aspect of the CSS, which aren't always based on execution times.

## CSS Modules

One reason for the rise in popularity in CSS modules (regardless of being in any formal spec) is that CSS has what some consider to be scalability problems and while contentious, there are a number of benefits to housing all your creations into their own neat boxes.

1. Namespace clarity
2. Local scope
3. Feature relationship and deferring load

Are a few that you should care about when it comes to performance.

#### Namespace clarity

When your fellow developers are thinking about naming their CSS it's very common for them to overlook or just ignore the question of _how will this work in a year?_, _will another developer also want to use this namespace?_ or _is this reusable_. Couple this with the problem of us being humans and forgetting or just not reading a *something thousand* line CSS file and you're in the same problem a lot of developers are in. This is why BEM and other exist, containment and clarity.

How does this relate to performance? Well, adding line after line without understanding the relationships between the CSS and the DOM or CSS and the JS results in bloat. It will often have you or other developers chasing their tails trying to make the CSS smaller all the time.

So see CSS modules not as a small line in the sand around your code, it's a wall with a big sign.

If done right this allows you and everyone else to understand what CSS relates to what feature or what patterns.

## Local scope

CSS is an open book, you write one class `.foo` and another `.foo` will inherit it's previous styles. While this has little to do with performance, the understanding of your codebase does. Namespace for specific features rather than your entire website adds significant clarity. Clarity that allows you to delete, rewrite and refactor with transparency between different team members.

Allowing you to write like this:

**feature.css**
```css
.title {}
.description {}
```

Not like this:

**website.css**
```css
.login-overlay .register .title {}
.login-overlay .register .description {}
```

## Feature relationship and deferring load

Understanding what CSS is impacting what area of your website or application, as simple as it sounds is very powerful. Aside from separation and clarity, we should never hope to ask your users to download styles (in the critical render path) from features that aren't visible or in use.

CSS Modules will allow you to situationally and sensibly spread the load across different features, pages or situations when and where it's needed, making your page visible faster and users less frustrated.

## Pre-processor Pitfalls

SASS, LESS, Stylus and others while seemingly efficient at adding some power to CSS, responsibility follows. While the use of shared constants, behind the scene modularity and the promotion of reusability. Working on a large application in a large team without aggressive architecture or maintenance doesn't help prevent code bloating, the more you turn CSS into a logical language the easier it is to make mistakes.

While pre-processing can be a viable options to help your team. Be aware that scope leaks, ignorance of final output, lengthy books of selectors or aggressive looping isn't uncommon.

Don't make the mistake of choosing only to make you and your developers lives easier at the expense of your users.

Here are some examples of things to be careful of:

### Bad Nesting

**Input**

```css

.module-container {
  background-color: red;

  .module-sub-container {
    background-color: yellow;

    .feature1 {
      background-color: orange;

      .feature2-container {
        background-color: white;

        span {
          background-color: green;
        }
      }
      .feature3 {
        background-color: transparent;

        &.option1 {
          background-color: blue;

          .option2 {
            background-color: purple;
          }
        }
        .option3 {
          background-color: black;
        }
      }
    }
  }
}
```

**Output**

```css

.module-container {
  background-color: red;
}
.module-container .module-sub-container {
  background-color: yellow;
}
.module-container .module-sub-container .feature1 {
  background-color: orange;
}
.module-container .module-sub-container .feature1 .feature2-container {
  background-color: white;
}
.module-container .module-sub-container .feature1 .feature2-container span {
  background-color: green;
}
.module-container .module-sub-container .feature1 .feature3 {
  background-color: transparent;
}
.module-container .module-sub-container .feature1 .feature3.option1 {
  background-color: blue;
}
.module-container .module-sub-container .feature1 .feature3.option1 .option2 {
  background-color: purple;
}
.module-container .module-sub-container .feature1 .feature3 .option3 {
  background-color: black;
}
```

## Beware frameworks

Coming Soon

## CSS expressions

Coming Soon

## Animating for Speed

Coming Soon

## Reduce Imports

Coming Soon
