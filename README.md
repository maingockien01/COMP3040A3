# Upcoming Concerts in Manitoba
## API Description

Our API provides the user with information about upcoming concerts in Manitoba. The user can specify a range of parameters such as a date range, an artist name, or a city name, however, all these parameters are optional. Should a user not specify any of the parameters, they will get a list of all concerts in Manitoba for the upcoming year.

The response received by the user will contain a list of concerts containing information such as a list of artists that will make an appearance in the concert, the name and address of the venue as well as the date and time of the concert.

In the case of invalid input such as a date range prior to the current date, or invalid artist or city names, the user will receive an error specifying the issue. The user may also receive an error in the case that a server-side error occurs.

## Endpoint(s)
Our API is simple, and there is only one endpoint.

```
GET /concerts
```

It will list all concerts in Manitoba in a given time range, city name, and participating artists.

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `start_date` | string | NO | start date (mm-dd-yyyy) of time range |
| `end_date` | string | NO | end date (mm-dd-yyyy) of time range |
| `city_name` | string | NO | city name to base search on |
| `artist` | string | NO | artist participates in concerts |

If no parameter is specified in a request, the API will return a response that lists all upcoming concerts in Manitoba in 1 year from the current day as default.

## Sample Request
This is a sample request for getting concerts information from our API for a given start date, end date, city name, and artist name.
The following request sample is provided in **curl**:
```
curl -H "Content-Type:application/json" -X GET "https://api.concertmb.org/concerts?start_date=11-20-2021&end_date=11-23-2021&city_name=Winnipeg&artist=Metallica"
```
## Sample Response
The response is formatted using **JSON**:

Response code: `200`

```
{
    "status": "Success"
    "concerts": [
        {
            "artists": ["Metallica", "Slash"],
            "venueName": "Bell MTS Center",
            "date": "11-21-2021",
            "venueAddress": "223 Carlton St #600, Winnipeg, MB, R3C 0V4",
            "time": "6:00pm"
        }
    ]
}
```

Response code: `400`

```
{
    "status": "Failure",
    "reason": "BadRequest",
    "message": "The user issued a faulty request. Please check the parameters and try again"
}
```

Response code: `500`

```
{
    "status": "Failure"
    "reason": "InternalServerError",
    "message": "An unexpected error occurred.",
}
```

## Resources

The request is formatted like the above example where the parameters must be given followed by "//api.concertmb.org/concerts?", the first parameter and second parameter are start_date and end_date that must be formatted as \<mm-dd-yyyy\>, followed by the city name and artist name. 

**Response code 200** responds to a successful call to the API.   
The response is formatted as JSON where the information is displayed in the order:  
* `artists`: The artist names as a list of strings.
* `venueName`: The venue name as a string.
* `date`: A string that represents the date in the format \<mm-dd-yyyy\>.
* `venueAddress`: A string that represents the address of the venue in the format {\<Street Adress>, \<City Name\>, \<Province\>, \<Postal Code\>}.
* `time`: A string that represents the start time of the concert in the format {\<hh:mm\>\<am/pm\>}.  

**Response code 400** responds if there is an error in the request and returns an error message.  

**Response code 500** responds if there is an issue on the server-side that caused an error and the request was not handled properly. A corresponding error message is also displayed.


## Group Members

* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
