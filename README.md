![eXide logo](resources/images/logo.png)

[![Build Status](https://travis-ci.com/eXist-db/eXide.svg?branch=develop)](https://travis-ci.com/eXist-db/eXide)

# eXide - a web-based XQuery IDE

eXide is a web-based XQuery IDE built around the [ace editor](https://ace.c9.io/). It is tightly integrated with the [eXist-db native XML database](https://exist-db.org). 

## Features

*   XQuery function and variable completion (press Ctrl-Space or Opt-Space)
*   Outline view showing all functions and variables reachable from the current file
*   Powerful navigation (press F3 on a function call to see its declaration)
*   Templates and snippets
*   Background syntax checks for XQuery and XML
*   Database manager
*   Support for EXPath application packages: scaffolding, deployment...
*   And more ...

eXide consists of two parts:

1.  a javascript library for the client-side application
2.  a set of XQuery scripts which are called via AJAX

## Dependencies

eXide requires the [shared-resources](https://github.com/eXist-db/shared-resources) package, which bundles the [ace editor](https://github.com/ajaxorg/ace) files and is included in eXist-db distributions.

Building eXide requires [git](https://git-scm.com/) and [Apache Ant](https://ant.apache.org/). 

Running tests requires [npm](https://www.npmjs.com/) and [node.js](https://nodejs.org/).

## Getting eXide

eXide is included in eXist-db distributions and can be opened directly at `http://localhost:8080/exist/apps/eXide`. It can also be opened via the Dashboard or the "Open eXide" entry in eXist-db's task or menu bar. 

You can upgrade to new releases of eXide via the Dashboard app's Package Manager. 

You can also build eXide from source and install it.

Read eXide's [usage documentation](https://exist-db.org/exist/apps/eXide/docs/doc.html) on eXist-db.org, or on a local system, open `http://localhost:8080/exist/apps/eXide/docs/doc.html`.

## Building

To build eXide from scratch:

```bash
git clone git://github.com/eXist-db/eXide.git
cd eXide
git submodule update --init --recursive
```

Next, call ant on the `build.xml` file in eXide:

```bash
ant
```

You should now find a `.xar` file in the `build/` directory: `build/eXide-*.*.*.xar`. The `.xar` file is an EXPath Application package containing eXide. Install this into any compatible eXist-db instance using the Dashboard's Package Manager.

## Testing

We welcome contributions to help us improve both unit and integration tests. Current tests can be found in the `cypress/integration` folder.

eXide's GitHub repository is configured to run tests automatically on each PR via TravisCI (see `.travis.yml`).

To run tests locally, build and install eXide on localhost, and start the tests:

```bash
npm run cypress
```

If successful, the test runner should report, "All specs passed!"

## Publishing

eXist-db.org Community administrators publish eXide releases by uploading the eXide `.xar` file to the [public repo](https://exist-db.org/exist/apps/public-repo/index.html). 

Releases are also published to the eXide GitHub repository's [Releases](https://github.com/eXist-db/eXide/releases) page. To do so, either use the Releases page or add a tag in the form: 'vX.X.X' to the repo (where `X` corresponds to the semantic version number of the new release). 

If you need help with a release of eXide, post a note in the [eXist-db Community Slack](https://exist-db.slack.com). 
