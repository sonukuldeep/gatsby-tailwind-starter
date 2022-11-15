<p align="center">
  <a href="https://www.gatsbyjs.com/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter">
    <img alt="Gatsby" src="https://www.gatsbyjs.com/Gatsby-Monogram.svg" width="60" />
  </a>
</p>
<h1 align="center">
  Gatsby minimal starter
</h1>

## 🚀 Quick start

1.  **Create a Gatsby site.**

    Use the Gatsby CLI to create a new site, specifying the minimal starter.

    ```shell
    # create a new Gatsby site using the minimal starter
    npm init gatsby
    ```

2.  **Start developing.**

    Navigate into your new site’s directory and start it up.

    ```shell
    cd my-gatsby-site/
    npm run develop
    ```

3.  **Open the code and start customizing!**

    Your site is now running at http://localhost:8000!

    Edit `src/pages/index.js` to see your site update in real-time!

4.  **Learn more**

    - [Documentation](https://www.gatsbyjs.com/docs/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Tutorials](https://www.gatsbyjs.com/tutorial/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Guides](https://www.gatsbyjs.com/tutorial/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [API Reference](https://www.gatsbyjs.com/docs/api-reference/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Plugin Library](https://www.gatsbyjs.com/plugins?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Cheat Sheet](https://www.gatsbyjs.com/docs/cheat-sheet/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

## 🚀 Quick start (Gatsby Cloud)

Deploy this starter with one click on [Gatsby Cloud](https://www.gatsbyjs.com/cloud/):

[<img src="https://www.gatsbyjs.com/deploynow.svg" alt="Deploy to Gatsby Cloud">](https://www.gatsbyjs.com/dashboard/deploynow?url=https://github.com/gatsbyjs/gatsby-starter-minimal)


## Install tailwind post Gatsby installation

The first thing you will need to do is add the following modules to your Gatsby site

```shell
npm install -D tailwindcss postcss autoprefixer gatsby-plugin-postcss
```

This adds the Tailwind modules along with the gatsby plugin you will need to use Tailwind with Gatsby. After you have added these modules you will need to init Tailwind using the following command

```shell
npx tailwindcss init -p
```

This will create the tailwind.config.js file along with the postcss.config.js files.

Next we will need to enable PostCSS in our gatsby.config.js file. Add the following plugin to this config file.

```shell
module.exports = {
  plugins: [
    'gatsby-plugin-postcss',
  ],
}
```

Now that we have added the postcss plugin to Gatsby we can configure the tailwind.config.js file to scan our templates for any tailwind class usage. This can be done by adding our source path to the tailwind.config.js file.

```shell
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Now lets' add a styles folder underneath our src folder. In the styles folder we will create a file called global.css. Add the following @include lines to the `global.css file.

```shell
/* ./src/styles/global.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Now that we have added a global.css file, we can add it as an import into the gatsby-browser.js file. If you do not have a Gatsby-browser.js file, go ahead and create one and add the following line.

```shell
// gatsby-browser.js
import './src/styles/global.css'
```

This completes tailwind configuration.