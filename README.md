# JSON deep decoder

A helper app to deeply decode JSON which may have some of its values as JSON-strings.

[Live demo](https://mindaugasw.github.io/json-deep-decoder/)

---

E.g. this JSON:
```json
{
  "deeply": "{\"encoded\":\"value\"}"
}
```

Will be decoded to:
```json
{
  "deeply": {
    "encoded": "value"
  }
}
```

While most other tools would not decode it any further and return the same JSON from input.

Supports decoding both JSON at the top level and JSON string. The following string is equivalent to the input above:  
`"{\"deeply\":\"{\\\"encoded\\\":\\\"value\\\"}\"}"`

Even more deeply encoded JSON example:  
`"{\"very\": \"{\\\"deeply\\\":\\\"{\\\\\\\"encoded\\\\\\\":\\\\\\\"value\\\\\\\"}\\\"}\"}"`

Will be decoded to:
```json
{
  "very": {
    "deeply": {
      "encoded": "value"
    }
  }
}
```
