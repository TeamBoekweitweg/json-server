# json-server

Fake rest api server to generate fake routes to speed up front-end development.

## Initial Setup

```bash
npm install -D json-server json-server-auth
```

## Run Json-server

use NPX so you won't need to install json-server globally.

```bash
npx json-server-auth db.json -p 5000
```

run json-server with authentication package while using db.json on port 5000.

## http requests and responses

I use httpie to make http requests. Feel free to use another program to make http requests (I.e.: Postman) check resources for more info.

### Register a user and receive a jwttoken.

request:

```bash
http :5000/register email="jan@jan.nl" password="start1234"
```

response:

```bash
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImphbkBqYW4ubmwiLCJpYXQiOjE2MTYxNTc5NDEsImV4cCI6MTYxNjE2MTU0MSwic3ViIjoiMSJ9.SQd4S66IBMeuI-ySGmXsA-r0TqRwP7hBWEPYAUH8H8g"
}
```

### Login to receive a jwttoken

request:

```bash
http :5000/login email="jan@jan.nl" password="start1234"
```

### Receive a fake Unique Barcode

It is not generating an actual Unique Barcode. It will respond always with the same response that respresents a unique barcode.

request:

```bash
http://localhost:5000/barcode
```

response:

```bash
[
    "94ac8ff1-eb0c-4117-b77a-64f0cfb6e792"
]
```

## resources

[json-server-auth](https://www.npmjs.com/package/json-server-auth)

[httpie](https://httpie.io/)

[postman](https://www.postman.com/)