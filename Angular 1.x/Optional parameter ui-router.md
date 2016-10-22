Non-URL route parameters


```javascript
state('new-nonurl', {
  url: '/new',
  params: {
    portfolioId: null,
  },
  templateUrl: 'new.html',
  controller: function($scope, $stateParams) {
     $scope.portfolioId = $stateParams.portfolioId;
  }
})
```

Now ui-sref="new-nonurl({ portfolioId: 3 })" will generate the link \new 
but still pass the portfolioId parameter in $stateParams.