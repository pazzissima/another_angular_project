Practicing Angular

So far this is our typical workflow when making an AngularJS app:

Create a module, and use ng-app in the view to define the application scope.
Create a controller, and use ng-controller in the view to define the controller scope.
Add data to $scope in the controller so they can be displayed with expressions in the view.
To see the app in browser:

cd into workspace
Fire up webserver: node web-server.js
Got to: http://localhost:8000/index.html

Creating your own directives!

What did we just do? We wrote code to teach the browser a new HTML element <app-info>, and used it in the view to display each app's details.

First in js/directives/appInfo.js, we made a new directive. We used app.directive to create a new directive named 'appInfo'. It returns an object with three options:

restrict specifies how the directive will be used in the view. The 'E' means it will be used as a new HTML element.
scope specifies that we will pass information into this directive through an attribute named info. The = tells the directive to look for an attribute named info in the <app-info> element, like this:
 <app-info info="shutterbugg"></app-info>
The data in info becomes available to use in the template given by templateURL.
templateUrl specifies the HTML to use in order to display the data in scope.info. Here we use the HTML in js/directives/appInfo.html.
Looking at js/directives/appInfo.html, we define the HTML to display details about an app, like its title and price. We use expressions and filters to display the data.

Then in index.html we use the new directive as the HTML element <app-info>. We pass in objects from the controller's scope ($scope.shutterbugg) into the <app-info> element's info attribute so that it displays.
