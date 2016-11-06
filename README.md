StoreJS exposes a simple API for cross browser local storage with expiration and fallback to cookies.

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
store.set('username', 'Shakeeb', { expires: '10s' } );
store.set('username', 'Shakeeb', { expires: '10m' } );
store.set('username', 'Shakeeb', { expires: '10h' } );
store.set('username', 'Shakeeb', { expires: '10d' } );
```


How does it work?
------------------
store.js uses localStorage when available, and falls back to cookies. It also use cookies like expiration behavior for localStorage as well.

Installation
------------
Just grab [store.min.js] include them with a script tag.
