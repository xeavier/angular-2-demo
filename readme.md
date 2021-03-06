# Single Page App with Angular 4

This is a single page app which provides the user with the ability to search for and view data from the Google Books Api.
The purpose of this app is to experiment with as many aspects of Angular 4 as possible. Other technologies used are Webpack, SASS, Jasmine, and of course the Google Books API.

#### features
* Ahead of Time compilation
* Lazy loading of routes
* Animated transitions
* Reactive forms
* Unit tests

### Configuration
There are separate configurations for testing, development and production. Webpack is used for generating builds.

#### Production environment
NgTools Webpack plugin does transpilation, AOT compilation, and supports lazy loading of feature modules. The Commons Chunk Plugin optimises generated bundles by removing shared code.

#### Dev environment
The dev config is similar to the production config with the main difference being it sets up the Webpack Dev server.

#### Testing Environment
The test config is even simpler than the dev config. We use the awesome-typescript-compiler instead of NgTools for compilation as we have no need for AOT compilation for unit tests.

### Issues encountered during development

1. If you want to exclude files from being transpiled, they need to be excluded in the tsconfig file. (Excluding them in the Webpack config doesn't work). A 'gotcha' here though is that the exclude property has a default value which excludes files such as those within node_module folder. If you fail to explicitly set these default values within the exclude array then the transpiler will attempt to compile them and likely result in errors.


2. In a component, moduleId is normally set using `module.id`. Angular expects moduleId to be a string but Webpack's implementation of `module.id` returns a number! Solution is to convert this into a string. e.g. `'' + module.id`.





