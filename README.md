# JSTestDriver + Jasmine + RequireJS #

This project demonstrates how you can test AMD modules with Jasmine using JSTestDriver.  Unlike other setups like podefr/jasmine-reqjs-jstd these modules can be anonymous modules.


## Run the tests ##

1. Clone the repository
2. cd to the project's root directory
3. Start the JSTestDriver server: `java -jar bin/JsTestDriver-1.3.4.b.jar --port 9876`
4. Open `http://localhost:9876/capture` in the browser(s) you want to run the tests in
5. Run the test suite: `java -jar bin/JsTestDriver-1.3.4.b.jar --reset --tests all`


## How does it work ##

RequireJS fetches the modules from the test server just like it would
in a development environment.  For this to work two things have to be
done:

1. JSTestDriver needs to be told to serve the modules.  It does so for all files that match the pattern under the `serve:` directive in `jsTestDriver.conf`.

2. All file paths need to be prefixed with `/test/`.  This is done using the `baseUrl` configuration option in `spec/lib/require_config.js`.


