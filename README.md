js-ppwcode-dev
==============

If you want to develop any of the js-ppwcode- projects, check out this über-repo.

The actual js-ppwcode- repositories are included as git submodules, and external
dependencies are setup in the way expected by the js-ppwcode- projects as git
submodules. The usual caveats for working with submodules apply.

You should copy this way of working for an application, where the js-ppwcode-
and other projects are external dependencies. For external dependencies, submodules
are the way to go. The `lib` directory of this project mimics the `lib/` directory
for an application.

Where external dependencies are located, is made explicit in the `dojoConfig.packages`
setting of your project, so you can do what you want. It is also relevant inside the
js-ppwcode- projects, in the definition of the tests, where there is also a variant
of `dojoConfig`. The setup in this repository is compatible with the choices made
in that respect in the js-ppwcode- projects.




Getting started
---------------
This project is defined  with submodules.

To download the submodules, use the literal git commands:

    > git submodule init
    > git submodule update

This will download all needed submodules into `src/lib/`.




Structure
---------
The main project files, with their associated tests, are located in
the `src/lib/ppwcode/util/PROJECT` and `src/lib/ppwcode/vernacular/PROJECT` directories.

The `src/lib/ppwcode/[util|vernacular]/PROJECT/_test/` directories contain the
unit test configurations and unit test starting points.

External dependencies are found in `src/lib`, next to `src/lib/ppwcode/`.

Next to `src/`, working with the project will create other directories,
like `src/node-modules/`, build-directories, reports, ..., and so on,
which are not to be committed to the repo.

This way, `src/` is an undisturbed structure, that represents an unbuild
version of "the application", which can be served over http during
development.


Tests
-----
### DOH

DOH is only supported for the time being, until all tests are moved to
Intern.

When the submodules are downloaded, the DOH tests should work out
of the box when you navigate your browser to
`src/lib/ppwcode/[util|vernacular]/PROJECT/_test/_doh/runTest.html`.
Make sure to run the tests on a web server.

### Intern
#### Setup:
* install node on your system from <http://nodejs.org>
* execute in this directory (i.e., the directory of this README):

        > npm install intern --save-dev


This will install the necessary node modules in `./node-modules`,
next to the `src/` directory.

#### Run in browser
The Intern tests should work when you navigate your browser to
`src/lib/ppwcode/[util|vernacular]/PROJECT/_test/_intern/runTest.html`.
Make sure to run the tests on a web server.


#### Run in NodeJS
The tests can also be run using NodeJS.

To run the tests, execute the following command in the root
directory:

    > node node_modules/intern/client config=src/lib/ppwcode/[util|vernacular]/PROJECT/_test/_intern/intern





TODO
----
* make an über-test
* bring enum - demo-project, new semantics into the fold?
