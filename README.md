# small_json
Reduce JSON by not nessesery whitespaces.
It use ECMA-262 3rd Edition as JSON base and removes space, linefeed, carriage rerun or horizontal tab as whitespaces.

```javascript
var smallJSON = function (json) {
  if (typeof json == "string") {
      return json.trimEnd().replace(/ (?=(?:(?:\\.|[^\\"])*"(?:\\.|[^\\"])*")*(?:\\.|[^\\"])*\})|[\n\r\t\v]*/g, "");
    } else {
      return json;
    }
};

var test_json = "{ \"key\": \"value\" }";
alert(smallJSON(test_json));
```

Thanks to Tim Pietzcker for regex exempla with groups.
