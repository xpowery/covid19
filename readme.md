Transforms the data from [CSSEGISandData/COVID-19](https://github.com/CSSEGISandData/COVID-19) into a json file. Available at [https://xpowery.github.io/covid19/timeseries.json](https://xpowery.github.io/covid19/timeseries.json). Updated three times a day using GitHub Actions.

The json contains the number of Coronavirus confirmed cases, deaths, and recovered cases for every country and every day since 2020-1-22:

```
{
  "india": {
    "2020-1-22" : [0, 0, 0],
    "2020-1-23" : [0, 0, 0],
    ...
  },
  ...
}
```

For example, if you want to use it from a web site:

```js
fetch("https://xpowery.github.io/covid19/timeseries.json")
  .then(response => response.json())
  .then(data => {
    for(let date in data["india"]) {
      const [confirmed, recovered, deaths] = data["india"][date];
    }
  });
```


## License

The code from this repo is MIT licensed.  
The data is under [CSSEGISandData/COVID-19](https://github.com/CSSEGISandData/COVID-19/) terms of use.
