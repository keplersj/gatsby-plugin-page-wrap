# gatsby-plugin-page-wrap

Gatsby plugin to conveniently wrap a component around pages.

## Motivation

This plugin allows you to ensure consistency in the pages created for your Gatsby site by wrapping them in a parent component. This allows your pages, as defined in `./src/pages/` or created dynamically, to focus on their content and empower Gatsby to ensure site-wide consistency.

Functionally this is equalivalent to the following:

```js
export default () => (
  <WrapperComponent>
    <PageContent />
  </WrapperComponent>
);
```

### Why use a plugin?

For most use cases, this plugin is likely not needed and overkill. However if you are dynamically creating many pages for your site or if your site is composed of many [Gatsby Themes](https://www.gatsbyjs.org/docs/themes/), this plugin can help ensure consistency (navigation, global styles, SEO, etc.) across the pages created for your site.

### Gatsby Themes

It is likely that if you are considering using Gatsby's `wrapRootElement` or `wrapPageElement` APIs to make the layout of your site built with themes consistent this plugin will fit your use case and simplify your site's `gatsby-node.js` and `gatsby-browser.js` scripts. However, if this is not you please read the [Gatsby Documentation on Gatsby Theme Layout](https://www.gatsbyjs.org/docs/themes/theme-composition/#layouts) and [Chris Biscardi's writings on the subject](https://www.christopherbiscardi.com/post/layouts-in-gatsby-themes/).

## Installation

```bash
# with npm:

npm install gatsby-plugin-page-wrap

# with yarn:

yarn add gatsby-plugin-page-wrap
```

## Usage

In your `gatsby-config.js`:

```js
module.exports = {
  plugins: [
    {
      resolve: "gatsby-plugin-page-wrap",
      options: {
        layouts: {
          default: "./src/components/BaseLayout/index.tsx"
        },
        blacklist: ["/404", "/index"]
      }
    }
  ]
};
```

## License

Copyright [Kepler Sticka-Jones](https://keplersj.com/) 2019. Licensed [ISC](https://choosealicense.com/licenses/isc/).
