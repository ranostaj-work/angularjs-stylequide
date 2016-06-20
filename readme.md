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
## Directives
## Controllers
## Services
## Factories
## Routing
## Performance
## Minification
## Application folder structure
