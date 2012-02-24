# Introduction

s3asy ('S-Three-Zee') is a simple library for issuing GET, PUT, and DELETE requests against Amazon S3. It allows caching of files  in a local redis instance using the ```If-Modified-Since``` and ```Last-Modified``` headers as cache-control.

It achieves this simplicity by utilizing [knox](https://github.com/LearnBoost/knox) and [cacheit](https://github.com/andrewjstone/cacheit) under the hood.

# Example

```javascript
var S3 = require('s3asy');
var s3 = new S3({
  key: '<api-key-here>',
  secret: '<secret-here>',
  bucket: 'learnboost',
  cache: true
});

s3.get('/some/path', {'x-amz-acl': 'private'}, function(err, body) {
  console.log(body);
});

```

# API

## s3.get(path, [headers], callback) 

## s3.put(path, [headers], data, callback)

## s3.delete(path, [headers], callback)
