# Global Styles

The first thing we will do is create global styles. These are styles that apply site-wide. They should be added to the root component of your theme.

We'll change the font to be sans-serif throughout our site. To do this let's import the `<Global>` component and the `css` function from Frontity into our root component file.

{% hint style="info" %}
`<Global>` and `css`, as well as `styled` which we will look at in the next lesson, are exported by the Emotion library. Frontity integrates Emotion so that you can import these from Frontity.
{% endhint %}

```jsx
// File: /packages/my-first-theme/src/components/index.js

// ...
import { connect, Global, css } from "frontity"

const Root = ({ state }) => {
  const data = state.source.get(state.router.link)

  return (
    <>
      <Global
        styles={css`
          html {
            font-family: system-ui, Verdana, Arial, sans-serif;
          }
        `}
      />
      {/* ... */}
    </>
  )
}
```

The `<Global>` component has an attribute, `styles`, which in turn takes a `css` function as it's value.

The `css` function takes as it's argument a [tagged template literal](https://wesbos.com/tagged-template-literals), which in this case consists of a string of standard CSS contained within backticks. You can put any CSS here that you want to be applied site wide.

When you save the file you should notice that the fonts on your site have now changed automatically to be sans-serif.

Next we'll look at the power and flexibility that styled components give us.

{% hint style="success" %}
**Check you're on the right track** by comparing your changes with [the ones in this commit](https://github.com/frontity-demos/tutorial-hello-frontity/commit/6ae98d9e25dbb706b9dff447955a3379ed1d17d0).
{% endhint %}
