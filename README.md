
gulp-web-modules plugin used to precompile and include handlebars templates

Usage
-----
Your handlebars template should be located in a file called *templates* within your section directory

    {project root}
    |-- sections
        |-- foo
            |-- templates
                |-- myTemplate.hbs

And you will be able to access your templates within the section using the following code

    var data = {foo: 'bar'};
    var content = require('./templates')(data);

Install
------
Add this plugin to the gulp-web-module reference in your gulpfile
    var gulpWebModules = require('gulp-web-modules'),
        gwmHandlebars = require('gwm-handlebars');

    gulpWebModules({
      plugins: [
        gwmHandlebars(options[, {handlebars instance}])
      ]
    }).injectTasks(gulp);

Options
-------
The options that can be provided when creating this plugin is a hash with the following values
* *ext*: (default "hbs") the file extension
* *fileName* (default "templates") the directory name (and module name when retrieving the templates)

The handlebars instance can be provided.  If not, handlebars ~1.3 will be used.