# miuri.js

Miuri is simple JavaScript class for parsing URIs.
It's designed to be used in browser, but it can be used as a NodeJS module.

It can retrieve information:

```javascript
miuri = require('miuri.js') // when run on Node.js

uri = new miuri('http://google.com')  
uri.host()  // google.com  
uri.protocol()  // http  
uri.path()      // /  
```

Also from URIs with complex queries:

```javascript
uri = new miuri('/?test=foo&arr[]=1&arr[]=2&data[name]=bar')
uri.query('test') // foo  
uri.query('arr')  // [1, 2]  
uri.query('data') // {name: 'bar'}  
uri.query()       // {test: 'foo', arr: [1, 2], name: 'bar'}  
```

With Miuri you can build full URIs:

```javascript
uri = new miuri()
uri.host('bing.com')
  .protocol('http')
  .path('search')
  .query({
    s: 'my test'
  })
  .toString() // http://bing.com/search?s=my%20test
```

## API reference

### protocol([protocol])
### username([username])
### password([password])
### host([host])
### port([port])
### path([path])
### query([prop, [value]])
### fragment([fragment])
### toString()

## License
Miuri is released under a MIT License.
