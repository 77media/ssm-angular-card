ssm-angular-card
============

Angular directive for card https://github.com/jessepollak/card

## Screenshot

TODO

## Demo

TODO

## Installation

### bower
`bower install ssm-angular-card`

##Usage

###`name` is required for form and inputs (you can use any unique name)

```html
<form action="#"
  name="cardForm"
  data-card
  data-width="500"
  data-card-container="#card-container"
  data-placeholders="cardPlaceholders"
  data-options="cardOptions"
  data-messages="cardMessages">

  <div>
    <input placeholder="Card number" type="text" name="CardNumber" card-number data-ng-model="card.number" />

    <input placeholder="Full name" type="text" name="CardName" card-name data-ng-model="card.name" />
  </div>
  <div>
    <input placeholder="MM" type="text" name="CardMonth" card-expiry data-ng-model="card.month" />/
    <input placeholder="YY" type="text" name="CardYear" card-expiry data-ng-model="card.year" />

    <input placeholder="CVC" type="text" name="CardCvc" card-cvc data-ng-model="card.cvc" />

    <input type="button" value="Change card" data-ng-click="changeCard()" />
    <input type="button" value="Clear" data-ng-click="clear()" />
  </div>
  
</form>
```

```js
angular.module('app', ['gavruk.card'])
.controller('ExampleCtrl', ['$scope', function($scope) {

  $scope.card = {
    name: 'Mike Brown',
    number: '5555 4444 3333 1111',
    expiry: '11 / 2020',
    cvc: '123'
  };

  $scope.cardPlaceholders = {
    name: 'Your Full Name',
    number: 'xxxx xxxx xxxx xxxx',
    expiry: 'MM/YY',
    cvc: 'xxx'
  };

  $scope.cardMessages = {
    validDate: 'valid\nthru',
    monthYear: 'MM/YYYY',
  };

  $scope.cardOptions = {
    debug: false,
    formatting: true
  };

}]);
```
