
OVERVIEW
--------------

A web service built in node.js that filters JSON data of TV programmes and returns a new JSON with only the required fields for each entry.


SETUP
--------------

Easy as. The package has no dependencies so 'npm install' is not necessary.


USAGE
--------------

The API takes a JSON formatted post and returns the filtered data. If the JSON data is invalid, the API will return a 400 error in JSON format. The current filter requirements are:

 - 'drm' must be true
 - 'episodeCount' must be over 0

 If the request is valid the returned JSON will have the key 'response' with an array of elements that each have the fields 'slug', 'title' and 'image'.


**Example request:**

```json
{
    "payload": [
        {
            "country": "UK",
            "description": "What's life like when you have enough children to field your own football team?",
            "drm": true,
            "episodeCount": 3,
            "genre": "Reality",
            "image": {
                "showImage": "http://catchup.ninemsn.com.au/img/jump-in/shows/16KidsandCounting1280.jpg"
            },
            "language": "English",
            "nextEpisode": null,
            "primaryColour": "#ff7800",
            "seasons": [
                {
                    "slug": "show/16kidsandcounting/season/1"
                }
            ],
            "slug": "show/16kidsandcounting",
            "title": "16 Kids and Counting",
            "tvChannel": "GEM"
        }
    ],
    "skip": 0,
    "take": 10,
    "totalRecords": 75
}
```


**Example response:**

```json
{
    "response": [
        {
            "image": "http://catchup.ninemsn.com.au/img/jump-in/shows/16KidsandCounting1280.jpg",
            "slug": "show/16kidsandcounting",
            "title": "16 Kids and Counting"
        }
    ]
}
```
