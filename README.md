# StoreJS
A package which exposes a simple API for cross browser local storage with expiration and fallback to cookies.

```js
// Store 'Shakeeb' at 'username'
store.set('username', 'Shakeeb')

// Get 'username'
store.get('username')

// Remove 'username'
store.remove('username')

// Store an object literal - store.js uses JSON.stringify under the hood
store.set('user', { name: 'Shakeeb', likes: 'javascript' })

// Get the stored object - store.js uses JSON.parse under the hood
var user = store.get('user')
alert(user.name + ' likes ' + user.likes)

// Store with expiration
store.set('username', 'Shakeeb', { expires: '10s' } ); // expires in 10 seconds
store.set('username', 'Shakeeb', { expires: '10m' } ); // expires in 10 minutes
store.set('username', 'Shakeeb', { expires: '10h' } ); // expires in 10 hours
store.set('username', 'Shakeeb', { expires: '10d' } ); // expires in 10 days

/// Use localStorage Directly
store.local('username', 'Shakeeb', { expires: '10s' } ); // store 'username' to localStorgae and make it expires in 10 seconds
store.local('username'); // get 'username' from localStorgae

/// Use Cookie Directly
store.cookie('username', 'Shakeeb', { expires: '10s' } ); // store 'username' to Cookie and make it expires in 10 seconds
store.cookie('username'); // get 'username' from Cookie
```


How does it work?
------------------
store.js uses localStorage when available, and falls back to cookies. It also use cookies like expiration behavior for localStorage as well.

Installation
------------
Just grab [store.min.js] include them with a script tag.
