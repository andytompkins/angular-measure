##angular-measure

angular service wrapper for performance.now() measurements

#### Usage

```javascript
var app = angular.module('myApp', ['angular-measure']);
app.controller('AppController', [ '$scope', '$measure', function($scope, $measure) {
	$measure.$start('operation1');
	// perform operation 1
	$measure.$stop('operation 1'); // only logs to console

	$measure.$start('operation 2');
	// perform operation 2
	$measure.$stop('operation 2', function(ms) {
		alert('it took ' + ms + ' ms');  // logs to console and shows time in alert
	});
	
	$measure.$start('operation 3');
	// perform part of operation 3
	  $measure.$start('nested operation');
	  // perform nested operation
	  $measure.$stop('nested operation');
	// perform the rest of operation 3
	$measure.$stop('operation 3');  
}]);
```
