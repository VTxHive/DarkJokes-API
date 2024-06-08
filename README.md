<div align="center">
  <img src="https://github.com/Harneet0162/DarkJokes-API/blob/main/Dark%20Jokes%20API.png" alt="Logo"/>
</div>
<br>
# Joke API Documentation
You can access this api at https://darkjokesapi.vercel.app/
## Table of Contents

- [Introduction](#introduction)
- [API Endpoints](#api-endpoints)
  - [/](#-)
  - [/random](#random)
  - [/joke-by-id](#joke-by-id)
  - [/search](#search)
- [Error Handling](#error-handling)
- [Contributing](#contributing)

## Introduction

Welcome to the Joke API! This API provides a collection of jokes in JSON format. You can access the jokes through various endpoints, which are described below.

## API Endpoints

### Parameter Usage

Here is the breif info about all the parameters in API

| Parameter | Info |
| --------------- | --------------- |
| type | Used with /random Option 1 dark and Option 2 dad-joke, default remains anything |
| limit | Used with /random Max 20 per request, default remains 1 |
| id | Used with /joke-by-id is a interger which cannot be 0 and negative, Required parameter! |
| query | Used with /search endpoint try searching words in jokes here, Required parameter! |

### /

This is the Home page of the API. It returns a simple message welcoming the user to the Joke API and providing a link to the Github page for more information.

**Example Response:**

```json
{
  "message": "Welcome to the Dark Jokes API, This is the Root Page. Visit our Github page for documentation: https://github.com/Harneet0162/Dark-Jokes-API"
}
```


### /random

This endpoint returns a random selection of jokes based on the 'type' parameter. The 'limit' parameter specifies the maximum number of jokes to return. 
If the 'limit' parameter is greater than 20, an error message is returned.

**Example Request:**

```python
import requests
import json

response = requests.get("https://darkjokesapi.vercel.app/random?limit=3&type=dad-joke")
data = response.json()
print(data)
```

**Example Response:**

```json
[
  {
    "from": "github",
    "id": 426,
    "joke": "I've decided to put up a marquee in my garden with some funky music and flashing lights. Now is the winter of my disco tent.",
    "type": "dad-joke"
  },
  {
    "from": "github",
    "id": 493,
    "joke": "Someone called me pretentious the other day... I almost choked on my latte.",
    "type": "dad-joke"
  },
  {
    "from": "github",
    "id": 210,
    "joke": "A man walked in to a bar with some asphalt on his arm. He said 'Two beers please, one for me and one for the road.'",
    "type": "dad-joke"
  }
]
```

### /joke-by-id

This endpoint returns a joke by its ID. If the ID is less than or equal to 0, an error message is returned. 
If the joke with the specified ID does not exist, an error message is returned.

**Example Request:**

```python
import requests
import json

response = requests.get("https://darkjokesapi.vercel.app/joke-by-id?id=5")
data = response.json()
print(data)
```

**Example Response:**

```json
{
    "joke": "Karate for amputees is called partial arts",
    "id": 5,
    "from": "reddit",
    "type": "dark"
}
```

### /search

This endpoint searches for jokes containing the specified query. If no jokes are found matching the query, an error message is returned.

**Example Request:**

```python
import requests
import json

response = requests.get("https://darkjokesapi.vercel.app/search?query=black")
data = response.json()
print(data)
```

**Example Response:**

```json
[
  {
    "from": "reddit",
    "id": 10,
    "joke": "Why do black people have white palms and white bottoms of there feet?  Because there's a little good in everyone.",
    "type": "dark"
  },
  {
    "from": "reddit",
    "id": 11,
    "joke": "Why do black men cry after sex?  The pepper spray.",
    "type": "dark"
  },
  {
    "from": "reddit",
    "id": 29,
    "joke": "Sir, this is a gloryhole. We're going black then.",
    "type": "dark"
  },
  {
    "from": "reddit",
    "id": 48,
    "joke": "Why is there only two handles on a black persons casket?   Have you ever seen a trash can with more than two handles?",
    "type": "dark"
  },
  {
    "from": "reddit",
    "id": 101,
    "joke": "What's the difference between a black man and a tractor tyre? The tyre doesn't sing when you put chains on it.",
    "type": "dark"
  }
]
```
## Error Handling

The API uses HTTP exceptions to handle errors. If an error occurs, the appropriate HTTP status code and error message are returned.

## Contributing

We welcome contributions to the Joke API! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.
