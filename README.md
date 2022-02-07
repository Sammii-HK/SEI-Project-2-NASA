# NASA API & React APP – SEI Project 2

[Live Site](sammii.dev/nasa-api): https://sammii.dev/nasa-api/#/

### Timeframe

1.5 days

## Technolgies Used

- React
- HTML 5
- SCSS
- NASA APIs
- JavaScript [ES6]
- Bulma (CSS framework)
- GitHub
- Git
- Node.js
- Webpack
- Insomnia

## Installation

1. Clone or download the repo
2. Open the `index.html` in your browser of choice

## Description

![Screenshot 2019-07-03 at 23 40 15](https://user-images.githubusercontent.com/40900195/60629114-5c6cfd00-9dec-11e9-9c1e-512d7bc8c874.png)

### Overview

[_Link to live site_](https://sammii-hk.github.io/SEI-Project-2-NASA/): https://sammii-hk.github.io/SEI-Project-2-NASA/#/

### Introduction

Liam and I worked in a pair to create a front-end web application. We chose to use NASA's APIs to include data from the Mars Rover and images from Astronomy Picture of the Day. It is an informational web application, where the APIs can be searched by date.

### Instructions

When the application loads, you enter a launchpad home page where the user can select to either enter the Mars Rover section or Astronomy Picture of the Day.

The Mars Rover index page uses a request to the API which is categorised by date, and displays all of the images available from that search.

<img width="1680" alt="Screenshot 2019-07-03 at 23 40 24" src="https://user-images.githubusercontent.com/40900195/60629116-6131b100-9dec-11e9-903c-51e645896f8f.png">

If an image is selected, you enter the Mars Rover show page, where the image is selected and information about when that miage was taken and what camera was it taken from is displayed.

<img width="1680" alt="Screenshot 2019-07-03 at 23 40 24" src="https://user-images.githubusercontent.com/40900195/60989884-fed23680-a33e-11e9-9473-93ddc3e77075.png">

Astronomy Picture of the Day index page

<img width="1680" alt="Screenshot 2019-07-03 at 23 40 40" src="https://user-images.githubusercontent.com/40900195/60629122-668efb80-9dec-11e9-9d1b-535fd470ef6a.png">

## Process

1. The first step was to install the neccassary packages required for the project, using npm.
2. Once the dependancies were installed, we then created a very basic one page app to make sure everything was up and running.
3. With the basic app structure was complete we then created an axios request to pull data from one of the APIs

### Challenges

Throughout the project there were some difficulties:

- The API we chose, although interesting, was not easy to use, particularly for our first project using an API
- The API's given information was quite limitied which restricted the possibilities of our App, so going forward I would look to find an alternative, or incorporate more than one 
- The calendar and NASA's way of formatting dates were different so we had to come up with a way to format the user's selected date before it was sent off to NASA's API

```javascript
  updateImages(randomDate = null){
    axios.get('https://api.nasa.gov/planetary/apod', {
      params: {
        date: randomDate || this.state.date.toISOString().substr(0,10),
        hd: true,
        api_key: 123456
      }
    })
      .then(res => this.setState({data: res.data }))
  }
```

### Wins

Within the project we had quite a few achievements:

- Due to the limitation of the API, we managed two APIs within a single app
- We made good use of the JavaScript logic to calculate a random date for pick from the calendar, which created a better user experience

```javascript
randomDatePicker(){
  const randomYear = Math.floor(Math.random() * 7)
  const randomMonth = Math.ceil(Math.random() * 12)
  const randomDay = Math.ceil(Math.random() * 28)
  const year = 2012 + randomYear
  const randomDate = `${year}-${randomMonth}-${randomDay}`

  this.setState({date: randomDate}, () => this.updateImages(randomDate))
}
```

## Future features

Going forward I want to expand the features of this app, I want to explore other APIs within a similar theme, to build upon the base app which we have already created and add more functionality, to explore what I can achieve.





