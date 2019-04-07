---
layout: post
title:      "Axios vs Fetch"
date:       2019-04-07 17:17:22 +0000
permalink:  axios_vs_fetch
---


Once you start testing your app in headless browser environment, there can be issues with fetch API. Not all browsers support native fetch API, older browsers especially. 

One of the stable library to substitute the native fetch is axios. Axios is a Javascript library used to make http requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. Another feature that it has over .fetch() is that it performs automatic transforms of JSON data.

First, we have to install axios on the command line:

npm install axios

To use it with React app we have to import it in the app

import  axios from  'axios';

Now we can use axios instead of fetch()  in almost identical way. It takes the URL as an argument and returns a promise. The result does not have to transform the returned response to JSON anymore. 

If you use .fetch() there is a two-step process when handing JSON data. The first is to make the actual request and then the second is to call the .json() method on the response.

const url = 'https://api.spotify.com/v1/artists/0OdUWJ0sBjDrqHygGUXeCF'

fetch(url).then(response => response.json()).then(data => console.log(data));



Here is how the same request works with axios

const url = 'https://api.spotify.com/v1/artists/0OdUWJ0sBjDrqHygGUXeCF'
axios.get(url).then(response => console.log(response));

So by using axios you can cut out the middle step of passing the results of the http request to the .json() method. Axios just returns the data object you would expect.

The second issue is how .fetch() handles error responses. Logically you would think that if .fetch() gets an error it would enter the .catch() block and return anything there, right? Not necessarily. Here is an example.

I have altered my url variable from the previous examples so that it is now incorrect. I would expect a 400 error at this point and for my .fetch() to go into the .catch() block but this is what happens instead.

const url = 'https://api.spotify.com/v1/artists/0OdUWJ0sBjDrqHygGUXeCFcdsds';
fetch(url).catch(error => console.log('BAD', error)).then(response => console.log('GOOD', response));
I’ve added the ‘BAD’ and ‘GOOD’ strings in the responses to clarify what is happening here.


I get the 400 response code but, as you can see by the ‘GOOD’ string in the console, the .then() block was executed. How does Axios handle this? The way you would probably expect. You get any kind of error with the http request and the .catch() block is executed.


The ‘BAD’ string is there and the error is logged to the console.

The .fetch() method is a great step in the right direction of getting http requests native in ES6, but just know that if you use it there are a couple of gotchas that might be better handled by third-party libraries like Axios.
