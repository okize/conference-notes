## Angular Workshop
### Todd Motto

__Links:__
* https://github.com/toddmotto/fowa2014
* http://www.airpair.com/angularjs
* https://github.com/toddmotto/angularjs-styleguide
* https://docs.angularjs.org/api/
* https://drive.google.com/drive/u/0/#folders/0B7Ovm8bUYiUDR29iSkEyMk5pVUk


### Routing
* dynamic routea and views
* XHR templates
* app state driven by url

$ location service

### Model
* application data structure
* JSON

### View
* components/html
* rendered output

directives - ```ng-<directive>```

### Controller
* drives model & view changes
* contains presentation logic
* hits business logic (services)

$scope - magic opbject that binds js to html
do not do dom manipulation in controller

### Two way data-binding
* keeps datain sync
* model changes drive view changes
* view changes drive model changes

```
<input type="text" ng-model="vm.searchTerm" />

Searching for: {{ vm.searchTerm }}
```

### Directives - manipulating the DOM
* reuseable chunks of code injected
* packaged and managed individually
* custom buttons, forms, tooltips (components)

```
function FileUpload() {
  return {
    scope: {},
    replace: true,
    template: [
      '<div>',
      '</div>'
    ].join(''),
    controller:  function ($scope) {

    }
  };
}

angular
  .module('app')
  .directive('FileUpload', FileUpload);
```

### Services
* Singletons, act as Constructors

```
function UploadService ($http) {
  this.uploadFile = function () {
    // upload file
  }
}

angular
  .module('app')
  .service('UploadService');
```

### Factory
* Singletons, return closures/Objects

```

function AuthService ($http) {
  var AuthService = {};

  AuthService.login = function (username, password) {

  };
  return AuthService;
}

angular.
  .module('app')
  .factory('AuthService', AuthService);

```

### Filters
* managing your data
* single filtering (non-loop)
* multiple ways to create

```
  <div class="timestamp">
    {{ vm.timestamp | date: 'yyyy-mm-dd' }}
  </div>
```

reccommend using .filter

---

### Creating your first app (3 Ds)
* __Design:__ JSON design for the best data responses
* __Distribute:__ integrate data with factory + controllers
* __Declare:__ push to the $scope

### Core functions
* ng-* attributes (internal directives)

```
  <a href="" ng-click="vm.submitForm()">
    Submit
  </a>
```

### Expressions
* inline javascript expression operators

```
  {{ vm.authorised && 'Welcome!' || 'Please login' }}
```


### Routing
* dynamic views, used with ng-views

```
function Router($routeProvider, $locationProvider) {
  $routeProvider
    .when('/inbox', {
      templateUrl: 'views/mailbox.html',
      controller: 'InboxCtrl as vm',
      resolve: InboxCtrl.resolve
    })
    .when('/email/:id', {
      templateUrl: 'views/email.html',
      controller: 'EmailCtrl as vm',
      resolve: EmailCtrl.resolve
    })
    .otherwise({
      redirectTo: 'inbox'
    });
};

angular
  .module('app')
  .config(Router);
```


### Dependency Injection
* the Angular
* minification

```
function AuthService($scope, $rootScope) {

}
AuthServices.$inject = ['$scope', '$rootScope'];

angular
  .module('app')
  .controller('AuthService', AuthService);

```

### Thinking Angular
* think in terms of scopes and data, NOT DOM; no add/remove/toggle classes, ever. Angular does this all for you based on data
* let the data do the work, keep code as minimal as possible
* abstract, abstract, abstract. Keep abstracting into different files for better manaement and copying individual files into new projects, premade working code.

