# Ajax Calls in jQuery

AJAX (Asynchronous JavaScript And XML) is used for updating webpages without reloading them.

## GET

### Client (`jQuery`)

```javascript
$.ajax({
    url: '/get-data',
    contentType: 'application/json',
    success: result => console.log(result),
})
```

or, more succinctly,

```javascript
$.get('/get-data', (data, status) => console.log(data))
```

### Server (`Node.js`, `express`)

```javascript
app.get('/get-data', (req, res) => {
  res.send(JSON.stringify(data))
})
```

## POST

### Client (`jQuery`)

```javascript
$.ajax({
    url: '/send-data',
    method: 'POST',
    contentType: 'application/json',
    data: JSON.stringify(data),
    success: response => console.log(response)
  })
```

or, more succinctly,

```javascript
$.post('/send-data', JSON.stringify(data), (data, status) => console.log(data))
```

### Server (`Node.js`, `express`, `body-parser`)

```javascript
app.use(require('body-parser').json())

app.post('/send-data', (req, res) => {
    const data = req.body
    // Use data
    res.send('Success!')
})
```

_Note: none of this code is tested, so use at your own risk_
    