# import
```
const axios = require('axios');
```
# get raw response
```
axios.get("url",{ transformResponse: (r) => r }); 
```
# get concurrent responses
```
(async () => {
  try {
    const [response1, response2] = await axios.all([
      axios.get('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2020-03-18'),
      axios.get('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2020-03-17')
    ]);
    console.log(response1.data.url);
    console.log(response1.data.explanation);

    console.log(response2.data.url);
    console.log(response2.data.explanation);
  } catch (error) {
    console.log(error.response.body);
  }
})();
```
