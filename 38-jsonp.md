#Explain how JSONP works(and how it's not really Ajax);

# Initial Thoughts

- What is `JSONP`?. `JSON` is Javascript Object Notation, it's a way to store data where javascript can easilly acess it. So what is the "P"?.

## Research

- P is "padding
- Does not use XMLHttpRequest
- seems like `php` uses this... like so to get away from XMLHttpRequest objects

https://www.w3schools.com/js/js_json_jsonp.asp

```
<?php
$myJSON = '{ "name":"John", "age":30, "city":"New York" }';

echo "myFunc(".$myJSON.");";
?>

```

- Looks like JSONP was used if the server was fully trusted
- CORS is a more modern way to trust external domains
- JSONP is really just javascript, sending a callback which then gives you back data.
- this is pretty hacky.

`script` uses a request, to get javascript callback, then the client can execute the callback.

```

<!-- https://mydomain.com -->
<script>
  function printData(data) {
    console.log(`My name is ${data.name}!`);
  }
</script>

<script src="https://example.com?callback=printData"></script>

```
