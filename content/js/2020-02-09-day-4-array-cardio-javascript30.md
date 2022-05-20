---
title: 'Day 4 – Array Cardio – #javascript30'
author: pt1602
type: post
date: 2020-02-09T15:59:25+00:00
url: /day-4-array-cardio-javascript30/
categories:
  - everything
  - javascript30
tags:
  - 30 days of javascript
  - array
  - arrays
  - coding
  - javascript
  - javascript30
  - variables

---
What have I learned today?

Given data:

`const inventors = [<br />
{ first: 'Albert', last: 'Einstein', year: 1879, passed: 1955 },<br />
{ first: 'Isaac', last: 'Newton', year: 1643, passed: 1727 },<br />
{ first: 'Galileo', last: 'Galilei', year: 1564, passed: 1642 },<br />
{ first: 'Marie', last: 'Curie', year: 1867, passed: 1934 },<br />
{ first: 'Johannes', last: 'Kepler', year: 1571, passed: 1630 },<br />
{ first: 'Nicolaus', last: 'Copernicus', year: 1473, passed: 1543 },<br />
{ first: 'Max', last: 'Planck', year: 1858, passed: 1947 },<br />
{ first: 'Katherine', last: 'Blodgett', year: 1898, passed: 1979 },<br />
{ first: 'Ada', last: 'Lovelace', year: 1815, passed: 1852 },<br />
{ first: 'Sarah E.', last: 'Goode', year: 1855, passed: 1905 },<br />
{ first: 'Lise', last: 'Meitner', year: 1878, passed: 1968 },<br />
{ first: 'Hanna', last: 'Hammarström', year: 1829, passed: 1909 }<br />
];<br />
` 

// filter();  
// Filter the list of inventors for those who were born in the 1500&#8217;s

`const fifeteen = inventors.filter(function (inventor) {<br />
if (inventor.year >= 1500 && inventor.year <= 1599) {<br />
return true;}<br />
});<br />
` 

// map();  
// Give us an array of the inventors first and last names

`const name = inventors.map(function (inventor) {<br />
const fullName = inventor.first + ', ' + inventor.last;<br />
return fullName;<br />
});<br />
` 

// sort();  
// Sort the inventors by birthdate, oldest to youngest

`const ordered = inventors.sort(function (firstPerson, secondPerson) {<br />
if (firstPerson.year > secondPerson.year) {<br />
return 1;<br />
} else {<br />
return -1;<br />
}<br />
});<br />
` 

// reduce();  
// How many years did all the inventors live all together?

`const allTogether = inventors.reduce(function (total, inventor) {<br />
return total + (inventor.passed - inventor.year);<br />
}, 0);<br />
` 

// nice stuff

`console.table();`

// arrow function

`const alphabetically = people.sort((firstPerson, secondPerson) => {});`