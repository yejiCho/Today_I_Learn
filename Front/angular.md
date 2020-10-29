# object Object 출력되는 경우

> json 형태의 [object Object] 출력하기

```
ex) json 형태의 object 변수인 objValues js에서 alert,console.log 찍고 싶을때

alert(JSON.stringify(objValues));
```

# AngularJS controllers

```
AngularJS application은 controllers에 의해 controll 된다.

컨트롤러는 자바스크립트의 객체이다.
자바스크립트 object 생성자에 의해 생성

ng-app = "myApp"
ng-controller = "myCtrl"
```

```javascript

<div ng-app="myApp" ng-controller="myCtrl">

First Name: <input type="text" ng-model="firstName"><br>
Last Name: <input type="text" ng-model="lastName"><br>
<br>
Full Name: {{firstName + " " + lastName}}

</div>

<script>
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
  $scope.firstName = "John";
  $scope.lastName = "Doe";
});
</script>
```

```javascript

<div ng-app="myApp" ng-controller="personCtrl">

First Name: <input type="text" ng-model="firstName"><br>
Last Name: <input type="text" ng-model="lastName"><br>
<br>
Full Name: {{fullName()}}

</div>

<script>
var app = angular.module('myApp', []);
app.controller('personCtrl', function($scope) {
  $scope.firstName = "John";
  $scope.lastName = "Doe";
  $scope.fullName = function() {
    return $scope.firstName + " " + $scope.lastName;
  };
});
</script>

```

- [angular_controllers](https://www.w3schools.com/angular/angular_controllers.asp)