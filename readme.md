# Angular 1.5.x style guide

Angular style guide for team development.

# Table of Contents
1. [Modules](#modules)
2. [Components](#components)
3. [Directives](#directives)
4. [Controllers](#controllers)
5. [Services](#services)
6. [Factories](#factories)
7. [Routing](#routing)
8. [Performance](#performance)
9. [Minification](#minification)
9. [Application folder structure](#application-folder-structure)


## Modules

- Use unique naming conventions with separators for sub-modules.

> For example `app` may be your root module while `app.dashboard` and `app.users` may be modules that are used as dependencies of app.

### Definitions

**Setters:**

Declare modules without a variable using the setter syntax.

Declare `app core` dependency modules in separate module:
```javascript

// Core module
 angular
    .module('app.core', [
        'ngMaterial',
        'ngRoute'
    ]);

```
Define `app` module and include `app.core`

```javascript
 // App module    
 angular
     .module('app', [
         'app.core',
         'app.dashboard',
         'app.users'
     ]);
 ```
**Getters:**

```javascript
angular
    .module('app')
    .controller('SomeController', SomeController);

function SomeController() { }
```

## Components

>In Angular, a Component is a special kind of directive that uses a simpler configuration which is suitable for a component-based application structure. [AngularJS doc for  more](https://docs.angularjs.org/guide/component) about **Components**

Components are essentially templates with a controller. They are not Directives, nor should you replace Directives with Components, unless you are upgrading "template Directives" with controllers, which are best suited as a component.

### Coponents architecture

* Components only control their own View and Data.
* Components should never modify any data or DOM that is out of their own scope.

```javascript

 (function(){

  angular
    .module('app')
    .component('myComponnent', myComponnent);

    // Component
    function myComponnent() {

      // Component Controller
      function myComponnentCtrl() {};


      return {
        templateUrl: "path/to/template",
        controller:myComponnentCtrl,
        require:{},
        bindings: {}
      }
    };

  })();

```


## Directives
## Controllers
## Services
## Factories
## Routing
## Performance
## Minification
## Application folder structure
