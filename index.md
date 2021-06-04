# CIT 281 lab 08

## Outcome:

This lab went back to fastify webservers and expeimented with fetching data.   
In this lab we fetched JSON placeholder data from a seperate website and created a webserver that parsed and displayed the requested data.   
The webpage displays a title and an image of a colored square with dimenssions.

## Code: 
**[Here]()** is a link to the full code and below is an excerpt.
```javascript
fetch('https://jsonplaceholder.typicode.com/photos')
  .then(responseFromJSONPlaceholder => { return responseFromJSONPlaceholder.json()})
  .then(responseAsJSON => {
    reply
    .code(200)
    .header("Content-Type", "text/json; charset=utf-8")
    .send({ error: "", statusCode: 200, photos: responseAsJSON });
  })
  .catch(err => {
    reply
    .code(404)
    .header("Content-Type", "text/json; charset=utf-8")
    .send({ error: "", statusCode: 404, photos: [] })
  })
});
```

## Images: 
Here is an image of a colorblock (number 12) displayed on the webpae.
![colorblock](https://github.com/Myles-P-D/cit281-lab08/blob/main/colorblock.png?raw=true "colorblock 12")
  
    
Here is an image of a different colorblock (number 30).
![colorblock 30](https://github.com/Myles-P-D/cit281-lab08/blob/main/colorblock_30.png?raw=true "colorblock 30")

