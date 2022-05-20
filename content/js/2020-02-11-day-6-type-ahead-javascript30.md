---
title: 'Day 6 – Type Ahead – #javascript30'
author: pt1602
type: post
date: 2020-02-11T20:01:26+00:00
url: /day-6-type-ahead-javascript30/
categories:
  - everything
  - javascript30
tags:
  - 30 days
  - 30 days of javascript
  - array
  - fetch
  - javascript
  - javascript30
  - js
  - json

---
// What have I learned today?

// get a json file for data

`const json = 'https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json';`

// fetch data from url

`fetch(json)<br />
 .then(rawData => rawData.json()) // convert promise to json<br />
 .then(data => cities.push(...data)); // convert promise to array & push data in cities via '...'`

// listen for typing

`input.addEventListener('change', showMatches);<br />
input.addEventListener('keyup', showMatches);`

// find typed stuff in json

`function findMatches(typedWord, cities) {<br />
  return cities.filter(place => {</p>
<p>    const regex = new RegExp(typedWord, 'gi'); // g = global -> look through entire string, i = lower and uppercase<br />
    return place.city.match(regex) || place.state.match(regex);<br />
  });<br />
};`

// show matched data

``function showMatches(){<br />
  const foundMatches = findMatches(this.value, cities);<br />
  const html = foundMatches.map(place => {<br />
    const regex = new RegExp(this.value, 'gi');<br />
    const cityName = place.city.replace(regex, `<span class="hl">${this.value}</span>`);<br />
    const stateName = place.state.replace(regex, `<span class="hl">${this.value}</span>`);<br />
    return `<br />
        ${cityName}, ${stateName}<br />
        ${place.population}<br />
    `;<br />
  }).join('');// from array to one string;;<br />
  suggestions.innerHTML = html;<br />
}``