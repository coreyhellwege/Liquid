# Shopify Basics

Enhancing and extending Shopify’s core features can be as simple as installing a new app, or as complex as developing backend functionality. When faced with a merchant need that cannot be solved with Shopify’s core features, ask yourself the following three questions:
- Is there an app/theme you can install to gain the desired functionality?
- Is there an app/theme that provides most of the functionality you need?
- What tools/resources are available to help you build this functionality?

## Developing for merchant needs

Successful apps and themes directly address a particular merchant need and provide a simple and direct solution. When merchants look for apps and themes to install on their stores, they are looking to address a specific pain point or challenge.

## Building a custom theme

For clients with larger budgets or more complex and unique needs, you can build your own custom theme from scratch. Developing Shopify themes can have a high degree of complexity and require a large time investment, depending on the needs of your audience.
This method will require you to have a significant level of familiarity using HTML, CSS, Liquid and the Shopify Admin API.

## Scripts

Exclusive to Shopify Plus merchants, the Shopify Script Editor—a Ruby API—can be used to create and simplify discounts and sales. Scripts run on Shopify servers and are used to create personalized experiences for customers in their cart or at checkout.

Shopify Plus merchants can benefit from scripts customizations like:
- Applying discounts on products and modifying line item properties in the cart
- Using script templates to offer bulk discounts, flat-rate discounts, BOGO, and percentage off sales that can be applied to an entire order or specific products within an order
- Showing or hiding payment options based on cart contents, customer tags, etc.
- Increasing average order value and offering free shipping on their terms

In order to use the Script Editor, the app has to be installed on a merchant store. Writing scripts requires some familiarity with both Ruby and Liquid.

## Buy button

The Shopify Buy Button lets you easily add e-commerce functionality to your merchants’ blog, website, or email campaigns. By doing this, your merchant can create unique buying experiences across multiple properties that are all managed through a single Shopify store.
The Buy Button allows you to create snippets of code which can be embedded in HTML to:
- Display products and collections on merchant sites/blogs/newsletters
- Add simple shopping cart and checkout functionality
- Provide buttons to link to Shopify Checkout
By using snippets of code to embed these products and features, you can avoid writing custom code or styles while still getting the custom functionality. The buy button is pre-installed as a sales channel app on every Shopify subscription plan. Creating embed codes can be done through the Shopify Admin.

## Authentication

In order to interact with the Shopify API, your app needs to provide authentication credentials. The way to provide these credentials depends on the type of app that you're developing.

### Private apps
Private apps can authenticate through basic HTTP authentication. When you create a private app through your Shopify Admin, you will be able to generate the credentials used to authenticate the app.

Private apps also require you to set permissions for your app within the Shopify Admin. These permissions dictate what your private app will have access to and should be set carefully.

### Public apps

Public apps are created through your partner dashboard. From there you will be able to generate API credentials for your app. Public apps provide credentials to a merchant store through an O-Auth handshake.

### Themes

While you do not need to provide authentication for your theme itself, tools used to develop themes, such as Slate and Theme Kit, will require you to create a private app to develop using them. You can learn more about authenticating these developer tools by reading our guides on getting started with Slate and setting up a local development environment using Theme Kit.

___

## General Development Best Practices

### Use supported libraries and tools

Using a Shopify supported API, SDK, or library is a great way to get started on a project. You can use official Shopify libraries or supported third party libraries for authenticating and interacting with the Shopify API. Whether you want to save time or are unfamiliar with the Shopify platform, starting to develop with a library allows you to save time upfront.
To save even more time, there are tools that provide you with a framework off of which you can build your app or theme.

- Theme developers can use Slate and Theme Kit to work off of a base theme template

### Use version control

Version control software (e.g. Git, Subversion, and Mercurial) allows you to track, save, and deploy changes to your codebase or filesystem. By integrating version control into your development process you can build more efficient and secure ways for developers to:

- Collaborate by working on the same feature codebase without sending files back and forth
- Store and deploy versions of software
- Restore previous versions in case of emergency
- Create constant backups for every major feature change of a product

### Automate your testing

Constant testing is essential for both apps and themes. For every update, feature release, and bug fix, thorough testing can prevent you from releasing unstable software. Failure to test can result in negative reviews and app/theme uninstalls.
Automated testing can ensure that code and web standards are met before you deploy a new feature. You can automate your testing by:

- Writing test cases for any custom code in apps or themes
- Using testing tools to provide automated web testing (e.g. Selenium, TestingWhiz, TestComplete)

### Adhere to common coding best practices

- Writing well documented code
- Writing object oriented code
- Writing testable code and providing test cases
- Structuring code blocks so that they are readable
- Formatting your code appropriately (e.g. indentation, quotation, casing)

### Use GraphQL

Where possible, using GraphQl to interact with Shopify’s APIs over REST will allow you to take advantage of faster requests and more structured responses. You can use the GraphQL explorer to run test queries or visit the Shopify Help Center to learn more about what GraphQl is and how it works with Shopify.

___

## Theme development best practices

### Develop locally

While you can make use of the Shopify Theme Editor to make changes to Liquid files from the Shopify Admin, developing locally provides a safer, quicker way to build and customize Shopify themes. By working on your theme’s codebase locally, you can avoid making changes directly on your published theme. This prevents errors,  bugs, or interruption to the store’s uptime. Local development also allows you to use the tools and workflows you are most comfortable with.

### Design and build-in components

Making use of pattern libraries and style guides to design components that can be reused is a great way to save on time and effort. It ensures a consistent look and feel for common elements and contributes to a smooth user experience.
Using components also saves time in development by allowing you to rebuild common features by importing a set style, configuration, or element. Shopify Polaris is an example of a design system that provides components to developers.

### Use Sass

Sass is a CSS preprocessor that allows you to do more with your stylesheets. You can use Sass to:
- Organize your styles by nesting elements or using partials
- Define and use variables for common or repeated styles (e.g. colors, borders, box-shadows)
- Define functions and mix-ins to use on any elements
- Use mathematical functions

___

## Development tools and features

- <b>Development stores</b> are a very useful feature in your Shopify Partner Dashboard for theme and app development. Development stores provide a sandbox environment to build, test, and play with the Shopify platform.

- <b>Theme Kit</b> is a command line tool that will enable you to upload themes to multiple environments, download a theme from a Shopify store, watch for local changes, and sync files automatically from a Shopify store.

- <b>Slate</b> is a theme scaffold and command line tool for developing Shopify themes. It’s designed to assist your development workflow and speed up the process of developing, testing, and deploying themes to Shopify stores.

- <b>Shopify Plus Partner Sandbox Stores</b> enable Shopify Plus Partners to learn, test and preview Shopify Plus products in up to 5 environments. These environments are for education and testing, and cannot be transferred to a paid plan (unlike development stores).

- <b>Developer Tools App</b> helps you develop by allowing you to experiment with Shopify’s API and populate your store with dummy data, such as products, customers, and orders.

- <b>Supported libraries</b> list official Shopify and supported third party APIs, SDKs, and examples for authenticating and interacting with the Shopify API. These libraries can help you develop Shopify apps quicker and more efficiently.

- <b>Postman</b> is a development environment app for APIs. You can use it to learn, design, and test API calls before building your app.

- <b>Shopify Partner Tools</b> is a list of resources available to Shopify Partners. This list includes a number of free tools that can be used to simplify your design or development processes and grow your business (e.g. project document templates, UI kits, and branding assets).
